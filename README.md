# ExploringSystemProgramming
I'm working with a student to learn some systems programming concepts. This repo is a place for us to share resources.

## Some resources

We'll work from some exercises that someone gave themself when learning Arm assembly.
He had a Raspberry Pi - a computer about the size of a deck of cards. You can get them for about $35, and they are actually quite powerful machines. For now, though, we'll write Arm programs and run them in an emulator. You can also run Arm programs on your android, but there is more to setting up a program on a phone, unless you are willing to treat your phone as a command-line unix system. For now, we'll work with the simplest of programs.

### Exercises

The exercises we'll start with is a series of blog posts starting at

- https://thinkingeek.com/series/arm-assembler-raspberry-pi/

There are other good (actually, much better) courses and tutorials that cover the same topic:

- https://bob.cs.sonoma.edu/IntroCompOrg-RPi/sec-instrs-1.html

Which is from the book *Introduction to Computer Organization: ARM Assembly Language Using the Raspberry Pi*. The entire book is free and online and organized for convenient online use. It goes into great detail on what's going on, and will be a useful reference for us. But for now we're going to just dive ahead to the blog post, which is like skipping to chapter 9.2 in the book.

We'll write and run our programs using a beautiful online tool that you can find at

- **Online Arm emulator**: https://cpulator.01xz.net/?sys=arm

If you want to run something locally, there is also a tool you can install and run on your machine

- **Download Arm emulator**: https://salmanarif.bitbucket.io/visual/index.html

Which I suspect is similar to the web-based thing. I'll be using the web-based thing.

There are other emulators, and you can emulate a complete running unix system if you want. But we want to focus on the machine and not the things the OS can do for us. Eventually we may talk about how to write the kernel of an operating system too.

Some Arm resources:

- **Arm developer website**: https://developer.Arm.com/
- **Arm assembler reference**: https://developer.Arm.com/documentation/dui0489/latest/
- **Arm architecture learning resource**: https://developer.arm.com/documentation/102404/0201/?lang=en
- **Introduction to Arm asembly**: https://azeria-labs.com/writing-arm-assembly-part-1/

Other references:

- **Arm architecture reference**: https://developer.arm.com/documentation/ddi0487/latest/ (pdf)
- **Arm instructions quick reference**: https://pages.cs.wisc.edu/~markhill/restricted/arm_isa_quick_reference.pdf (best if you have a printer)
- **A book, which is not free**: https://www.oreilly.com/library/view/the-definitive-guide/9780124080829

### Chapter 1

The first exercise is from https://thinkingeek.com/2013/01/09/Arm-assembler-raspberry-pi-chapter-1/.  The task is to write code to leave the value `2` in `r0` (register zero).  In the exercise, there is also what is effectively a "return" instruction, but we'll ignore that for now because we're not running inside an operating system. We'll just let our program run off the end of the instruction section, which will halt the emulator. We want to write code so that the emulator runs, and when it halts the number `2` is in `r0`.

You can just type one line to get the assembly source to look like the following. The first two lines are probably already there. You want the assembly source to look like this:

```
.global _start
_start:
	
	mov r0, #2 /* Put a 2 inside the register r0 */
```

Click the "Compile and Load" button above the program, which starts up the emulator and halts it before any code is run. Then click the "Continue" button.

The program should stop at `_end` (the end of the program section) and the register display should show the value `2` now in `r0`.

Congratulations!

Now, lets look around at the emulator and talk about the Arm machine, its registers, instructions, memory, and other things. What about the stack? Where is the stack? Where are local variables? How do we write functions? Don't [cheat and look at Chapter 10](https://bob.cs.sonoma.edu/IntroCompOrg-RPi/chp-subroutine.html).

I'm not actually familiar with `Arm` assembly, so I'll be learning along with you.
