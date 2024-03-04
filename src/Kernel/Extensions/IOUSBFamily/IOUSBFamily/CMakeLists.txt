add_kext_bundle(IOUSBFamily INFO_PLIST Info.plist KERNEL_PRIVATE BUNDLE_IDENTIFIER com.apple.iokit.IOUSBFamily BUNDLE_VERSION 5.6.0)
target_sources(IOUSBFamily PRIVATE
    IOUSBBus.cpp
    IOUSBCommand.cpp
    IOUSBController_Errata.cpp
    IOUSBController_Pipes.cpp
    IOUSBControllerListElement.cpp
    IOUSBController.cpp
    IOUSBControllerUserClient.cpp
    IOUSBControllerV2.cpp
    IOUSBControllerV3.cpp
    IOUSBDevice.cpp
    IOUSBHubDevice.cpp
    IOUSBHubPolicyMaker.cpp
    IOUSBInterface.cpp
    IOUSBLog.cpp
    IOUSBNub.cpp
    IOUSBPipe.cpp
    IOUSBPipeV2.cpp
    IOUSBRootHubDevice.cpp
    IOUSBWorkLoop.cpp
)

set_property(TARGET IOUSBFamily PROPERTY CXX_STANDARD 98)
target_link_libraries(IOUSBFamily PRIVATE IOACPIFamilyHeaders IOPCIFamilyHeaders IOUSBFamilyHeaders xnu_kernel_private_headers CoreCryptoHeaders)
target_compile_options(IOUSBFamily PRIVATE -Wno-implicit-int-conversion -Wno-four-char-constants -Wmost -Wunknown-pragmas)
install(TARGETS IOUSBFamily DESTINATION System/Library/Extensions COMPONENT BaseSystem)
