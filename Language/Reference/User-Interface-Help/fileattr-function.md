---
title: FileAttr function (Visual Basic for Applications)
keywords: vblr6.chm1008919
f1_keywords:
- vblr6.chm1008919
ms.prod: office
ms.assetid: 368baa57-40ed-306c-3371-96691d071aed
ms.date: 12/12/2018
ms.localizationpriority: medium
---


# FileAttr function

Returns a [Long](../../Glossary/vbe-glossary.md#long-data-type) representing the file mode for files opened by using the **[Open](open-statement.md)** statement.

## Syntax

**FileAttr**(_filenumber_, _returntype_)

<br/>

The **FileAttr** function syntax has these [named arguments](../../Glossary/vbe-glossary.md#named-argument):

|Part|Description|
|:-----|:-----|
|_filenumber_|Required; [Integer](../../Glossary/vbe-glossary.md#integer-data-type). Any valid [file number](../../Glossary/vbe-glossary.md#file-number).|
|_returntype_|Required; **Integer**. Number indicating the type of information to return. Specify 1 to return a value indicating the file mode. On 16-bit systems only, specify 2 to retrieve an operating system file handle. _Returntype_ 2 is not supported in 32-bit systems and causes an error.|

## Return values

When the _returntype_ [argument](../../Glossary/vbe-glossary.md#argument) is 1, the following return values indicate the file access mode:

|Mode|Value|
|:-----|:-----:|
|**Input**|1|
|**Output**|2|
|**Random**|4|
|**Append**|8|
|**Binary**|32|

## Example

This example uses the **FileAttr** function to return the file mode and file handle of an open file. The file handle is returned only on 16-bit systems; on 32-bit systems, passing 2 as a second argument generates an error.

```vb
Dim FileNum, Mode, Handle
FileNum = 1    ' Assign file number.
Open "TESTFILE" For Append As FileNum    ' Open file.
Mode = FileAttr(FileNum, 1)    ' Returns 8 (Append file mode).
Handle = FileAttr(FileNum, 2)    ' Returns file handle.
Close FileNum    ' Close file.

```

## See also

- [Functions (Visual Basic for Applications)](../functions-visual-basic-for-applications.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]