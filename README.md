# Python libmagic for Apple Silicon

Install `libmagic` on Apple Silicon Macs based on M1 or M2 (or Mx):

This repository originated from [this answer](https://stackoverflow.com/a/76560266/3782119) on Stack Overflow.

**Step 1)** First, try to uninstall any other already-installed `libmagic` libraries and then install `python-magic-bin`:
```bash
$ pip uninstall python-magic
$ pip install python-magic-bin
``` 
**If it was successful, then you are all set!** If that fails, however, that means the wheel (binary) is not found for your Mac, then head to Step 2.

**Step 2)** Install `libmagic` via Homebrew:
```bash
$ brew install libmagic
```

**Step 3)** Copy the `magic` directory from [the repository](https://github.com/SHi-ON/libmagic-apple-silicon) to the directory where your Python environment libraries are located. Run `$ pip list -v` to be able to locate the path to your libraries directory. As an explanation on the origin of the `magic` directory, it has been derived from an Intel-based Mac with `python-magic` installed via pip.

**Step 4)** Copy `libmagic.dylib` from the `lib` directory in the libmagic that Homebrew has installed to the `magic/libmagic` directory in Step 3 to replace the `YOUR_libmagic.dylib`. Please note that you need to copy the original file, not the alias (symbolic link).
 Run `$ brew list -v` to help you locate the path to the library installed by Homebrew. A typical path looks like `/usr/local/Cellar/libmagic/5.44/lib`.


If you have done the steps above, then you are going to be able to import libmagic:
```python
import magic
```
