Example program using cudawrappers
==================================

This is an example project that uses the cudawrappers library as a dependency
by automatically downloading a copy from GitHub.

To run the example, install the vector_add_example program from this repository:
```bash
git clone https://github.com/nlesc-recruit/usage-example-cmake-pull
cd usage-example-cmake-pull
cmake -DCMAKE_INSTALL_PREFIX=$HOME/.local -S . -B build
make -C build
make -C build install
```
the `-DCMAKE_INSTALL_PREFIX=$HOME/.local` tells the computer to install the
program in `~/.local`. This is useful if you do not have root access
to the computer you are working on.

The example can be run with:
```bash
vector_add_example
```
or, if `~/.local/bin` is not in your `$PATH`,
```bash
~/.local/bin/vector_add_example
```

The expected behaviour is that
```
hurray! 2
```
is printed to the terminal.
