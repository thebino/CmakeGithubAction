# Github actions cmake sample

![Build](https://github.com/thebino/CmakeGithubAction/workflows/Build/badge.svg)

This is a cmake sample using Github actions with a matrix build.


## Build
Generate the project by calling 
```shell_script
cmake . -B build
```

Compile the project
```shell_script
cmake --build build
```

Create an installer with the following command:
```shell_script
cpack --config build/CPackConfig.cmake 
```

