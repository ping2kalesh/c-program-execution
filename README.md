# C program execution process

1. Preprocessor converts the source file (app.c) into pre-processed file (app.i)

    ```markdown
    gcc -E app.c -o app.i
    ```

2. Compiler converts the pre-processed file (app.i) into assembly (app.s)

    ```markdown
    gcc -S app.i -o app.s
    ```

3. Assembler takes the assembly file (app.s) as input and generates relocatable object file (app.o)

    ```markdown
    gcc -c app.s -o app.o
    ```

4. Linker converts the relocatable object file (app.o) into executable file (app.out)

    ```markdown
    gcc app.o -o app.out
    ```


The steps 1 and 2 are usually referred as compilation and the steps 3 and 4 are referred as build.

#testing




