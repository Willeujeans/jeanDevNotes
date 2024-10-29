# SOLID
## Single Responsibility 
_A Class should only contain things that are closely related to each other._
All data and functionality within a Class should be aligned towards accomplishing the same goal.
``` ASCII
    ┌──────────────┐   ┌──────────────────┐
    │Book          │   │Person            │
    │ -title       │   │ -books_read[Book]│
 ┌──► -pages[]     ├───► -read(Book)      │
 │  │ -flip_page() │   └──────────────────┘
 │  └──────────────┘                       
 │                                         
 │  ┌────────────────┐                     
 │  │Page            │                     
 └──┤ -words[string] │                     
    │ -get_sentence()│                     
    └────────────────┘                     
```
## Open Closed
_Code should be open to extension, and closed to modification._
We want to add functionality without changing the contents of the file.  
This can be achieved a number of ways through patterns, and design approaches.  
``` ASCII
 ┌──────────────┐     
 │  Book Class  │    
 └──────────────┘   
        ▲           
        │                 
  ┌─────┴──────┐     
  │ ComicBook  │    
  │   Class    │    
  └────────────┘    
```
_Instead of adding comicBook aspects to Book, ComicBook inherit from Book and override the methods._  
## Liskov Substitution
_A Child class should be able to do everything a Parent can do._
A Child Class should at any time, be able to replace its Parent Class and accomplish the same things.
If we were to add Audiobooks to types of Books you can read, we could have it inherit from Book. But you can't Read AudioBooks, if they inherit from the Book Class then the Parent class could do something (_Read_) that the Child (_AudioBook_) can not do. Instead we can create a Literature Class for both Book Class and Audiobook Class to inherit from.
``` ASCII  
  1.                2.                              
  ┌─────────┐               ┌──────────┐         
  │  Book   │               │Literature│         
  └─────────┘               └──────────┘         
       ▲                        ▲  ▲             
  ┌────┴────┐       ┌─────────┐ │  │ ┌─────────┐ 
  │AudioBook│       │  Book   ├─┘  └─┤AudioBook│ 
  └─────────┘       └─────────┘      └─────────┘ 
```
## Interface Segregation
_Make your interfaces small to reduce the amount of methods that are forced to be implemented._
Separating `Read Interface` and `Write Interface` from the `Author Interface `allows us to use them in multiple other interfaces without giving the `Book Interface` the `write()` method that will not be used.
```ASCII 
                                 ┌───────────────────┐  
                                 │ Author Interface: │  
                                 │                   │  
                           ┌──►  │ -Write Interface  │  
                           │     │ -Read Interface   │  
                           │     └───────────────────┘  
                           │     ┌───────────────────┐  
  ┌─────────────────────┐  │     │ Book Interface:   │  
  │ Author Interface:   │  ├──►  │                   │  
  │                     │  │     │ -Read Interface   │  
  │ -Read()             ├──┤     └───────────────────┘  
  │ -Write()            │  │     ┌───────────────────┐  
  └─────────────────────┘  │     │ Read Interface:   │  
                           ├──►  │                   │  
                           │     │ -Read()           │  
                           │     └───────────────────┘  
                           │     ┌───────────────────┐  
                           │     │ Write Interface:  │  
                           └──►  │                   │  
                                 │ -Write()          │  
                                 └───────────────────┘   
```
## Dependency Inversion
_A high level Class should not depend on a lower level Class._
Following this principle allows you to easily change the Classes your High Level Class uses.
If the Book Class used a Page class this would make the high level class (_Book_) dependent on the lower level class (_Page_),

Using Dependency Injection, we can create an interface `Ipage` that variations of `Page` will implement, this makes changing which type of `Page` the book contains very easy.
``` ASCII
                         ┌───────────────┐                          
                         │Ipage Interface│                          
                         │               │                          
                ┌────────► -get_words()  ◄─────────┐                
                │        │               │         │                
                │        └───────────────┘         │                
                │                                  │                
    ┌───────────┴─────────────┐     ┌──────────────┴─────────────┐  
    │BookPage implements Ipage│     │JournalPage implements Ipage│  
    │                         │     │                            │  
  ┌─┤ @override               │     │ @override                  │  
  │ │ -get_words()            │     │ -get_words()               │  
  │ └─────────────────────────┘     └────────────────────────────┘  
  │                                                                 
  │                                                                 
  │    ┌──────────────────┐                                         
  │    │Book              │                                         
  │    │                  │                                         
  └────► -Page(Ipage page)│                                         
       └──────────────────┘                                          
```
The reason why this works is because the Book Class will no longer care which type of Page it uses, it only cares that it can call the Methods and properties that the Page Class has, any Class that implements an interface must have the method that was specified.