How to reproduce `missing source filename` error
================================================

This issue is reproducible on Windows with MSVC (Linux with gcc works correctly).

1. run `scons` so that the default target gets built succesfully
1. run `scons --interactive` and then:

    - type `b` and hit Enter (nothing gets built since the cache has been previously populated)
    - type `sh del hello.obj` and hit Enter (to manually delete the object file)
    - type `b` and hit Enter

1. the build will fail because the compiler is invoked without passing the name of the file `hello.c`:

```sh
    scons>>> b
    scons: Building targets ...
    cl /Fohello.obj /c /nologo
    cl : Command line error D8003 : missing source filename
    scons: *** [hello.obj] Error 2
    scons: building terminated because of errors.
    scons: Clearing cached node information ...
    scons: done clearing node information.
    scons>>>