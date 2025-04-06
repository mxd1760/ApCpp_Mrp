# MRP for build error when using APCpp as submodule with vs2022 command prompt

recreating the issue discussed in [this](https://github.com/N00byKing/APCpp/pull/22) pull request


## How to reproduce

1. Clone this repository on a windows machine

2. Open "Developer Command Prompt for VS 2022"

> [!NOTE]
>  This can be installed using an administrator command prompt and the following commands:
>  ```
>  winget install Microsoft.VisualStudio.2022.BuildTools 
>  ```
>  ```
>  "%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\setup.exe" modify^
>    --passive^
>    --channelId VisualStudio.17.Release^
>    --productId Microsoft.VisualStudio.Product.BuildTools^
>    --add Microsoft.VisualStudio.Workload.VCTools;includeRecommended
>  ```

3. `cd` into the repo

4. Initialize submodules
  ```
  git submodule update --recursive --init
  ```

5. run `cmake -B build -D ^"CMAKE_TOOLCHAIN_FILE=%VCPKG_ROOT%\scripts\buildsystems\vcpkg.cmake^"`

## Try out solutions

This repo has multiple branches

 - master: reproduces the issue
 - my_fix: fix with WORKING_DIRECTORY
 - N00byking_fix: fix with CMAKE_CURRENT_BINARY_DIR

To try these out switch to the branch and run
```
git submodule update --recursive --init
```
again in order to make sure you are using the correct commit for the submodule