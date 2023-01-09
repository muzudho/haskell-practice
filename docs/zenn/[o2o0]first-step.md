📅2023-01-09 mon (成人の日) 22:30  

とりあえず 公式サイトを読み進める  

📖[First steps](https://www.haskell.org/ghcup/steps/)  

👇とにかく以下のファイルを作る  

hello.hs:  

```haskell
main = putStrLn "Hello, Haskell!"
```

👇そして以下のコマンドを打鍵  

```shell
ghc hello.hs
```

Output:  

```shell
[1 of 1] Compiling Main             ( hello.hs, hello.o )
Assembler messages:
Error: can't open C:\\Users\\むずでょ\\AppData\\Local\\Temp\\ghc19776_0\\ghc_2.s for reading: No such file or directory
`gcc.exe' failed in phase `Assembler'. (Exit code: 1)
```

エラーが出た。  
`C:\\Users\\むずでょ\\AppData\\Local\\Temp\\` までは有り、 `ghc19776_0` は無い。  
ググる  

🔍````gcc.exe' failed in phase `Assembler'. (Exit code: 1)```  

📖['gcc.exe' failed in phase 'Assembler' while running Haskell code)](https://stackoverflow.com/questions/65051731/gcc-exe-failed-in-phase-assembler-while-running-haskell-code)  
📖[gcc.exe' failed in phase Linker'. (Exit code: 1) #8560](https://github.com/haskell/cabal/issues/8560)  

👆 `ghcup` にバグがあるとのこと  

👇 以下のコマンドを試す  

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

再インストールできたようなので Visual Studio Code を再起動  

👇そして以下のコマンドを打鍵  

```shell
ghc --version
'ghc' は、内部コマンドまたは外部コマンド、
操作可能なプログラムまたはバッチ ファイルとして認識されていません。
```

？  

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

`ghc 9.4.4` がある？  
じゃあ、それインストールする  

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

再インストールできたようなので Visual Studio Code を再起動  

👇そして以下のコマンドを打鍵  

```shell
ghc --version
'ghc' は、内部コマンドまたは外部コマンド、
操作可能なプログラムまたはバッチ ファイルとして認識されていません。
```

？  

じゃあ `cabal` と `stack` のアップグレードを試していく  

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

とりあえず Visual Studio Code を再起動  

👇そして以下のコマンドを打鍵  

```shell
ghc --version
'ghc' は、内部コマンドまたは外部コマンド、
操作可能なプログラムまたはバッチ ファイルとして認識されていません。
```

じゃあ、次のコマンドを打鍵  

```shell
ghcup install cabal --force 9.4.4
[ Info  ] verifying digest of: gs.exe
[ Error ] Both installation and setting the tool failed. Install error was: Unable to find a download for the requested version/distro. 
[ ...   ] Set error was: The version 9.4.4 of the tool cabal is not installed.
[ Error ] Also check the logs in C:\ghcup\logs
```

ログの場所が示された。 `C:\ghcup\logs` を見てみる  

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

`9.4.4` というバージョンは無い？  

とりあえず違う結果を期待して　逆順でコマンドを打鍵していく（※注：同じことを繰り返して違う結果を求めるのは狂人だとアインシュタインは言ったらしい。それに倣う）  

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
'ghc' は、内部コマンドまたは外部コマンド、
操作可能なプログラムまたはバッチ ファイルとして認識されていません。
```

アインシュタインでも駄目。  

だったらパスが通っていないのではないか？  
じゃあパスを追加する。  

📄 `C:\ghcup\ghc\9.4.4\bin\ghc.exe` は有る。  
そこで  

```shell
echo %PATH%
C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;C:\Program Files\Git\cmd;C:\Program Files (x86)\PostgreSQL\10\bin;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\PostgreSQL\11\bin;C:\Program Files\Microsoft SQL Server\130\Tools\Binn\;C:\Program Files\ninja\bin;C:\Program Files\CMake\bin;C:\Users\むずでょ\go\bin;C:\Program Files\PuTTY\;C:\Program Files\nodejs\;C:\Program Files\Amazon\AWSCLIV2\;C:\Program Files\Docker\Docker\resources\bin;C:\ProgramData\DockerDesktop\version-bin;C:\Program Files\Go\bin;C:\Program Files\dotnet\;C:\Users\むずでょ\AppData\Local\Programs\Eclipse Adoptium\jdk-11.0.13.8-hotspot\bin;C:\Ruby27-x64\bin;C:\Users\むずでょ\.cargo\bin;C:\Users\むずでょ\AppData\Local\Microsoft\WindowsApps;C:\Users\むずでょ\AppData\Local\GitHubDesktop\bin;C:\Users\むずでょ\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\むずでょ\AppData\Local\Microsoft\WindowsApps;C:\Users\むずでょ\.dotnet\tools;C:\Users\むずでょ\.dotnet\tools;C:\Program Files (x86)\GnuWin32\bin;C:\Users\むずでょ\AppData\Roaming\npm;C:\Program Files\Graphviz\bin;C:\Users\むずでょ\go\bin;C:\ghcup\bin
```

```shell
set PATH=%PATH%;C:\ghcup\ghc\9.4.4\bin
```

```shell
echo %PATH%
C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;C:\Program Files\Git\cmd;C:\Program Files (x86)\PostgreSQL\10\bin;C:\Program Files\NVIDIA Corporation\NVIDIA NvDLISR;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\PostgreSQL\11\bin;C:\Program Files\Microsoft SQL Server\130\Tools\Binn\;C:\Program Files\ninja\bin;C:\Program Files\CMake\bin;C:\Users\むずでょ\go\bin;C:\Program Files\PuTTY\;C:\Program Files\nodejs\;C:\Program Files\Amazon\AWSCLIV2\;C:\Program Files\Docker\Docker\resources\bin;C:\ProgramData\DockerDesktop\version-bin;C:\Program Files\Go\bin;C:\Program Files\dotnet\;C:\Users\むずでょ\AppData\Local\Programs\Eclipse Adoptium\jdk-11.0.13.8-hotspot\bin;C:\Ruby27-x64\bin;C:\Users\むずでょ\.cargo\bin;C:\Users\むずでょ\AppData\Local\Microsoft\WindowsApps;C:\Users\むずでょ\AppData\Local\GitHubDesktop\bin;C:\Users\むずでょ\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\むずでょ\AppData\Local\Microsoft\WindowsApps;C:\Users\むずでょ\.dotnet\tools;C:\Users\むずでょ\.dotnet\tools;C:\Program Files (x86)\GnuWin32\bin;C:\Users\むずでょ\AppData\Roaming\npm;C:\Program Files\Graphviz\bin;C:\Users\むずでょ\go\bin;C:\ghcup\bin;C:\ghcup\ghc\9.4.4\bin
```

```shell
ghc --version
The Glorious Glasgow Haskell Compilation System, version 9.4.4
```

そりゃそうだろうとは思うが、なんでパスぐらい通してくれないのだろう  

何を言っているか分からないかもしれないが、  
Windows のタスクバーの `田の字` みたいなアイコンから `設定` 画面を出し、 🔍`設定の検索` へ `env` と打鍵し、  
`システム環境変数の設定` リンクをクリックし、`環境変数` ボタンを押下し、`システム環境変数(S)` の `Path` 変数を選択して `編集` ボタンを押下し、  
`新規`ボタンを押下し、とにかく `C:\ghcup\ghc\9.4.4\bin` を追加する。あとは `OK` ボタンを押下しながら設定ウィンドウを閉じていく  

👇そして以下のコマンドを打鍵  

```shell
ghc hello.hs
[1 of 2] Compiling Main             ( hello.hs, hello.o )
[2 of 2] Linking hello.exe
```

コンパイルでけた  

👇さらに以下のコマンドを打鍵

```shell
./hello
'.' は、内部コマンドまたは外部コマンド、
操作可能なプログラムまたはバッチ ファイルとして認識されていません。
```

コマンドプロンプトになっていた。 Powershell に変更  

```shell
./hello
Hello, Haskell!
```

でけた  

📅2023-01-09 mon (成人の日) 23:31  

コンパイルと実行を一度にするには、 `runghc hello.hs` と打鍵すればいいらしい  

```shell
runghc hello.hs
runghc : 用語 'runghc' は、コマンドレット、関数、スクリプト ファイル、または操作可能なプログラムの名前として認識されません。名前が正しく記述されていることを確認し、パスが含まれている場合はそのパスが正し
いことを確認してから、再試行してください。
発生場所 行:1 文字:1
+ runghc hello.hs
+ ~~~~~~
    + CategoryInfo          : ObjectNotFound: (runghc:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

？  

設定した Path 環境変数を Visual Studio Code が認識していないようなので、 Visual Studio Code を再起動  

```shell
runghc hello.hs
Hello, Haskell!
```

じゃあ `runghc` 使おう  

📅2023-01-09 mon (成人の日) 23:47  
