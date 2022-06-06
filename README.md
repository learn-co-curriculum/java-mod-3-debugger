# Debugger

## Learning Goals

- Use the debugging features in IntelliJ

## Introduction

We will use IntelliJ as the IDE for walking through a sample debugging session.
This guide is assuming that you have already installed IntelliJ and configured
it to run some of the sample code we have been going through in this module.

An IDE debugger is a great tool for going through your code step by step to try
to figure out why something may not be working the way that you anticipated.

In your project view, navigate to the class you would like to debug and open it
by double-clicking it. Here I have opened open our `TechnicalProjectRunner`
class from earlier in this module:

![open-class.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/open-class.png)

When you run the debugger, it will run your class just like you would with the
run command, except that it can stop on specific lines of code and pause the
execution of your program. The places where you ask the debugger to stop are
called "breakpoints" and can be specified anywhere in your source code.

When a debugger comes across a breakpoint, it will stop and give you control
over the execution of the subsequent lines of code.

Let's first run our `TechnicalProjectRunner` class through the debugger without
any breakpoints - right click on any empty area in the open file and select the
debug option:

![right-click-debug.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/right-click-debug.png)

You will then the following output:

![default-debug-output.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/default-debug-output.png)

You will notice a different window at the bottom of your IDE with some buttons
we haven't seen before. Let's go ahead and set up a breakpoint so we can have
another run through the debugger but have it pause this time, so we can learn
more about the options it provides when our program is paused.

In order to set a breakpoint, click anywhere in the open space to the right of
the line number in the editor window - a red dot will appear to indicate that
you successfully set a breakpoint on that line:

![set-breakpoint.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/set-breakpoint.png)

Now run the debugger again and you should see the IDE pause the execution of
your program once it gets to that line:

![breakpoint-reached.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/breakpoint-reached.png)

The panel at the bottom of IntelliJ now shows a lot of information to help us
understand what's happening in the program and give us options on how to
proceed.

1. Execution is currently on line 9

![exec-on-line-9.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/exec-on-line-9.png)

2. You can inspect any of the values in your program or add the name of a
   specific variable to keep a "watch" on, which will pop the variable in that
   panel when it comes into scope:

![inspect-variables.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/inspect-variables.png)

3. Once you have inspected all the values you're currently interested in, you
   can choose how to proceed with the execution of the program:

![execution-options.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/execution-options.png)

1.  Step Over: runs the current line of code and stops again on the next line
2.  Step Into: follows the instruction on the current line of code on the line
    of code that it points to
3.  Force Step Into: use when Step Into doesn't actually go into the call - this
    happens when the call is to a method in a compiled class (like a
    `System.out.println()` for example)
4.  Step Out: finishes the execution of the current method and pauses on the
    next line in the calling method
5.  Run to cursor: continues the execution of the program until the debugger
    reaches the instruction where your cursor is current positioned

To continue our example, we will proceed by using the "Step Into" option, which
takes us to the `startDelivery()` method and pauses on the first line:

![start-delivery.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/start-delivery.png)

You can continue running the debugger in this way to step through every line of
code and inspect every value in your program.

You can also choose to resume execution of your program or stop the debugger all
together in the left hand side of the debugger panel:

![debugger-run-options.png](https://curriculum-content.s3.amazonaws.com/java-mod-2/type-casting/debugger-run-options.png)

When you resume the execution of your program, the debugger will run your
program until the next breakpoint or until completion if it does not run into
another breakpoint.

Debugging a great tool to understand what your program is actually doing and to
help you find the reason(s) it's not doing what you expect it to.
