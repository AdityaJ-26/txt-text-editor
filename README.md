## Installation Guide for wxWidgets
```
mkdir third_party
cd third_party
git clone git@github.com:wxWidgets/wxWidgets.git wxWidget

cd wxWidgets
# if required submodules are not present
git submodule update --init --recursive

mkdir build-custom
cd build-custom

# use --prefix if you want local installation rather than system wide installation
../configure \
    --with-gtk=3 \
    --disable-debug \
    --prefix=<absolute_path_to_third_party>/wxWidgets

make -j$(nproc)
make install

cd ../..
# test installation
./wxWidgets/bin/wx-config --version

# if working
rm -rf wxWidget
```
