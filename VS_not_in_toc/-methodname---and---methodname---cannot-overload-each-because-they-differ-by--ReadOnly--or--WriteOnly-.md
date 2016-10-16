---
title: "&lt;methodname&gt;&#39; and &#39;&lt;methodname&gt;&#39; cannot overload each because they differ by &#39;ReadOnly&#39; or &#39;WriteOnly&#39;"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2440fd29-e205-4004-b2ee-9d954d17b8d3
caps.latest.revision: 8
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# &lt;methodname&gt;&#39; and &#39;&lt;methodname&gt;&#39; cannot overload each because they differ by &#39;ReadOnly&#39; or &#39;WriteOnly&#39;
You have attempted to overload two methods that differ from each other only in their `ReadOnly` and `WriteOnly` declarations. You cannot use anything other than the argument list to differentiate versions.  
  
 **Error ID:** BC30366  
  
### To correct this error  
  
-   Make sure the methods are differentiated by more than `ReadOnly` and `WriteOnly`.  
  
## See Also  
 [Considerations in Overloading Procedures](../Topic/Considerations%20in%20Overloading%20Procedures%20\(Visual%20Basic\).md)