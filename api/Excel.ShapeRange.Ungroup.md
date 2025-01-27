---
title: ShapeRange.Ungroup method (Excel)
keywords: vbaxl10.chm640094
f1_keywords:
- vbaxl10.chm640094
ms.prod: excel
api_name:
- Excel.ShapeRange.Ungroup
ms.assetid: d7794250-e4b4-6998-e43d-4b41475ac6c9
ms.date: 05/14/2019
ms.localizationpriority: medium
---


# ShapeRange.Ungroup method (Excel)

Ungroups any grouped shapes in the specified shape or range of shapes. Disassembles pictures and OLE objects within the specified shape or range of shapes.


## Syntax

_expression_.**Ungroup**

_expression_ A variable that represents a **[ShapeRange](Excel.shaperange.md)** object.


## Return value

A **ShapeRange** object that represents the ungrouped shapes.


## Remarks

Because a group of shapes is treated as a single object, grouping and ungrouping shapes changes the number of items in the **[Shapes](excel.shapes.md)** collection, and changes the index numbers of items that come after the affected items in the collection.


## Example

This example ungroups any grouped shapes and disassembles any pictures or OLE objects on _myDocument_.

```vb
Set myDocument = Worksheets(1) 
For Each s In myDocument.Shapes 
 s.Ungroup 
Next
```

<br/>

This example ungroups any grouped shapes on _myDocument_ without disassembling pictures or OLE objects on the document.

```vb
Set myDocument = Worksheets(1) 
For Each s In myDocument.Shapes 
 If s.Type = msoGroup Then s.Ungroup
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]