# dzaima/APL

## General Tips
 - dzaima/APL has long integer support using suffix `L`.
 - If you require an executable of your dzaima/APL program:
   - Go to `src/APL/Main.java` 
   - Navigate to the line `Scope global = new Scope();`
   - Add your code to a string, and call `exec(string,global)` after that line
   - Add `System.exit(0);` after that
   - execute `./build`, your executable will be stored as `APL.jar`.

## Solved Examples
