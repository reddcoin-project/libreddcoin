CXXFLAGS=$(shell pkg-config --cflags libbitcoin) -ggdb
LIBS=$(shell pkg-config --libs libbitcoin)

default: all

bootstrap.o: bootstrap.cpp
	$(CXX) -o $@ -c $< $(CXXFLAGS)

bootstrap: bootstrap.o
	$(CXX) -o $@ $< $(LIBS)

bootstrap-fast.o: bootstrap-fast.cpp
	$(CXX) -o $@ -c $< $(CXXFLAGS)

bootstrap-fast: bootstrap-fast.o
	$(CXX) -o $@ $< $(LIBS)

detect-network.o: detect-network.cpp
	$(CXX) -o $@ -c $< $(CXXFLAGS)

detect-network: detect-network.o
	$(CXX) -o $@ $< $(LIBS)

all: bootstrap bootstrap-fast detect-network 

clean:
	rm -f bootstrap bootstrap-fast detect-network
	rm -f *.o
