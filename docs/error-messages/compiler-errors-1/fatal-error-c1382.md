---
title: "Fatal Error C1382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-tools"]
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: ["C1382"]
dev_langs: ["C++"]
helpviewer_keywords: ["C1382"]
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fatal Error C1382
the PCH file 'file' has been rebuilt since 'obj' was generated. Please rebuild this object  
  
 When using [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), the compiler detected a .pch file that is newer than a CIL .obj that points to it. The information in the CIL .obj file is out of date. Rebuild the object.  
  
 C1382 can also occur if you compile with **/Yc**, but also pass multiple source code files to the compiler.  To resolve, do not use **/Yc** when passing multiple source code files to the compiler.  For more information, see [/Yc (Create Precompiled Header File)](../../build/reference/yc-create-precompiled-header-file.md).