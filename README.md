
SARUtils is the newest, greatest library of them all!

Download library from here:
https://github.com/stiana/SARUtils/releases/tag/v0.1.2


Usage example
```
VAR
  fbConcater : FB_Concater;
  stringResult : STRING;

  myInt : INT := 123;
  myReal : REAL := 45.67;
  myWord : WORD := 16#ABCD;
  myString : STRING := 'example';
  myBool : BOOL := TRUE;
END_VAR


fbConcater.Clear().V(myInt).L('/').V(myReal).L('/').V(myBool).L('/').V(myWord).L('/').V(myString);

stringResult := fbConcater.GetString(); // Will result in the following string '123/45.67/TRUE/43981/example'
```
