# jpegxl-sys

`jpegxl-sys` is a wrapper over `jpeg-xl` library. Check out the original library [here](https://gitlab.com/wg1/jpeg-xl).

## Building

Now building `jpeg-xl` and statically linking is by default.

If you wish to use existing library and dynamically linking, then set the include path and lib path
with `DEP_JXL_INCLUDE` and `DEP_JXL_LIB` respectively, as well as `--no-default-features`.

## Usage

Check out testing units in `src/lib.rs` for some examples.

### Multithreading

Because `libjxl_threads` uses `std::thread`, if you build and statically link `jpeg-xl`, you need to
link `libc++` standard library as well. Using dynamic library doesn't need this requirement.
If you don't want the dependency, you can use `without-threads` feature.
