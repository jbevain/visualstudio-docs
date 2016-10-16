---
title: "Compiler Error CS1654"
ms.custom: na
ms.date: 10/01/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 471c1298-1908-449d-b765-8dc3cd81a11d
caps.latest.revision: 9
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
# Compiler Error CS1654
Cannot modify members of 'variable' because it is a 'read-only variable type'  
  
 This error occurs when you try to modify members of a variable which is read-only because it is in a special construct.  
  
 One common area that this occurs is within [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md) loops. It is a compile-time error to modify the value of the collection elements. Therefore, you cannot make any modifications to elements that are [value types](../Topic/Value%20Types%20\(C%23%20Reference\).md), including [structs](../Topic/Structs%20\(C%23%20Programming%20Guide\).md). In a collection whose elements are [reference types](../Topic/Reference%20Types%20\(C%23%20Reference\).md), you can modify accessible members of each element, but any try to add or remove or replace complete elements will generate [Compiler Error CS1656](../Topic/Compiler%20Error%20CS1656.md).  
  
## Example  
 The following example generates error CS1654 because `Book` is a `struct`. To fix the error, change the `struct` to a [class](../Topic/class%20\(C%23%20Reference\).md).  
  
```  
using System.Collections.Generic;  
using System.Text;  
  
namespace CS1654  
{  
  
    struct Book  
    {  
        public string Title;  
        public string Author;  
        public double Price;  
        public Book(string t, string a, double p)  
        {  
            Title=t;  
            Author=a;  
            Price=p;  
  
        }  
    }  
  
    class Program  
    {  
        List<Book> list;  
        static void Main(string[] args)  
        {  
             //Use a collection initializer to initialize the list  
            Program prog = new Program();  
            prog.list = new List<Book>();  
            prog.list.Add(new Book ("The C# Programming Language",  
                                    "Hejlsberg, Wiltamuth, Golde",  
                                     29.95));  
            prog.list.Add(new Book ("The C++ Programming Language",  
                                    "Stroustrup",  
                                     29.95));  
            prog.list.Add(new Book ("The C Programming Language",  
                                    "Kernighan, Ritchie",  
                                    29.95));  
            foreach(Book b in prog.list)  
            {  
                //Compile error if Book is a struct  
                //Make Book a class to modify its members  
                b.Price +=9.95; // CS1654  
            }  
  
        }  
    }  
}  
  
```