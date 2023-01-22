# 📅2023-01-22 sun 21:34 start

他の文章を読んでみる  

📖 [Install or upgrade](http://docs.haskellstack.org/en/stable/install_and_upgrade/)  

`Windows インストーラー` を使ってみる  

Visual Studio Code を再起動  

Input:  

```shell
stack install
```

Output:  

```plaintext
realgcc.exe: fatal error: cannot execute 'cc1': CreateProcess: No such file or directory
compilation terminated.

<no location info>: error:
    output was redirected with -o, but no output will be generated
because there is no StackSetupShim module.

C:\sr\setup-exe-src\setup-shim-sDt42OhJ.hs:1:1: error:
    `gcc.exe' failed in phase `C pre-processor'. (Exit code: 1)
  |
1 | {-# LANGUAGE CPP            #-}
  | ^

Error: [S-6374]
       While building simple Setup.hs (scroll up to its section to see the error) using:
       C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5\bin\ghc-9.2.5.exe -rtsopts -threaded -clear-package-db -global-package-db -hide-all-packages -package base -main-is StackSetupShim.mainOverride -package Cabal-3.6.3.0 C:\sr\setup-exe-src\setup-sDt42OhJ.hs C:\sr\setup-exe-src\setup-shim-sDt42OhJ.hs -o C:\sr\setup-exe-cache\x86_64-windows\tmp-Cabal-simple_sDt42OhJ_3.6.3.0_ghc-9.2.5.exe
       Process exited with code: ExitFailure 1
```

👆 似たようなエラー  

他の文章を読んでみる  

📖 [Haskell 環境準備 (for Windows10)](https://qiita.com/taashi/items/956507a64892504cd05f)  

stack のインストール  
📖 [commercialhaskell / stack](https://github.com/commercialhaskell/stack/releases)  
から、  
`stack-2.9.3-windows-x86_64-installer.exe` を選んでダウンロード、インストール  

Visual Studio Code を再起動  

Input:  

```shell
stack setup
```

Output:  

```plaintext
Error: [S-5159]
The GHC located at C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5\bin\ghc-9.2.5.exe failed to compile a sanity check. Please see:

    http://docs.haskellstack.org/en/stable/install_and_upgrade/

for more information. Exception was:
Received ExitFailure 1 when running
Raw command: "C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\bin\\ghc-9.2.5.exe" "C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Temp\\stack-sanity-check-4ccd218b6076b159\\Main.hs" -no-user-package-db
Run from: C:\Users\むずでょ\AppData\Local\Temp\stack-sanity-check-4ccd218b6076b159\
Standard output:

[1 of 1] Compiling Main             ( C:\Users\stack: <stderr>: commitAndReleaseBuffer: invalid argument (invalid character)
```

👆 似たようなエラー  

Input:  

```shell
stack ghci
```

Output:  

```plaintext
Using main module: 1. Package `sample' component sample:exe:sample-exe with main-is file: C:\Users\むずでょ\Documents\GitHub\haskell-practice\haskell-project\sample\app\Main.hs
realgcc.exe: fatal error: cannot execute 'cc1': CreateProcess: No such file or directory
compilation terminated.

<no location info>: error:
    output was redirected with -o, but no output will be generated
because there is no StackSetupShim module.

C:\sr\setup-exe-src\setup-shim-sDt42OhJ.hs:1:1: error:
    `gcc.exe' failed in phase `C pre-processor'. (Exit code: 1)
  |
1 | {-# LANGUAGE CPP            #-}
  | ^

Error: SetupHsBuildFailure (ExitFailure 1) Nothing "C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\bin\\ghc-9.2.5.exe" ["-rtsopts","-threaded","-clear-package-db","-global-package-db","-hide-all-packages","-package","base","-main-is","StackSetupShim.mainOverride","-package","Cabal-3.6.3.0","C:\\sr\\setup-exe-src\\setup-sDt42OhJ.hs","C:\\sr\\setup-exe-src\\setup-shim-sDt42OhJ.hs","-o","C:\\sr\\setup-exe-cache\\x86_64-windows\\tmp-Cabal-simple_sDt42OhJ_3.6.3.0_ghc-9.2.5.exe"] Nothing []

Warning: Build failed, but trying to launch GHCi anyway
The following GHC options are incompatible with GHCi and have not been passed to it: -threaded
Configuring GHCi with the following packages: sample

Warning: Didn't find expected autogen file: C:\Users\むずでょ\Documents\GitHub\haskell-practice\haskell-project\sample\.stack-work\dist\8a54c84f\build\autogen\cabal_macros.h

Warning: Didn't find expected autogen file: C:\Users\むずでょ\Documents\GitHub\haskell-practice\haskell-project\sample\.stack-work\dist\8a54c84f\build\sample-exe\autogen\cabal_macros.h
GHCi, version 9.2.5: https://www.haskell.org/ghc/  :? for help
File C:\Users\繧縺壹〒繧ⅨDocuments\GitHub\haskell-practice\haskell-project\sample\app\Main.hs not found
[1 of 1] Compiling Lib              ( C:\Users\むずでょ\Documents\GitHub\haskell-practice\haskell-project\sample\src\Lib.hs, interpreted )
Ok, one module loaded.
Loaded GHCi configuration from C:\Users\むずでょ\AppData\Local\Temp\haskell-stack-ghci\32d4d4d9\ghci-script
ghci> 
```

👆 似たようなエラー  

続けて入力  

Input:  

```shell
foldl1 (+) [1..10]
```

Output:  

```plaintext
<interactive>:1:1: warning: [-Wtype-defaults]
    ? Defaulting the following constraints to type ‘Integer’
        (Show a0) arising from a use of ‘print’ at <interactive>:1:1-18
        (Num a0) arising from a use of ‘it’ at <interactive>:1:1-18
        (Enum a0) arising from a use of ‘it’ at <interactive>:1:1-18
    ? In a stmt of an interactive GHCi command: print it
55
ghci> 
```

👆 何かエラー  

続けて入力  

Input:  

```shell
:q
```

Output:  

```plaintext
Leaving GHCi.
```

📅2023-01-22 sun 22:02 end  

# 📅2023-01-22 sun 22:04 start

他の文章を読んでみる  

📖 [WindowsでHaskellを扱う時によく遭遇するエラーと対処法](https://haskell.jp/blog/posts/2017/windows-gotchas.html)  

Input:  

```shell
chcp 65001
stack exec -- site rebuild
```

Output:  

```plaintext
Executable named site not found on path: [".","C:\\Users\\\12416\12378\12391\12423\\Documents\\GitHub\\haskell-practice\\.stack-work\\install\\b27699ae\\bin","C:\\sr\\snapshots\\2363ceba\\bin","C:\\sr\\compiler-tools\\x86_64-windows\\ghc-9.2.5\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\mingw\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\msys2-20221216\\mingw64\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\msys2-20221216\\usr\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\msys2-20221216\\usr\\local\\bin","C:\\Windows\\system32","C:\\Windows","C:\\Windows\\System32\\Wbem","C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\","C:\\Windows\\System32\\OpenSSH\\","C:\\Program Files (x86)\\NVIDIA Corporation\\PhysX\\Common","C:\\Program Files\\Git\\cmd","C:\\Program Files (x86)\\PostgreSQL\\10\\bin","C:\\Program Files\\NVIDIA Corporation\\NVIDIA NvDLISR","C:\\WINDOWS\\system32","C:\\WINDOWS","C:\\WINDOWS\\System32\\Wbem","C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\","C:\\WINDOWS\\System32\\OpenSSH\\","C:\\Program Files\\PostgreSQL\\11\\bin","C:\\Program Files\\Microsoft SQL Server\\130\\Tools\\Binn\\","C:\\Program Files\\ninja\\bin","C:\\Program Files\\CMake\\bin","C:\\Users\\\12416\12378\12391\12423\\go\\bin","C:\\Program Files\\PuTTY\\","C:\\Program Files\\nodejs\\","C:\\Program Files\\Amazon\\AWSCLIV2\\","C:\\Program Files\\Docker\\Docker\\resources\\bin","C:\\ProgramData\\DockerDesktop\\version-bin","C:\\Program Files\\Go\\bin","C:\\Program Files\\dotnet\\","C:\\ghcup\\ghc\\9.4.4\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Roaming\\local\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\Eclipse Adoptium\\jdk-11.0.13.8-hotspot\\bin","C:\\Ruby27-x64\\bin","C:\\Users\\\12416\12378\12391\12423\\.cargo\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Microsoft\\WindowsApps","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\GitHubDesktop\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\Microsoft VS Code\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Microsoft\\WindowsApps","C:\\Users\\\12416\12378\12391\12423\\.dotnet\\tools","C:\\Users\\\12416\12378\12391\12423\\.dotnet\\tools","C:\\Program Files (x86)\\GnuWin32\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Roaming\\npm","C:\\Program Files\\Graphviz\\bin","C:\\Users\\\12416\12378\12391\12423\\go\\bin","C:\\ghcup\\bin"]
```

👆 動いてなさげ  

👇 元に戻すなら  

Input:  

```shell
chcp 932
stack exec -- site rebuild
```

Output:  

```plaintext
Executable named site not found on path: [".","C:\\Users\\\12416\12378\12391\12423\\Documents\\GitHub\\haskell-practice\\.stack-work\\install\\b27699ae\\bin","C:\\sr\\snapshots\\2363ceba\\bin","C:\\sr\\compiler-tools\\x86_64-windows\\ghc-9.2.5\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\mingw\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\msys2-20221216\\mingw64\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\msys2-20221216\\usr\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\msys2-20221216\\usr\\local\\bin","C:\\Windows\\system32","C:\\Windows","C:\\Windows\\System32\\Wbem","C:\\Windows\\System32\\WindowsPowerShell\\v1.0\\","C:\\Windows\\System32\\OpenSSH\\","C:\\Program Files (x86)\\NVIDIA Corporation\\PhysX\\Common","C:\\Program Files\\Git\\cmd","C:\\Program Files (x86)\\PostgreSQL\\10\\bin","C:\\Program Files\\NVIDIA Corporation\\NVIDIA NvDLISR","C:\\WINDOWS\\system32","C:\\WINDOWS","C:\\WINDOWS\\System32\\Wbem","C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\","C:\\WINDOWS\\System32\\OpenSSH\\","C:\\Program Files\\PostgreSQL\\11\\bin","C:\\Program Files\\Microsoft SQL Server\\130\\Tools\\Binn\\","C:\\Program Files\\ninja\\bin","C:\\Program Files\\CMake\\bin","C:\\Users\\\12416\12378\12391\12423\\go\\bin","C:\\Program Files\\PuTTY\\","C:\\Program Files\\nodejs\\","C:\\Program Files\\Amazon\\AWSCLIV2\\","C:\\Program Files\\Docker\\Docker\\resources\\bin","C:\\ProgramData\\DockerDesktop\\version-bin","C:\\Program Files\\Go\\bin","C:\\Program Files\\dotnet\\","C:\\ghcup\\ghc\\9.4.4\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Roaming\\local\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\Eclipse Adoptium\\jdk-11.0.13.8-hotspot\\bin","C:\\Ruby27-x64\\bin","C:\\Users\\\12416\12378\12391\12423\\.cargo\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Microsoft\\WindowsApps","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\GitHubDesktop\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\Microsoft VS Code\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Microsoft\\WindowsApps","C:\\Users\\\12416\12378\12391\12423\\.dotnet\\tools","C:\\Users\\\12416\12378\12391\12423\\.dotnet\\tools","C:\\Program Files (x86)\\GnuWin32\\bin","C:\\Users\\\12416\12378\12391\12423\\AppData\\Roaming\\npm","C:\\Program Files\\Graphviz\\bin","C:\\Users\\\12416\12378\12391\12423\\go\\bin","C:\\ghcup\\bin"]
```

👆 動いてなさげ  

他の文章を読んでみる  

📖 [windowsでHaskellのIOまわりで日本語を文字化けなく表示させる方法](https://shokos.hatenablog.com/entry/20111109/1320828466)  

Input:  

```shell
cabal install utf8-string
```

Output:  

```plaintext
Resolving dependencies...
Build profile: -w ghc-9.4.4 -O1
In order, the following will be built (use -v for more details):
 - utf8-string-1.0.2 (lib) (requires download & build)
Downloading  utf8-string-1.0.2
Downloaded   utf8-string-1.0.2
Starting     utf8-string-1.0.2 (lib)
Building     utf8-string-1.0.2 (lib)
Installing   utf8-string-1.0.2 (lib)
Completed    utf8-string-1.0.2 (lib)
Warning:
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@ WARNING: Installation might not be completed as desired! @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
The command "cabal install [TARGETS]" doesn't expose libraries.
* You might have wanted to add them as dependencies to your package. In this
case add "utf8-string" to the build-depends field(s) of your package's .cabal
file.
* You might have wanted to add them to a GHC environment. In this case use
"cabal install --lib utf8-string". The "--lib" flag is provisional: see
https://github.com/haskell/cabal/issues/6481 for more information.
```

👆 警告が出た  

Input:  

```shell
cabal install --lib utf8-string
```

Output:  

```plaintext
Resolving dependencies...
Up to date
```

👆 よく分からない  

📅2023-01-22 sun 22:20 end  
