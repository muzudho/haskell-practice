๐2023-01-09 mon (ๆไบบใฎๆฅ) 22:30  

ใจใใใใ ๅฌๅผใตใคใใ่ชญใฟ้ฒใใ  

๐[First steps](https://www.haskell.org/ghcup/steps/)  

๐ใจใซใใไปฅไธใฎใใกใคใซใไฝใ  

hello.hs:  

```haskell
main = putStrLn "Hello, Haskell!"
```

๐ใใใฆไปฅไธใฎใณใใณใใๆ้ต  

```shell
ghc hello.hs
```

Output:  

```shell
[1 of 1] Compiling Main             ( hello.hs, hello.o )
Assembler messages:
Error: can't open C:\\Users\\ใใใงใ\\AppData\\Local\\Temp\\ghc19776_0\\ghc_2.s for reading: No such file or directory
`gcc.exe' failed in phase `Assembler'. (Exit code: 1)
```

ใจใฉใผใๅบใใ  
`C:\\Users\\ใใใงใ\\AppData\\Local\\Temp\\` ใพใงใฏๆใใ `ghc19776_0` ใฏ็กใใ  
ใฐใฐใ  

๐````gcc.exe' failed in phase `Assembler'. (Exit code: 1)```  

๐['gcc.exe' failed in phase 'Assembler' while running Haskell code)](https://stackoverflow.com/questions/65051731/gcc-exe-failed-in-phase-assembler-while-running-haskell-code)  
๐[gcc.exe' failed in phase Linker'. (Exit code: 1) #8560](https://github.com/haskell/cabal/issues/8560)  

๐ `ghcup` ใซใใฐใใใใจใฎใใจ  

๐ ไปฅไธใฎใณใใณใใ่ฉฆใ  

```shell
ghc --version
The Glorious Glasgow Haskell Compilation System, version 9.2.5
```

```shell
ghcup rm ghc 9.2.5
[ Info  ] downloading: https://raw.githubusercontent.com/haskell/ghcup-metadata/master/ghcup-0.0.7.yaml as file C:\ghcup\cache\ghcup-0.0.7.yaml
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed 
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
[ Warn  ] New ghc version available. To upgrade, run 'ghcup install ghc 9.4.4'      
[ Warn  ] New cabal version available. To upgrade, run 'ghcup install cabal 3.8.1.0'
[ Warn  ] New stack version available. To upgrade, run 'ghcup install stack 2.9.3'  
[ Info  ] verifying digest of: gs.exe
[ Info  ] Removing ghc symlinks
[ Info  ] Removing ghc-x.y.z symlinks
[ Info  ] Removing/rewiring ghc-x.y symlinks
[ Info  ] Removing files safely from: C:\ghcup\ghc\9.2.5
[ Info  ] After removing GHC you might also want to clean up your cabal store at: ~/.cabal/store/ghc-<ghcver>
```

```shell
ghcup install ghc 9.2.5
[ Warn  ] New cabal version available. To upgrade, run 'ghcup install cabal 3.8.1.0'
[ Warn  ] New stack version available. To upgrade, run 'ghcup install stack 2.9.3'  
[ Info  ] verifying digest of: gs.exe
[ Info  ] downloading: https://downloads.haskell.org/~ghc/9.2.5/ghc-9.2.5-x86_64-unknown-mingw32.tar.xz as file C:\ghcup\tmp\ghcup-75300077afc2ab5c\ghc-9.2.5-x86_64-unknown-mingw32.tar.xz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed  
100  479M  100  479M    0     0  23.3M      0  0:00:20  0:00:20 --:--:-- 25.0M
[ Info  ] verifying digest of: ghc-9.2.5-x86_64-unknown-mingw32.tar.xz
[ Info  ] Unpacking: ghc-9.2.5-x86_64-unknown-mingw32.tar.xz to C:\ghcup\tmp\ghcup-075c0be68bf65859
[ Info  ] Installing GHC (this may take a while)
[ Info  ] Merging file tree from "C:\ghcup\tmp\ghcup-075c0be68bf65859\ghc-9.2.5-x86_64-unknown-mingw32" to "C:\ghcup\ghc\9.2.5"
[ Info  ] GHC installation successful
```

ๅใคใณในใใผใซใงใใใใใชใฎใง Visual Studio Code ใๅ่ตทๅ  

๐ใใใฆไปฅไธใฎใณใใณใใๆ้ต  

```shell
ghc --version
'ghc' ใฏใๅ้จใณใใณใใพใใฏๅค้จใณใใณใใ
ๆไฝๅฏ่ฝใชใใญใฐใฉใ?ใพใใฏใใใ ใใกใคใซใจใใฆ่ช่ญใใใฆใใพใใใ
```

๏ผ  

```shell
ghcup --version
The GHCup Haskell installer, version v0.1.18.0
```

```shell
ghcup install ghc
[ Info  ] downloading: https://raw.githubusercontent.com/haskell/ghcup-metadata/master/ghcup-0.0.7.yaml as file C:\ghcup\cache\ghcup-0.0.7.yaml
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
[ Warn  ] New ghc version available. To upgrade, run 'ghcup install ghc 9.4.4'
[ Warn  ] New cabal version available. To upgrade, run 'ghcup install cabal 3.8.1.0'
[ Warn  ] New stack version available. To upgrade, run 'ghcup install stack 2.9.3'
[ Info  ] verifying digest of: gs.exe
[ Warn  ] ghc-9.2.5 is already installed; if you really want to reinstall it, you may want to run 'ghcup install cabal --force 9.2.5'
```

`ghc 9.4.4` ใใใ๏ผ  
ใใใใใใใคใณในใใผใซใใ  

```shell
ghcup rm ghc 9.2.5
[ Warn  ] New ghc version available. To upgrade, run 'ghcup install ghc 9.4.4'
[ Warn  ] New cabal version available. To upgrade, run 'ghcup install cabal 3.8.1.0'
[ Warn  ] New stack version available. To upgrade, run 'ghcup install stack 2.9.3'
[ Info  ] verifying digest of: gs.exe
[ Info  ] Removing ghc-x.y.z symlinks
[ Info  ] Removing/rewiring ghc-x.y symlinks
[ Info  ] Removing files safely from: C:\ghcup\ghc\9.2.5
[ Info  ] After removing GHC you might also want to clean up your cabal store at: ~/.cabal/store/ghc-<ghcver>
```

```shell
ghcup install ghc 9.4.4
[ Warn  ] New cabal version available. To upgrade, run 'ghcup install cabal 3.8.1.0'
[ Warn  ] New stack version available. To upgrade, run 'ghcup install stack 2.9.3'
[ Info  ] verifying digest of: gs.exe
[ Info  ] downloading: https://downloads.haskell.org/~ghc/9.4.4/ghc-9.4.4-x86_64-unknown-mingw32.tar.xz as file C:\ghcup\tmp\ghcup-4fa0ac2853ddf15f\ghc-9.4.4-x86_64-unknown-mingw32.tar.xz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  265M  100  265M    0     0  24.9M      0  0:00:10  0:00:10 --:--:-- 25.7M
[ Info  ] verifying digest of: ghc-9.4.4-x86_64-unknown-mingw32.tar.xz
[ Info  ] Unpacking: ghc-9.4.4-x86_64-unknown-mingw32.tar.xz to C:\ghcup\tmp\ghcup-0813c6c1334909a6
[ Info  ] Installing GHC (this may take a while)
[ Info  ] Merging file tree from "C:\ghcup\tmp\ghcup-0813c6c1334909a6\ghc-9.4.4-x86_64-unknown-mingw32" to "C:\ghcup\ghc\9.4.4"
[ Info  ] GHC installation successful
```

ๅใคใณในใใผใซใงใใใใใชใฎใง Visual Studio Code ใๅ่ตทๅ  

๐ใใใฆไปฅไธใฎใณใใณใใๆ้ต  

```shell
ghc --version
'ghc' ใฏใๅ้จใณใใณใใพใใฏๅค้จใณใใณใใ
ๆไฝๅฏ่ฝใชใใญใฐใฉใ?ใพใใฏใใใ ใใกใคใซใจใใฆ่ช่ญใใใฆใใพใใใ
```

๏ผ  

ใใใ `cabal` ใจ `stack` ใฎใขใใใฐใฌใผใใ่ฉฆใใฆใใ  

```shell
ghcup install cabal 3.8.1.0
[ Warn  ] New stack version available. To upgrade, run 'ghcup install stack 2.9.3'
[ Info  ] verifying digest of: gs.exe
[ Info  ] downloading: https://downloads.haskell.org/~cabal/cabal-install-3.8.1.0/cabal-install-3.8.1.0-x86_64-windows.zip as file C:\ghcup\tmp\ghcup-2a57c47b5948ba84\cabal-install-3.8.1.0-x86_64-windows.zip
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 14.7M  100 14.7M    0     0  15.6M      0 --:--:-- --:--:-- --:--:-- 15.6M
[ Info  ] verifying digest of: cabal-install-3.8.1.0-x86_64-windows.zip
[ Info  ] Unpacking: cabal-install-3.8.1.0-x86_64-windows.zip to C:\ghcup\tmp\ghcup-76468813f70e80fe
[ Info  ] Installing cabal
[ Info  ] Cabal installation successful
```

```shell
ghcup install stack 2.9.3
[ Info  ] verifying digest of: gs.exe
[ Info  ] downloading: https://github.com/commercialhaskell/stack/releases/download/v2.9.3/stack-2.9.3-windows-x86_64.tar.gz as file C:\ghcup\tmp\ghcup-798a9b6a97e6f0d9\stack-2.9.3-windows-x86_64.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 17.0M  100 17.0M    0     0  5579k      0  0:00:03  0:00:03 --:--:-- 8103k
[ Info  ] verifying digest of: stack-2.9.3-windows-x86_64.tar.gz
[ Info  ] Unpacking: stack-2.9.3-windows-x86_64.tar.gz to C:\ghcup\tmp\ghcup-f397c0835b1717f5
[ Info  ] Installing stack
[ Info  ] Stack installation successful
[ Info  ] Stack manages GHC versions internally by default. To improve integration, please visit:
[ ...   ]   https://www.haskell.org/ghcup/guide/#stack-integration
[ ...   ] 
[ ...   ] Also check out:
[ ...   ]   https://docs.haskellstack.org/en/stable/yaml_configuration
[ ...   ] 
```

```shell
ghcup install ghc 9.4.4
[ Info  ] verifying digest of: gs.exe
[ Warn  ] ghc-9.4.4 is already installed; if you really want to reinstall it, you may want to run 'ghcup install cabal --force 9.4.4'
```

ใจใใใใ Visual Studio Code ใๅ่ตทๅ  

๐ใใใฆไปฅไธใฎใณใใณใใๆ้ต  

```shell
ghc --version
'ghc' ใฏใๅ้จใณใใณใใพใใฏๅค้จใณใใณใใ
ๆไฝๅฏ่ฝใชใใญใฐใฉใ?ใพใใฏใใใ ใใกใคใซใจใใฆ่ช่ญใใใฆใใพใใใ
```

ใใใใๆฌกใฎใณใใณใใๆ้ต  

```shell
ghcup install cabal --force 9.4.4
[ Info  ] verifying digest of: gs.exe
[ Error ] Both installation and setting the tool failed. Install error was: Unable to find a download for the requested version/distro. 
[ ...   ] Set error was: The version 9.4.4 of the tool cabal is not installed.
[ Error ] Also check the logs in C:\ghcup\logs
```

ใญใฐใฎๅ?ดๆใ็คบใใใใ `C:\ghcup\logs` ใ่ฆใฆใฟใ  

ghcup.log:  

```plaintext
Debug: Identified Platform as: Windows
Debug: last access was 93.3364476s ago, cache interval is 300s
Debug: Decoding yaml at: C:\ghcup\cache\ghcup-0.0.7.yaml
Info: verifying digest of: gs.exe
Error: Both installation and setting the tool failed. Install error was: Unable to find a download for the requested version/distro. 
Set error was: The version 9.4.4 of the tool cabal is not installed.
Error: Also check the logs in C:\ghcup\logs

```

`9.4.4` ใจใใใใผใธใงใณใฏ็กใ๏ผ  

ใจใใใใ้ใ็ตๆใๆๅพใใฆใ้้?ใงใณใใณใใๆ้ตใใฆใใ๏ผโปๆณจ๏ผๅใใใจใ็นฐใ่ฟใใฆ้ใ็ตๆใๆฑใใใฎใฏ็ไบบใ?ใจใขใคใณใทใฅใฟใคใณใฏ่จใฃใใใใใใใใซๅฃใ๏ผ  

```shell
ghcup install stack 2.9.3
[ Info  ] verifying digest of: gs.exe
[ Warn  ] stack-2.9.3 is already installed; if you really want to reinstall it, you may want to run 'ghcup install cabal --force 2.9.3'
```

```shell
ghcup install cabal 3.8.1.0
[ Info  ] verifying digest of: gs.exe
[ Warn  ] cabal-3.8.1.0 is already installed; if you really want to reinstall it, you may want to run 'ghcup install cabal --force 3.8.1.0'
```

```shell
ghcup install ghc 9.4.4
[ Info  ] verifying digest of: gs.exe
[ Warn  ] ghc-9.4.4 is already installed; if you really want to reinstall it, you may want to run 'ghcup install cabal --force 9.4.4'
```

```shell
ghc --version
'ghc' ใฏใๅ้จใณใใณใใพใใฏๅค้จใณใใณใใ
ๆไฝๅฏ่ฝใชใใญใฐใฉใ?ใพใใฏใใใ ใใกใคใซใจใใฆ่ช่ญใใใฆใใพใใใ
```

ใขใคใณใทใฅใฟใคใณใงใ้ง็ฎใ  

ใ?ใฃใใใในใ้ใฃใฆใใชใใฎใงใฏใชใใ๏ผ  
ใใใใในใ่ฟฝๅ?ใใใ  

๐ `C:\ghcup\ghc\9.4.4\bin\ghc.exe` ใฏๆใใ  
ใใใง  

```shell
echo %PATH%
C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;C:\Program Files\Git\cmd;C:\Program Files (x86)\PostgreSQL\10\bin;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\PostgreSQL\11\bin;C:\Program Files\Microsoft SQL Server\130\Tools\Binn\;C:\Program Files\ninja\bin;C:\Program Files\CMake\bin;C:\Users\ใใใงใ\go\bin;C:\Program Files\PuTTY\;C:\Program Files\nodejs\;C:\Program Files\Amazon\AWSCLIV2\;C:\Program Files\Docker\Docker\resources\bin;C:\ProgramData\DockerDesktop\version-bin;C:\Program Files\Go\bin;C:\Program Files\dotnet\;C:\Users\ใใใงใ\AppData\Local\Programs\Eclipse Adoptium\jdk-11.0.13.8-hotspot\bin;C:\Ruby27-x64\bin;C:\Users\ใใใงใ\.cargo\bin;C:\Users\ใใใงใ\AppData\Local\Microsoft\WindowsApps;C:\Users\ใใใงใ\AppData\Local\GitHubDesktop\bin;C:\Users\ใใใงใ\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\ใใใงใ\AppData\Local\Microsoft\WindowsApps;C:\Users\ใใใงใ\.dotnet\tools;C:\Users\ใใใงใ\.dotnet\tools;C:\Program Files (x86)\GnuWin32\bin;C:\Users\ใใใงใ\AppData\Roaming\npm;C:\Program Files\Graphviz\bin;C:\Users\ใใใงใ\go\bin;C:\ghcup\bin
```

```shell
set PATH=%PATH%;C:\ghcup\ghc\9.4.4\bin
```

```shell
echo %PATH%
C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;C:\Program Files\Git\cmd;C:\Program Files (x86)\PostgreSQL\10\bin;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\PostgreSQL\11\bin;C:\Program Files\Microsoft SQL Server\130\Tools\Binn\;C:\Program Files\ninja\bin;C:\Program Files\CMake\bin;C:\Users\ใใใงใ\go\bin;C:\Program Files\PuTTY\;C:\Program Files\nodejs\;C:\Program Files\Amazon\AWSCLIV2\;C:\Program Files\Docker\Docker\resources\bin;C:\ProgramData\DockerDesktop\version-bin;C:\Program Files\Go\bin;C:\Program Files\dotnet\;C:\Users\ใใใงใ\AppData\Local\Programs\Eclipse Adoptium\jdk-11.0.13.8-hotspot\bin;C:\Ruby27-x64\bin;C:\Users\ใใใงใ\.cargo\bin;C:\Users\ใใใงใ\AppData\Local\Microsoft\WindowsApps;C:\Users\ใใใงใ\AppData\Local\GitHubDesktop\bin;C:\Users\ใใใงใ\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\ใใใงใ\AppData\Local\Microsoft\WindowsApps;C:\Users\ใใใงใ\.dotnet\tools;C:\Users\ใใใงใ\.dotnet\tools;C:\Program Files (x86)\GnuWin32\bin;C:\Users\ใใใงใ\AppData\Roaming\npm;C:\Program Files\Graphviz\bin;C:\Users\ใใใงใ\go\bin;C:\ghcup\bin;C:\ghcup\ghc\9.4.4\bin
```

```shell
ghc --version
The Glorious Glasgow Haskell Compilation System, version 9.4.4
```

ใใใใใใ?ใใใจใฏๆใใใใชใใงใในใใใ้ใใฆใใใชใใฎใ?ใใ  

ไฝใ่จใฃใฆใใใๅใใใชใใใใใใชใใใ  
Windows ใฎใฟในใฏใใผใฎ `็ฐใฎๅญ` ใฟใใใชใขใคใณใณใใ `่จญๅฎ` ็ป้ขใๅบใใ ๐`่จญๅฎใฎๆค็ดข` ใธ `env` ใจๆ้ตใใ  
`ใทในใใ?็ฐๅขๅคๆฐใฎ่จญๅฎ` ใชใณใฏใใฏใชใใฏใใ`็ฐๅขๅคๆฐ` ใใฟใณใๆผไธใใ`ใทในใใ?็ฐๅขๅคๆฐ(S)` ใฎ `Path` ๅคๆฐใ้ธๆใใฆ `็ทจ้` ใใฟใณใๆผไธใใ  
`ๆฐ่ฆ`ใใฟใณใๆผไธใใใจใซใใ `C:\ghcup\ghc\9.4.4\bin` ใ่ฟฝๅ?ใใใใใจใฏ `OK` ใใฟใณใๆผไธใใชใใ่จญๅฎใฆใฃใณใใฆใ้ใใฆใใ  

๐ใใใฆไปฅไธใฎใณใใณใใๆ้ต  

```shell
ghc hello.hs
[1 of 2] Compiling Main             ( hello.hs, hello.o )
[2 of 2] Linking hello.exe
```

ใณใณใใคใซใงใใ  

๐ใใใซไปฅไธใฎใณใใณใใๆ้ต

```shell
./hello
'.' ใฏใๅ้จใณใใณใใพใใฏๅค้จใณใใณใใ
ๆไฝๅฏ่ฝใชใใญใฐใฉใ?ใพใใฏใใใ ใใกใคใซใจใใฆ่ช่ญใใใฆใใพใใใ
```

ใณใใณใใใญใณใใใซใชใฃใฆใใใ Powershell ใซๅคๆด  

```shell
./hello
Hello, Haskell!
```

ใงใใ  

๐2023-01-09 mon (ๆไบบใฎๆฅ) 23:31  

ใณใณใใคใซใจๅฎ่กใไธๅบฆใซใใใซใฏใ `runghc hello.hs` ใจๆ้ตใใใฐใใใใใ  

```shell
runghc hello.hs
runghc : ็จ่ช 'runghc' ใฏใใณใใณใใฌใใใ้ขๆฐใในใฏใชใใ ใใกใคใซใใพใใฏๆไฝๅฏ่ฝใชใใญใฐใฉใ?ใฎๅๅใจใใฆ่ช่ญใใใพใใใๅๅใๆญฃใใ่จ่ฟฐใใใฆใใใใจใ็ขบ่ชใใใในใๅซใพใใฆใใๅ?ดๅใฏใใฎใในใๆญฃใ
ใใใจใ็ขบ่ชใใฆใใใๅ่ฉฆ่กใใฆใใ?ใใใ
็บ็ๅ?ดๆ ่ก:1 ๆๅญ:1
+ runghc hello.hs
+ ~~~~~~
    + CategoryInfo          : ObjectNotFound: (runghc:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

๏ผ  

่จญๅฎใใ Path ็ฐๅขๅคๆฐใ Visual Studio Code ใ่ช่ญใใฆใใชใใใใชใฎใงใ Visual Studio Code ใๅ่ตทๅ  

```shell
runghc hello.hs
Hello, Haskell!
```

ใใใ `runghc` ไฝฟใใ  

๐2023-01-09 mon (ๆไบบใฎๆฅ) 23:47  
