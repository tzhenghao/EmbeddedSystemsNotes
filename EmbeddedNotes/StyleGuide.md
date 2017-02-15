#Style Guide

DO NOT use dynamic memory allocation after task initialization
	- Memory allocators and garbage collectors - unpredictable behavior.
	- Forgetting to free memory
	- Overstepping boundaries on allocated memory
	- Stray pointers

ALL communication and data exchanges SHOULD happen via IPC (inter-process communication)

DO NOT use "goto"s.

CAREFUL with the use of externs. Extern x with int type may be different than extern x with double type from another file.

Functions of more than 10 lines should have at least 1 assertion.

Use of C preprocessor SHALL be limited to file inclusion and simple macros.

DO NOT define macros within a function or a block.

DO NOT use non-constant pointers to functions.

RECOMMENDED FILE FORMAT:

Include files -> macro definitions -> typedefs -> external declarations -> file static declarations -> function declarations
