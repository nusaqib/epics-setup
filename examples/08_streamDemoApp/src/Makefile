TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = streamDemo
# streamDemo.dbd will be created and installed
DBD += streamDemo.dbd

# streamDemo.dbd will be made up from these files:
streamDemo_DBD += base.dbd

# streamDemo_registerRecordDeviceDriver.cpp derives from streamDemo.dbd
streamDemo_SRCS += streamDemo_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
streamDemo_SRCS_DEFAULT += streamDemoMain.cpp
streamDemo_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#streamDemo_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
streamDemo_LIBS += $(EPICS_BASE_IOC_LIBS)


##### ADDED FOR STREAM DEVICE ############
streamDemo_DBD += stream.dbd
streamDemo_DBD += asyn.dbd
streamDemo_DBD += drvAsynIPPort.dbd

streamDemo_LIBS += asyn
streamDemo_LIBS += stream

##########################################
#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

