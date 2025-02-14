# WebUSB - CWDWG (ChipWon Device Working Group)

## Overview
The repository is worked out by CWDWG (ChipWon Device Working Group). This project is used for demostrating the WebUSB, a JavaScript application programming interface, is for securely providing access to USB devices from web applications.

## Connect to Site
GitHub Pages site for connecting to ChipWon `WebUSB CWDWG Port` devices:
- https://arthur-chipwon.github.io/webusb/

## Implementation
WCID, which it stands for "Windows Compatible ID", is an extension of the WinUSB Device functionality, put forward by Microsoft during the Windows 8 Developer Preview and that uses capabilities (Microsoft OS Descriptors, or MODs). Then after USB 3.0 publish, WCID has been developed to Microsoft OS Compatibility Descriptors within Binary device Object Store (BOS) Descriptor.

**Important:** Only USB 2.0 devices, version 2.0 or later version 2.01, can be recognized as WCID by inqueried Microsoft OS String Descriptor, i.e. 0xEE string descriptor. Thus the Device Descriptor's bcdUSB field must be set to 0x0200 or 0x0201.

**Important:** Either USB devices version 2.0 or later, i.e. the Device Descriptor's bcdUSB field as 0x0210 or above, also be recognized as WCID by inqueried the Binary device Object Store (BOS). The Binary device Object Store is a concept introduced in USB 3.0 but has also been backported to USB 2.0 devices as part of version 2.1. Thus this demostration do not support to set the Device Descriptor's bcdUSB field as 0x0210 due to the previous constriant.

**Important:** By the way, the WCID device by reported the BOS Descriptor, i.e. the Device Descriptor's bcdUSB field as 0x0210 or above, only support the number of interfaces, which it is greater than 2. And the composite device still have to include 1 non-vendor-specific interface or above. A WebUSB device with supported BOS involving WebUSB Descriptor and Microsoft OS 2.0 Descriptor is as shown as the link [Build A Device for WebUSB](https://developer.chrome.com/docs/capabilities/build-for-webusb/).

## Demos And References
- [WinUSB device - MSDN](https://learn.microsoft.com/en-us/windows-hardware/drivers/usbcon/automatic-installation-of-winusb/)
- [WebUSB API - W3C](https://wicg.github.io/webusb/)
- https://github.com/pbatard/libwdi/wiki/WCID-Devices/
- https://github.com/WICG/webusb/
- https://github.com/webusb/arduino/
- [Build A Device for WebUSB](https://developer.chrome.com/docs/capabilities/build-for-webusb/)
