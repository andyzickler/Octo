Octo
====

Octo is a high-level assembler for the Chip8 virtual machine, complete with an environment for testing programs. You can try it out [here](http://johnearnest.github.io/Octo/).

While a program is running, you can press escape to return to the editor. The Chip8 keypad is represented on your keyboard as follows:

	Chip8 Key   Keyboard
	---------   ---------
	 1 2 3 C     1 2 3 4
	 4 5 6 D     q w e r
	 7 8 9 E     a s d f
	 A 0 B F     z x c v

To learn more about Chip8 programming techniques, have a look at the [documentation](https://github.com/JohnEarnest/Octo/tree/gh-pages/docs) section. The manual for Octo assembly language can be found [here](https://github.com/JohnEarnest/Octo/tree/gh-pages/docs/Manual.md).

The Octo assembler can also be used as a command-line tool via a [Node.js](http://nodejs.org) fontend:

	$ ./octo
		usage: octo [--decompile] [--roundtrip] [--qshift]
			[--qloadstore] <source> [<destination>]
	$ cat simple.8o
		: main
			va := 1
			vb := 2
	$ ./octo simple.8o simple.ch8
	$ hexdump simple.ch8
		0000000 6a 01 6b 02                                    
		0000004

The `--decompile` option can be used to send an existing Chip8 binary through Octo's general-purpose decompiler.
