add_kext_bundle(IOI2CFamily KERNEL_PRIVATE INFO_PLIST Info.plist BUNDLE_IDENTIFIER com.apple.iokit.IOI2CFamily BUNDLE_VERSION 1.0.8b1)
target_sources(IOI2CFamily PRIVATE
    IOI2CBus.cpp
    IOI2CService.cpp
    IOI2CUserClient.cpp
    IOI2CController.cpp
    IOI2CDevice.cpp
)

set_property(TARGET IOI2CFamily PROPERTY CXX_STANDARD 98)
target_compile_options(IOI2CFamily PRIVATE -Wmost -Wno-four-char-constants -Wno-unknown-pragmas)
target_link_libraries(IOI2CFamily PRIVATE IOI2CFamilyHeaders)
install(TARGETS IOI2CFamily DESTINATION System/Library/Extensions COMPONENT BaseSystem)

add_library(IOI2CFamilyHeaders INTERFACE)
target_include_directories(IOI2CFamilyHeaders INTERFACE include)