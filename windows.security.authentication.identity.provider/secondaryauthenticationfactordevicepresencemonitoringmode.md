---
-api-id: T:Windows.Security.Authentication.Identity.Provider.SecondaryAuthenticationFactorDevicePresenceMonitoringMode
-api-type: winrt enum
---

<!-- Enumeration syntax.
public enum SecondaryAuthenticationFactorDevicePresenceMonitoringMode : int 
-->

# Windows.Security.Authentication.Identity.Provider.SecondaryAuthenticationFactorDevicePresenceMonitoringMode

## -description
Contains values that describe the type of connection that the system uses to monitor the presence of a companion device (such as a wearable device). 

## -enum-fields
### -field Unsupported:0
Device presence monitoring is not supported.

### -field SystemManaged:2
The system uses classing Bluetooth protocol to monitor the presence of the companion device.

### -field AppManaged:1
The system uses an app that corresponds to the companion device to monitor its presence.

## -remarks
A companion device must specify this value when registering for presence monitoring. If the companion device has only registered for secondary authentication and not presence monitoring, its corresponding [**SecondaryAuthenticationFactorInfo**](SecondaryAuthenticationFactorInfo.md) will show a default value of *unsupported*.

## -see-also

## -examples
