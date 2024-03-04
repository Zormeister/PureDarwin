add_kext_bundle(IOHIDFamily KERNEL_PRIVATE INFO_PLIST Info.plist BUNDLE_IDENTIFIER com.apple.iokit.IOHIDFamily BUNDLE_VERSION 2.0.0)
target_sources(IOHIDFamily PRIVATE
    AppleEmbeddedHIDEventService.cpp
    AppleEmbeddedKeyboard.cpp
    AppleUserHIDDevice.cpp
    AppleUserHIDEventService.cpp
    Cosmo_USB2ADB.c
    IOBSDConsole.cpp
    IOFixed64.cpp
    IOHIDActionQueue.cpp
    IOHIDConsumer.cpp
    IOHIDDevice.cpp
    IOHIDDeviceElementContainer.cpp
    IOHIDDeviceShim.cpp
    IOHIDElementContainer.cpp
    IOHIDElementPrivate.cpp
    IOHIDEvent.cpp
    IOHIDEventDriver.cpp
    IOHIDEventQueue.cpp
    IOHIDEventRepairDriver.cpp
    IOHIDEventService.cpp
    IOHIDEventServiceFastPathUserClient.cpp
    IOHIDEventServiceQueue.cpp
    IOHIDEventServiceUserClient.cpp
    IOHIDEventSource.cpp
    IOHIDFamilyPrivate.cpp
    IOHIDInterface.cpp
    IOHIDKeyboard.cpp
    IOHIDKeyboardDevice.cpp
    IOHIDKeyboardEventDevice.cpp
    IOHIDLibUserClient.cpp
    IOHIDPointing.cpp
    IOHIDPointingDevice.cpp
    IOHIDPointingEventDevice.cpp
    IOHIDProviderPropertyMerger.cpp
    IOHIDPrivate.cpp
    IOHIDResource.cpp
    IOHIDResourceUserClient.cpp
    IOHIDSystem.cpp
    IOHIDUserClient.cpp
    IOHIDUserDevice.cpp
    IOHIDWorkLoop.cpp
    IOHIDevice.cpp
    IOHIKeyboard.cpp
    IOHIKeyboardMapper.cpp
    IOHIPointing.cpp
    IOHITablet.cpp
    IOHITabletPointer.cpp)

set_property(TARGET IOHIDFamily PROPERTY CXX_STANDARD 98)
target_compile_options(IOHIDFamily PRIVATE -Wmost -Wno-four-char-constants -Wno-unknown-pragmas)
target_link_libraries(IOHIDFamily PRIVATE IOGraphicsFamilyHeaders IOHIDFamilyHeaders)
install(TARGETS IOHIDFamily DESTINATION System/Library/Extensions COMPONENT BaseSystem)