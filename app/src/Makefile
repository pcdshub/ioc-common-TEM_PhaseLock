TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build an ioc application
# Use PROD_IOC_RTEMS for RTEMS only
# Use PROD_IOC_Linux for Linux only
PROD_IOC = TEM_PhaseLock

# TEM_PhaseLock.dbd will be created and installed
DBD += TEM_PhaseLock.dbd

# TEM_PhaseLock.dbd will be made up from these files:
TEM_PhaseLock_DBD += base.dbd
TEM_PhaseLock_DBD += iocAdmin.dbd
TEM_PhaseLock_DBD += asSupport.dbd
TEM_PhaseLock_DBD += asyn.dbd
TEM_PhaseLock_DBD += drvAsynSerialPort.dbd
TEM_PhaseLock_DBD += drvAsynIPPort.dbd
TEM_PhaseLock_DBD += stream.dbd

# <name>_registerRecordDeviceDriver.cpp will be created from <name>.dbd
TEM_PhaseLock_SRCS += TEM_PhaseLock_registerRecordDeviceDriver.cpp
TEM_PhaseLock_SRCS_DEFAULT += TEM_PhaseLockMain.cpp

# Add locally compiled object code
#TEM_PhaseLock_SRCS += dbSubExample.c

TEM_PhaseLock_LIBS += devIocStats
TEM_PhaseLock_LIBS += autosave
TEM_PhaseLock_LIBS += asyn
TEM_PhaseLock_LIBS += stream
TEM_PhaseLock_LIBS += $(EPICS_BASE_IOC_LIBS)

ifneq '$(T_A)' 'RTEMS-beatnik'
PROD_SYS_LIBS_DEFAULT += pcre
SHRLIB_DEPLIB_DIRS += $(PCRE_LIB)
endif

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

