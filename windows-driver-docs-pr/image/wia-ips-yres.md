---
title: WIA_IPS_YRES
description: The WIA_IPS_YRES property contains the current vertical resolution setting, in pixels per inch, for a device.
keywords: ["WIA_IPS_YRES Imaging Devices"]
topic_type:
- apiref
api_name:
- WIA_IPS_YRES
api_location:
- Wiadef.h
api_type:
- HeaderDef
ms.date: 10/05/2021
ms.localizationpriority: medium
---

# WIA_IPS_YRES

The WIA_IPS_YRES property contains the current vertical resolution setting, in pixels per inch, for a device.

Property Type: VT_I4

Valid Values: WIA_PROP_RANGE or WIA_PROP_LIST

Access Rights: Read/write or read-only

## Remarks

An application sets the WIA_IPS_YRES property to set the vertical resolution. The WIA minidriver creates and maintains this property.

If a device can be set to only a single value, create a WIA_PROP_LIST type and place the valid value in it. This situation also applies when one resolution setting depends on another resolution. (For example, the vertical resolution can depend on the horizontal resolution.)

WIA_IPS_YRES is required for all image acquisition-enabled items and stored image items; it is not available for storage items.

## Requirements

**Header:** wiadef.h (include Wiadef.h)

## See also

[**WIA_IPS_XEXTENT**](wia-ips-xextent.md)

[**WIA_IPS_XPOS**](wia-ips-xpos.md)

[**WIA_IPS_XRES**](wia-ips-xres.md)

[**WIA_IPS_YEXTENT**](wia-ips-yextent.md)

[**WIA_IPS_YPOS**](wia-ips-ypos.md)
