## Installation Guide for wxWidgets
```
> mkdir third_party
> cd third_party
> git clone

> cd wxWidgets
> mkdir build-custom
> cd build-custom

> ../configure \
    --with-gtk=3 \
    --disable-debug \
    --prefix=$PWD/library

> make -j$(nproc)
> make install

> mv library/ ../../

# test installation
> ./library/bin/wx-config --version

# if working
> rm -rf wxWidgets
> mv library/ wxWidgets/
```
