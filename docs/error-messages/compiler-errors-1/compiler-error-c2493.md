---
title: "Compiler Error C2493 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: ["cpp-tools"]
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: ["C2493"]
dev_langs: ["C++"]
helpviewer_keywords: ["C2493"]
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2493
illegal form of __based  
  
 A `__based` expression must be based on a pointer.  
  
 The following sample generates C2493:  
  
```  
// C2493.cpp  
// compile with: /c  
char mybase;  
int __based(mybase) ptr;   // C2493  
  
// OK  
char * mybase;  
int __based(mybase) * ptr;  
```