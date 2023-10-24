CXXSTD = c++17

CXX = nvc++
CXXFLAGS = -std=$(CXXSTD) -cuda -gpu=cc60 -gpu=rdc
LINKFLAGS = $(CXXFLAGS) -cudalib=curand

a.out: main.o amrex_random.o
	$(CXX) $(LINKFLAGS) -o $@ $^

amrex_random.o: amrex_random.cpp amrex_random.H
	$(CXX) $(CXXFLAGS) -c -o $@ $<

main.o: main.cpp amrex_random.H
	$(CXX) $(CXXFLAGS) -c -o $@ $<

clean:
	${RM} *.o a.out

FORCE:

.PHONY: clean
