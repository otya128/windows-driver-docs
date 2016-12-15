---
title: Providing a Vendor-Defined ACPI Device Interface
author: windows-driver-content
description: Providing a Vendor-Defined ACPI Device Interface
MS-HAID:
- 'opregdg\_41ee73b4-351a-4bd0-9566-14b9ad69bd68.xml'
- 'acpi.providing\_a\_vendor\_defined\_acpi\_device\_interface'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 5a7fd03b-6d4f-481b-8e4e-0e1deaf88583
keywords: ["ACPI devices WDK , device interfaces", "vendor-defined device interfaces WDK ACPI", "device interfaces WDK ACPI", "function drivers WDK ACPI , vendor-defined device interfaces", "WDM function drivers WDK ACPI , vendor-defined device interfaces"]
---

# Providing a Vendor-Defined ACPI Device Interface


## <a href="" id="ddk-providing-a-vendor-defined-acpi-device-interface-kg"></a>


A vendor can provide an optional [*device interface*](https://msdn.microsoft.com/library/windows/hardware/ff556277#wdkgloss-device-interface) and support for custom IOCTLs to operate an ACPI device's functional device object ([*FDO*](https://msdn.microsoft.com/library/windows/hardware/ff556280#wdkgloss-fdo)).

The function driver typically calls [**IoRegisterDeviceInterface**](https://msdn.microsoft.com/library/windows/hardware/ff549506) in its [**AddDevice**](https://msdn.microsoft.com/library/windows/hardware/ff540521) routine to register a device interface. The driver calls [**IoSetDeviceInterfaceState**](https://msdn.microsoft.com/library/windows/hardware/ff549700) to enable the interface after Plug and Play starts the FDO. The driver should disable the interface if a device is removed by Plug and Play.

The device interface class GUID is vendor-defined.

 

 


--------------------

