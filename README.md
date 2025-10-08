From Wikipedia, the free encyclopedia
CodeView
Original author	David Norris
Developer	Microsoft
Initial release	1985; 40 years ago
Operating system	MS-DOS
Platform	x86
Type	Debugger

CodeView is a standalone debugger created by David Norris at Microsoft in 1985 as part of its development toolset.[1] It originally shipped with Microsoft C 4.0 and later. It also shipped with Visual Basic for MS-DOS, Microsoft BASIC PDS, and a number of other Microsoft language products.[2] It was one of the first debuggers for MS-DOS to be full-screen oriented, rather than line-oriented (as Microsoft's predecessors DEBUG and SYMDEB or Digital Research's SID).
Overview

When running, CodeView presents the user with several windows that can be tiled, moved, sized and otherwise manipulated via the keyboard or mouse, with CodeView 4.x providing a richer interface. Some of the windows include:

    Code window – the code window showed the currently debugged code in its source code context.
    Data window – a hexadecimal dump of a user-specified memory area.
    Watch window – a contextual display of variables by name.
    Locals window – a contextual display of variables local to the current function.
    Command window – user commands (using the same or similar syntax as DEBUG and SYMDEB) could be entered here.
    Assembly window – the assembly (machine code) was displayed, allowing for single-stepping through functions.
    Register window – to visualize the 80x86 register contents, including segments, flags and the FPU (CodeView existed before MMX and other SIMD extensions).
    Output window – a window showing startup operations and debugging information relating to breakpoints,[2] hardware breaks (interrupt 0 and 3), etc.

Features
386 mode – 8086, 80286 and 80386 and later processors. 386 enhanced mode is activated by a menu option, allowing for 32-bit registers and disassembly.
Monochrome monitor support – allows debugging on either a single color (CGA, EGA or VGA) monitor with page/memory swapping between the user application and the CodeView screen, or using a separate monochrome monitor. The monochrome monitor exists in memory address space 0xb0000, while the color monitor exists at 0xb8000 for text and 0xa0000 for graphics. Use of the monochrome monitor with its separate memory address space allows debugging graphics applications without affecting the display, as well as all text modes. Monochrome monitors are limited to 25 lines, whereas color monitors allow 25, 43 or 50 line mode, allowing for more information on the screen at the same time.

Creating symbolic debugging output, which allows memory locations to be viewed by their programmer-assigned name, along with a program database showing the source code line related to every computer instruction in the binary executable, is enabled by the command line switch -Zi given to the compiler, and -CO given to the linker. Variants like -Zs and -Zd provide lesser information, and smaller output files which, during the early 1990s, were important due to limited machine resources, such as memory and hard disk capacity. Many systems in those days had 8MB of memory or less.

CodeView handles all program models, including TINY, SMALL, COMPACT, MEDIUM, LARGE and HUGE, with TINY (DOS-based .COM files) having their symbolic debugger information stored in a separate file, with all of the other .EXE formats containing the symbolic information directly inside the executable. This often introduced a notable size increase, and it therefore became desirable for some developers to use #pragma switches within their C (and later C++) source code to prevent the majority of the application from having symbolic output, and instead limiting that output to only those portions which required it for current debugging.

CodeView version 3.x and 4.x introduced various transport layers, which removed some of the memory space limitations to this form of symbolic debugging. Typically the debugger runs in the lower 640KB memory space alongside the application being debugged, which greatly decreases the amount of memory available to the application being debugged. The transport layer allows only a stub to exist in main memory, while the bulk of the debugger code resides in EMS or XMS (memory above the 1 MB barrier, or outside of the normal 0 KB - 640 KB address space typically used by DOS programs). CodeView also came with a CVPACK command-line utility, which can reduce the size of the CodeView-generated information internally, while still retaining full symbolic access to data.
Visual C++ support

Microsoft released Visual C++ 1.0 with CodeView functionality integrated directly into a single programming environment, known as the Integrated Development Environment (IDE) -- though CodeView was still available in the 16-bit versions of Visual C++. QuickC and a number of other development tools in the 'Quick' series also supported this move to a single-source IDE, what became the precursor to the modern Visual Studio developer environment, as well as the model for countless other developer toolsets.

This integration was seen by many developers as a more natural way of developing software because both coding and debugging could be handled without switching programs or context, and all from the same logical location (even though internally many separate programs were running to support editing, compiling and debugging). As a result, most development tools and/or platforms offer similar products or features.

Today, the debugger is considered an integrated and essential part of the Microsoft Visual Studio family of products, and owes its true roots to CodeView, and the enhancements seen in version 4.x specifically.
Symdeb

Another debugging product available from Microsoft in the mid-1980s was SYMDEB.[3]

It had over 30 commands, and was described by PC Magazine as a step up from DEBUG.[4] Codeview in turn was described as "a fullscreen SYMDEB".
See also
Borland Turbo Debugger
SoftICE
x86 memory models
Microsoft Visual Studio Debugger
Program database - CodeView formats and types are still present in debugging information generated by modern C++ toolchains

References

"CodeView 3.x". WinWorld.
Microsoft Macro Assembler 5.1 - Microsoft CodeView and Utilities. Microsoft Corporation. 1987. p. 157. Document No. 4108-40010-500-R03-1287.
Par, Jeff (2018-02-25). "A Short History of SYMDEB". PCjs Machines. Retrieved 2019-05-19.
"SYMDEB: A step up from Debug". PC World. 1986-10-14. p. 296.
"SYMDEB". PC Magazine. Vol. 5, no. 17. Ziff Davis, Inc. 1986-09-30. p. 38. ISSN 0888-8507.
"MS C 4.0 Documentation Added". OS2museum.com.
"CodeView Type Records — LLVM 13 documentation". llvm.org. Retrieved 2021-12-19.
