# MacOS

## Malware analysis

Persistance

Once the malware has infected the system, its goal is to persist on the computer, which can be done in multiple way as a startup item in launch item or login item, etc.



### Disassembling & decompiling

The majority of mach-o is written in object-c, which retain their class when compiled into bin, include the classes, methods and variables. Tools such as class-dump can be used to extract the information of examination.

Packer - It quite common for bin to be packed code e.g. python coded that have been packed into a bin file using  Platypus, there exist many type of packers.

Platypus - bin that have been packed with platypus it code that viewed inside the application directory contents/resources/ looking for a file named script. If this file exist it most likely a application created using platypus.  

PyInstaller - identified by look for the embedded string Py-SetPythonHome,  The compiled coded can be extracted from the binary by using pyinstxtracotor, to decompile the compiled python by using a decompiler such as decompiler.com

Electron - identified by javascript files can be found inside /contents/resources dir, achieved in .asar files