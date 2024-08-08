# SARUtils - TwinCAT 3.1 library with an improved concat function.


Download library from here:

https://github.com/stiana/SARUtils/releases/tag/v0.1.2

### Methods
- Clear() - Empties the string
- V() - Adds a variable of ANY type to the string
- L() - Adds a literal to the string i.e. L('this is a literal')
- GetString() - Returns the resulting string


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
