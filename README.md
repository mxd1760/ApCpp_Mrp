# MRP for build error when using APCpp as submodule with vs2022 command prompt

recreating the issue discussed in [this](https://github.com/N00byKing/APCpp/pull/22) pull request


## How to reproduce

1. Clone this repository on a windows machine

2. Initialize submodules
  ```
  git submodule update --recursive --init
  ```

3. Open "Developer Command Prompt for VS 2022"

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
>    --add Microsoft.VisualStudio.Workload.NativeDesktop;includeRecommended
>  ```

4. `cd` into the repo

5. run `cmake -B build`