add_kext_bundle(IOGraphicsFamily KERNEL_PRIVATE INFO_PLIST Info.plist BUNDLE_IDENTIFIER com.apple.iokit.IOGraphicsFamily BUNDLE_VERSION 585.1)
target_sources(IOGraphicsFamily PRIVATE
    GMetric/GMetric.cpp
    GTrace/GTrace.cpp
    IODisplay.cpp
    IODisplayWrangler.cpp
    IODisplayWranglerUserClients.cpp
    IOBacklightDisplay.cpp
    IOI2CInterface.cpp
    IOFramebuffer.cpp
    IOFramebufferUserClient.cpp
    IOBootFramebuffer.cpp
)

set_property(TARGET IOGraphicsFamily PROPERTY CXX_STANDARD 11)
set_property(TARGET IOGraphicsFamily PROPERTY C_STANDARD 11)
target_compile_options(IOGraphicsFamily PRIVATE -Wno-implicit-int-conversion -Wno-inconsistent-missing-override -Wno-sign-conversion -Wno-shadow)
target_link_libraries(IOGraphicsFamily PRIVATE IOGraphicsFamilyHeaders IOACPIFamilyHeaders IOPCIFamilyHeaders IONDRVSupportHeaders CoreCryptoHeaders IOHIDFamilyHeaders)
install(TARGETS IOGraphicsFamily DESTINATION System/Library/Extensions COMPONENT BaseSystem)

add_library(IOGraphicsFamilyHeaders INTERFACE)
target_include_directories(IOGraphicsFamilyHeaders INTERFACE include)
