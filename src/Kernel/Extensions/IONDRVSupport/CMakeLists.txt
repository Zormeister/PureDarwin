add_kext_bundle(IONDRVSupport KERNEL_PRIVATE INFO_PLIST Info.plist BUNDLE_IDENTIFIER com.apple.iokit.IONDRVSupport BUNDLE_VERSION 585.1)
target_sources(IONDRVSupport PRIVATE
    IONDRV.cpp
    IONDRVFramebuffer.cpp
    IONDRVLibraries.cpp
)

set_property(TARGET IONDRVSupport PROPERTY CXX_STANDARD 11)
target_compile_options(IONDRVSupport PRIVATE -Wno-implicit-int-conversion -Wno-inconsistent-missing-override -Wno-sign-conversion -Wno-shadow)
target_link_libraries(IONDRVSupport PRIVATE IONDRVSupportHeaders)
install(TARGETS IONDRVSupport DESTINATION System/Library/Extensions COMPONENT BaseSystem)

add_library(IONDRVSupportHeaders INTERFACE)
target_include_directories(IONDRVSupportHeaders INTERFACE include)
