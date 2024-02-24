add_kext_bundle(AppleSMBIOS INFO_PLIST Info.plist BUNDLE_IDENTIFIER com.apple.driver.AppleSMBIOS BUNDLE_VERSION 1.7)
target_sources(AppleSMBIOS PRIVATE
    AppleSMBIOS.cpp
)

set_property(TARGET AppleSMBIOS PROPERTY CXX_STANDARD 98)
target_link_libraries(AppleSMBIOS PRIVATE IOACPIFamilyHeaders IOPCIFamilyHeaders)
target_compile_options(AppleSMBIOS PRIVATE -Wno-implicit-int-conversion -Wno-four-char-constants -Wmost -Wunknown-pragmas)
install(TARGETS AppleSMBIOS DESTINATION System/Library/Extensions COMPONENT BaseSystem)
