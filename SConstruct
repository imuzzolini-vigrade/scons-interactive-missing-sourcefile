env = DefaultEnvironment()

env.Program("hello.c")

# HOW TO REPRODUCE WITH MSVC ON WINDOWS:
# 1. run "scons" so that the default target gets built succesfully
# 2. run "scons --interactive"
# 2. type "b" and hit Enter (nothing gets built since the cache has been previously populated)
# 4. type "sh del hello.obj" and hit Enter (to delete the object file)
# 5. type "b" and hit Enter
# 6. the build will fail because the compiler is invoked without passing the name of the file "hello.c"
