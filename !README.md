This downloads standalone 64-bit MSVC compiler, linker & other tools, also headers/libraries from Windows SDK into portable folder, without installing Visual Studio. Has bare minimum components - no UWP/Store/WindowsRT stuff, just files & tools for 64-bit native desktop app development.

Run `python.exe portable-msvc.py` and it will download output into `msvc` folder. By default it will download latest available MSVC & Windows SDK - currently v14.32.17.2 and v10.0.22621.0.

You can list available versions with `python.exe portable-msvc.py --show-versions` and then pass versions you want with `--msvc-version` and `--sdk-version` arguments.

To use cl.exe/link.exe from output folder, first run `setup.bat` - after that PATH/INCLUDE/LIB env variables will be setup to use all the tools as usual. You can also use clang-cl.exe with these includes & libraries.

To use clang-cl.exe without running setup.bat, pass extra `/winsysroot msvc` argument (msvc is folder name where output is stored).
