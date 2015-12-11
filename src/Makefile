OBJECTS = main.o particle.o v3.o
SRC=main.cpp particle.cpp v3.cpp
INC=.

NVCC=nvcc
NVCCFLAGS=-arch=sm_20


all: $(OBJECTS)
	$(NVCC) $(NVCCFLAGS) $(OBJECTS) -o app

%.o: %.cpp
	$(NVCC) -x cu $(NVCCFLAGS) $(INC) -dc $< -o $@

clean:
	rm -f *.o app
