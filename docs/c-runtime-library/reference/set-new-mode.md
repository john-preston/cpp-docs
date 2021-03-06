---
title: "_set_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-standard-libraries"]
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: ["_set_new_mode"]
apilocation: ["msvcrt.dll", "msvcr80.dll", "msvcr90.dll", "msvcr100.dll", "msvcr100_clr0400.dll", "msvcr110.dll", "msvcr110_clr0400.dll", "msvcr120.dll", "msvcr120_clr0400.dll", "ucrtbase.dll", "api-ms-win-crt-heap-l1-1-0.dll"]
apitype: "DLLExport"
f1_keywords: ["set_new_mode", "_set_new_mode"]
dev_langs: ["C++"]
helpviewer_keywords: ["handler modes", "_set_new_mode function", "set_new_mode function"]
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_new_mode
Sets a new handler mode for `malloc`.  
  
## Syntax  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### Parameters  
 `newhandlermode`  
 New handler mode for `malloc`; valid value is 0 or 1.  
  
## Return Value  
 Returns the previous handler mode set for `malloc`. A return value of 1 indicates that, on failure to allocate memory, `malloc` previously called the new handler routine; a return value of 0 indicates that it did not. If the `newhandlermode` argument does not equal 0 or 1, returns -1.  
  
## Remarks  
 The C++ `_set_new_mode` function sets the new handler mode for [malloc](../../c-runtime-library/reference/malloc.md). The new handler mode indicates whether, on failure, `malloc` is to call the new handler routine as set by [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). By default, `malloc` does not call the new handler routine on failure to allocate memory. You can override this default behavior so that, when `malloc` fails to allocate memory, `malloc` calls the new handler routine in the same way that the `new` operator does when it fails for the same reason. For more information, see the [new](../../cpp/new-operator-cpp.md) and [delete](../../cpp/delete-operator-cpp.md) operators in the *C++ Language Reference*. To override the default, call:  
  
```  
_set_new_mode(1)  
```  
  
 early in your program or link with Newmode.obj (see [Link Options](../../c-runtime-library/link-options.md)).  
  
 This function validates its parameter. If `newhandlermode` is anything other than 0 or 1, the function invokes the invalid parameter handler, as described in [Parameter Validation](../../c-runtime-library/parameter-validation.md). If execution is allowed to continue, **_**`set_new_mode` returns -1 and sets `errno` to `EINVAL`.  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h>|  
  
 For more compatibility information, see [Compatibility](../../c-runtime-library/compatibility.md) in the Introduction.  
  
## See Also  
 [Memory Allocation](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)