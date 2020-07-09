# Geany-Windows-Setup

Geany is a Open-Source, Lightweight Editor for C and C++ programming.

Refer this for Linux Setup.<br />
https://github.com/Errichto/youtube/wiki/Linux-setup<br />
I have referred this guide to create a guide for Windows OS.

### Setup Instruction:
	
1. Install MinGW Environment from http://www.mingw.org/<br />
	1.1. Download Setup for Windows.<br />
  1.2. Install it.<br />
  1.3. Open MinGW Installation Manager.<br />
  1.4. Select All Checkboxes in Basic Setup.<br />
  1.5. Apply Changes.<br />
  1.6. It will install MinGW. (If you get error for some file, Run Installer Again)<br />
  1.7. Add Path to System Environment Variables. (Most Windows PC will have Path like this `C:\MinGW\bin`)<br />
      Refer this to add Path https://stackoverflow.com/questions/5733220/how-do-i-add-the-mingw-bin-directory-to-my-system-path<br />
2. Download and Install Geany Editor from https://www.geany.org/
3. Geany Configuration for C and C++<br />
  3.1. Open preferences with Ctrl+Alt+P.<br />
  3.2. Change Key Binding for convinence.<br />
4. Go to `Build` -> `Set Build Commands` and copy these flags.<br />
  Compile(F8): `g++ -std=c++17 -Wshadow -Wall -o "%e" "%f" -O2 -Wno-unused-result`<br />
  Build (F9): `g++ -std=c++17 -Wshadow -Wall -o "%e" "%f" -fsanitize=undefined -fsanitize-undefined-trap-on-error -D_GLIBCXX_DEBUG`<br />
  If you get compilation errors, try changing from c++17 to c++14 and/or removing sanitizers (one fsanitize flags).<br />
  As `-fsanitize=address` is not working in MinGW for some odd reasons. So, I have not included it. Let me know if anyone has solution for this.<br />
5. If your computer beeps after compilation, unmark `Beep on errors` in Preferences -> General -> Miscellaneous.

If you find that to insert dot(.) or comma(,), you need to press button two times and then press backspace to print symbols.<br />
I have a fix for you.<br />

Go to `Settings -> Time & Language -> Language`. Add a preferred language as English(United States). Select all it's options. Download it and keep it as first preference.<br />
Then Go to `Settings -> Devices -> Typing -> Advanced Keyboard Settings`. Set Override for default input method as English(United States).<br />
Resolved
