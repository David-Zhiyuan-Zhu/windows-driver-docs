---
title: TVOT_COMBOBOX
description: The TVOT_COMBOBOX option type consists of a combo box inside a group box.
keywords: ["TVOT_COMBOBOX Print Devices"]
topic_type:
- apiref
api_name:
- TVOT_COMBOBOX
api_location:
- compstui.h
api_type:
- HeaderDef
ms.date: 09/08/2021
ms.localizationpriority: medium
---

# TVOT_COMBOBOX

The TVOT_COMBOBOX option type consists of a combo box inside a group box.

## OPTITEM structure  

**Sel/pSel**  
Index into the [**OPTPARAM**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optparam) array that is pointed to by the **pOptParam** member of the option's [**OPTTYPE**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_opttype) structure. This specifies the currently selected option parameter.

## OPTPARAM structure array (pOptParam member of OPTTYPE)

**pData**  
**pOptParam**\[0\]->**pData** points to the first text string to be displayed in the combo box. **pOptParam**\[1\]->**pData** points to the second text string to be displayed in the combo box. **pOptParam**\[*n*\]->**pData** points to the *n*th text string to be displayed in the combo box.

**IconID**  
**pOptParam**\[0\]->**IconID** identifies an icon to be associated with the first text string. **pOptParam**\[1\]->**IconID** identifies an icon to be associated with the second text string. **pOptParam**\[*n*\]->**IconID** identifies an icon to be associated with the *n*th text string.

**lParam**  
Not used.

## OPTTYPE structure

**Type**  
TVOT_COMBOBOX

**Count**  
The number of OPTPARAM structures; that is, the number of text strings to be displayed in the combo box.

**Style**  
The following optional bit flags can be specified.

| Flag | Description |
|--|--|
| OTS_LBCB_INCL_ITEM_NONE | If set, CPSUI includes a "None" string in the combo box. If a user selects "None", the **Sel/pSel** union is set to negative one. |
| OTS_LBCB_NO_ICON16_IN_ITEM | If set, CPSUI does not draw each option parameter's icon (**IconID** in OPTPARAM) when displaying the parameter's value in the combo box. |
| OTS_LBCB_PROPPAGE_CBUSELB | When the option is displayed on a non-treeview property sheet page, it is displayed as a listbox instead of a combobox. |
| OTS_LBCB_SORT | If set, CPSUI displays text strings in alphabetic order. |

**BegCtrlID**  
If **pDlgPage** in [**COMPROPSHEETUI**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui) identifies a CPSUI-supplied page, or if **DlgTemplateID** in [**DLGPAGE**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_dlgpage) identifies a CPSUI-supplied template, **BegCtrlID** is not used. Otherwise, **BegCtrlID** must contain the first control identifier of a sequentially numbered set of control identifiers. Control identifiers must identify the following Windows controls:

| Control Identifier | Windows Control |
|--|--|
| **BegCtrlID** contents | Group box |
| **BegCtrlID** contents+1 | Title text |
| **BegCtrlID** contents+2 | Combo box |
| **BegCtrlID** contents+3 | Combo box icon |
| **BegCtrlID** contents+4 | Extended check box or extended push button (optional) |
| **BegCtrlID** contents+5 | Extended check box or extended push button icon (optional) |

For additional information, see [Customizing CPSUI-Supported Window Controls](./customizing-cpsui-supported-window-controls.md).

## Requirements

**Header:** compstui.h (include Compstui.h)

## See also

[**OPTITEM**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem)

[**OPTPARAM**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optparam)

[**OPTTYPE**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_opttype)
