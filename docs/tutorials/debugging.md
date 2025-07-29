# Debugging C code with lldb

This tutorial explains how to debug the C code in the R source using the CodeLLDB VS Code extension.

**1) Build R**

Follow the tutorial [Building R](./building_r.md) to build R from source.

**2) Start an R terminal**

Start an R terminal, using the version of R you just built (e.g. `r-devel`). Get the process ID of the R session:
```r
Sys.getpid()
```

**3) Start the debugger**

In the "Run and Debug" side bar, select `(lldb) Attach to R` and click the green play button.

![run-debug-sidebar](https://user-images.githubusercontent.com/3343008/270405753-42515289-3253-4e67-9642-42b78a9c3132.png)

A prompt will appear at the top of the window. Enter the process ID from the previous step.

**4) Set a breakpoint**

In a C file in the R source, e.g. `$TOP_SRCDIR/src/nmath/rgamma.c`, set a breakpoint by clicking in the gutter to the left of a line number.

![set-breakpoint](https://user-images.githubusercontent.com/3343008/270405756-3a7894a4-969c-4c3e-8809-23214a60155b.png)

**5) Run R code**

In the R terminal, run some R code that calls the C function where you set a breakpoint, e.g.
```r
rgamma(5, 1)
```
The debugger should stop at the breakpoint. You can now inspect the values of variables, step through the code, etc.

![debugging](https://user-images.githubusercontent.com/3343008/270405759-a783b98c-8519-453f-b31c-3086b97f3944.png)
