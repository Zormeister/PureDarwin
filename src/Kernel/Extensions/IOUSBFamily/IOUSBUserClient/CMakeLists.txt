add_kext_bundle(IOUSBUserClient INFO_PLIST Info.plist KERNEL_PRIVATE BUNDLE_IDENTIFIER com.apple.iokit.IOUSBUserClient BUNDLE_VERSION 5.6.0)
target_sources(IOUSBUserClient PRIVATE
   IOUSBDeviceUserClient.cpp
   IOUSBInterfaceUserClient.cpp
   IOUSBInterfaceUserClientV3.cpp
   IOUSBUserClientInit.cpp
)

set_property(TARGET IOUSBUserClient PROPERTY CXX_STANDARD 98)
target_link_libraries(IOUSBUserClient PRIVATE IOACPIFamilyHeaders IOPCIFamilyHeaders IOUSBFamilyHeaders xnu_kernel_private_headers CoreCryptoHeaders)
target_compile_options(IOUSBUserClient PRIVATE -Wno-implicit-int-conversion -Wno-four-char-constants -Wmost -Wunknown-pragmas)
install(TARGETS IOUSBUserClient DESTINATION System/Library/Extensions/IOUSBFamily.kext/PlugIns/ COMPONENT BaseSystem)
