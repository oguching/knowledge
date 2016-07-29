Access modifiers in OOP languages

Private
* can be accessed only from the class where it is declared

Protected
 * can be accessed from the class where it is declared and also from inherited classes
 
Public
 * can accessed outside of the class.
 
A rule of thumb I remember reading is to set class variables as private and methods as public. Another approach to managing visibility is to mark all properties as _protected_, and only allow access to them using `getter` and `setter` methods.
