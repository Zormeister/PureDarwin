add_library(IOUSBFamilyHeaders INTERFACE)
target_include_directories(IOUSBFamilyHeaders INTERFACE include)

# HIDDriver - TBD, after IOHID & IOG are working
# TODO: IOUSBCompositeDriver, AppleUSBHub, AppleUSBMergeNub, AppleUSBOHCI, AppleUSBUHCI, AppleUSBECHI, AppleUSBXHCI, AppleUSBiPod & AppleUSBOpticalMouse

add_subdirectory(IOUSBFamily)