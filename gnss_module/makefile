# makefile for sample
# author: zhuang.sr
# date: 2019.09.12

CXX = arm-poky-linux-gnueabi-g++  -march=armv7ve -marm -mfpu=neon -mfloat-abi=hard -mcpu=cortex-a7 --sysroot=/opt/poky-st/2.4.2/sysroots/cortexa7hf-neon-poky-linux-gnueabi

# define dependence library
LDFLAGS = -L ../lib
LIBS = -lstarlocation-ntrip -lgyro_module  -lpthread -lsins_gps -shared -fPIC

# define objects and target name
OBJS = gnss_module.cpp
TAR = ../lib/libgnss_module.so

# complie command
$(TAR) : $(OBJS)
	$(CXX) $(OBJS) $(LDFLAGS) $(LIBS) -o $(TAR) -Wl,-rpath,../lib

# clean command
clean:
	rm -f $(TAR)
