๐2023-01-09 mon (ๆไบบใฎๆฅ) 23:50  

โช[ไฝๆฅญ็จBGM](https://www.youtube.com/watch?v=74EApHZde-8)  

๐[First steps](https://www.haskell.org/ghcup/steps/)  

๐ ๆๅณใฏๅใใใชใใใใณใณใใคใซใจใฉใผใๅบใใณใใณใใๆธใใฆใใใฎใง็ไผผใใ  

```shell
ghc -Wall hello.hs -fforce-recomp
[1 of 2] Compiling Main             ( hello.hs, hello.o )

hello.hs:1:1: warning: [-Wmissing-signatures]
    Top-level binding with no type signature: main :: IO ()
  |
1 | main = putStrLn "Hello, Haskell!"
  | ^^^^
[2 of 2] Linking hello.exe [Objects changed]
```

ใใใฆ `hello.hs` ใไฟฎๆญฃใใใใจใใใใจใใใ  

hello.hs:  

```shell
main :: IO ()
main = putStrLn "Hello, world!"
```

๐ ๅๅบฆใใณใใณใใๆ้ต  

```shell
ghc -Wall hello.hs -fforce-recomp
[1 of 2] Compiling Main             ( hello.hs, hello.o )
[2 of 2] Linking hello.exe [Objects changed]
```

ใจใฉใผใฏๅบใชใใฃใใใไฝใใใฃใฆใใใฎใๅใใใชใ  

# REPL

`ghci` ใจใใใณใใณใใง REPL ใงใใใจใใ่ฉฑใใใใใ  
ใใฃในใใฌใคใฎใกใใปใผใธใ่ฆใชใใใใญใผใใผใใๆ้ตใใใฎใ็นฐใ่ฟใใใคใ ใ  
ใคใณใฟใผใใชใฟใผๅใฎใใญใฐใฉใใณใฐ่จ่ชใงใงใใใใคใ   

ใใฃใฆใฟใใ  

```shell
ghci
GHCi, version 9.4.4: https://www.haskell.org/ghc/  :? for help
ghci>
```

```shell
1 + 1
2
ghci>
```

```shell
putStrLn "Hello, world!"
Hello, world!
ghci>
```

REPL ใงใใฆใ  

ใจใใใง ่ทๅ ดใงใใงใใพใใใใจๅ ฑๅใใใฆๆๅบใใใใจใซใใฐใใใใจ ไธ้ทใใใใงใใใฃใฆ่จใฃใใใญ๏ผใใจ่ฟใใใใใจใใใฃใใฎใง ็ฌใ่จใฏใใงใใใใจใ่ใใใใใงใใใใจ่จใใใใซใใฆใใ  

```shell
double x = x + x
ghci> double 2
4
```

๐ ๅใใใใใใ Haskell ใฎๆธใๆนใใใ  
ใใใฏใฉใ ใๅผใฎๆธใๆนใใใฆใใใจ่ใใใจ `double` ใฏ ใใ ใฎๅๅใงใ  
๏ผ่ก็ฎใฏ `double` ใซ 2 ใๆธกใใใจใใๅฝไปคใงใ  
๏ผ่ก็ฎใฏ `double` ใซๆธกใใใใใฎใ x ใงๅใๅใฃใฆใ `x + x` ใใใใใจใใใใจใชใฎใ ใใ  

```shell
ghci> :{
ghci| map f list =
ghci|     case list of
ghci|         [] -> []
ghci|         x : xs -> f x : map f xs
ghci| :}
ghci> map (+1) [1, 2, 3]
[2,3,4]
ghci>
```

๐ ไฝใใฃใฆใใใใใฃใฑใๅใใใ  
ๅใซ้ฒใ  

```shell
ghci> :load hello.hs
Ok, one module loaded.
ghci> main
Hello, world!
ghci>
```

๐ `:load` ใงใใใกใคใซใ่ชญ่พผใใฎใใใใใชใ  

```shell
ghci> import Data.Bits
ghci> shiftL 32 1
64
ghci> clearBit 33 0
32
```

๐ `Data.Bits` ใจใใไฝใใ่ชญ่พผใใงใ32 ใ 1 bit ่ซ็ๅทฆใทใใๆผ็ฎใใใฆ 64 ใซใใใฎใ ใใใ  
`clearBit` ใฏ 100001 ใฎๅณ็ซฏใฎใใใใ 0 ใงไธๆธใใใฆ 100000 ใซใใใฎใใใใใชใใ็ฅใใใใฉ  

```shell
:type pubStrLn

<interactive>:1:1: error:
    Variable not in scope: pubStrLn
    Suggested fix: Perhaps use โputStrLnโ (imported from Prelude)
```

๐ ใใๅใใใใๅผทๅถ็ตไบใฎๆนๆณใๅใใใ  

```shell
Leaving GHCi.
```

ใใใใ่ฉฆใใจ `[Ctrl] + [D]` ใงๆญขใพใฃใ  

```shell
C:\Users\ใใใงใ\Documents\GitHub\haskell-practice>ghci
GHCi, version 9.4.4: https://www.haskell.org/ghc/  :? for help
ghci> :type putStrLn 
putStrLn :: String -> IO ()
ghci> quit

<interactive>:2:1: error:
    Variable not in scope: quit
    Suggested fix: Perhaps use โquotโ (imported from Prelude)
ghci> :quit
Leaving GHCi.
```

๐ ้ ญใฎใณใญใณ `:` ใๅฟใใใใ  

ใพใ ็ถใใฏ้ทใใใ ใใใใง็ตใใ  

๐2023-01-10 tue 00:21 end  

# ๐2023-01-22 sun 19:27 start

โช[ไฝๆฅญ็จBGM](https://www.youtube.com/watch?v=oSBlfiO7jwM)  

`Using external packages in ghci` ใฎ็ฏใ่ชญใใ GHCI ใฏใณใณใใคใฉใไฝใใ ใใใใ  
ใณใณใใคใฉใงใๅค้จใใใฑใผใธใไฝฟใๆนๆณใ ใใใ  

`cabal` ใจ `stack` ใจใใใฎใใใฃใฆใใใใไฝฟใฃใฆใคใณในใใผใซใงใใใใใใ  
ใจใซใใใณใใณใใๅฉใใฆใฟใใ  

Input:  

```shell
cabal repl --build-depends async,say
```

Output:  

```plaintext
Resolving dependencies...
Build profile: -w ghc-9.4.4 -O1
In order, the following will be built (use -v for more details):
 - hashable-1.4.2.0 (lib) (requires download & build)
 - say-0.1.0.1 (lib) (requires download & build)
 - async-2.2.4 (lib) (requires download & build)
 - fake-package-0 (lib) (first run)
Downloading  hashable-1.4.2.0
Downloaded   hashable-1.4.2.0
Downloading  async-2.2.4
Starting     hashable-1.4.2.0 (lib)
Downloaded   async-2.2.4
Downloading  say-0.1.0.1
Downloaded   say-0.1.0.1
Starting     say-0.1.0.1 (lib)
Building     say-0.1.0.1 (lib)
Building     hashable-1.4.2.0 (lib)
Installing   say-0.1.0.1 (lib)
Completed    say-0.1.0.1 (lib)
Installing   hashable-1.4.2.0 (lib)
Completed    hashable-1.4.2.0 (lib)
Starting     async-2.2.4 (lib)
Building     async-2.2.4 (lib)
Installing   async-2.2.4 (lib)
Completed    async-2.2.4 (lib)
Configuring library for fake-package-0..
Warning: No exposed modules
GHCi, version 9.4.4: https://www.haskell.org/ghc/  :? for help
Loaded GHCi configuration from C:\\Users\\ใใใงใ\\AppData\\Local\\Temp\\cabal-repl.-25248\\setcwd.ghci
ghci>
```

๐ ไฝใใฏๅใใใชใใ ไฝใใใใใใใ ใ  
`[Ctrl]+[D]` ใงๆใใ  

Input:  

```shell
stack exec --package async --package say -- ghci
```

Output:  

```plaintext
Writing implicit global project config file to: C:\Users\ใใใงใ\AppData\Roaming\stack\global-project\stack.yaml
Note: You can change the snapshot via the resolver field there.
Using latest snapshot resolver: lts-20.8
Downloaded msys2-20221216.
Downloaded 7z.dll.
Downloaded 7z.exe.
Decompressing msys2-20221216.tar.xz...

7-Zip 22.01 (x64) : Copyright (c) 1999-2022 Igor Pavlov : 2022-07-15

Scanning the drive for archives:
1 file, 77407912 bytes (74 MiB)

Extracting archive: C:\Users\ใใใงใ\AppData\Local\Programs\stack\x86_64-windows\msys2-20221216.tar.xz
--
Path = C:\Users\ใใใงใ\AppData\Local\Programs\stack\x86_64-windows\msys2-20221216.tar.xz
Type = xz
Physical Size = 77407912
Method = LZMA2:24 CRC32
Streams = 1
Blocks = 6
Cluster Size = 67108864
Characteristics = BlockPackSize BlockUnpackSize

Everything is Ok

Size:       337323520
Compressed: 77407912
Extracting msys2-20221216.tar...
Extracted total of 21 files from msys2-20221216.tar
Copying skeleton files.
These files are for the users to personalise their msys2 experience.

They will never be overwritten nor automatically updated.

'./.bashrc' -> '/home/ใใใงใ/.bashrc'
'./.bash_logout' -> '/home/ใใใงใ/.bash_logout'
'./.bash_profile' -> '/home/ใใใงใ/.bash_profile'
'./.inputrc' -> '/home/ใใใงใ/.inputrc'
'./.profile' -> '/home/ใใใงใ/.profile'
Preparing to install GHC to an isolated location.
This will not interfere with any system-level installation.
Downloaded ghc-9.2.5.
Already downloaded.
Already downloaded.
Decompressing ghc-9.2.5.tar.xz...

7-Zip 22.01 (x64) : Copyright (c) 1999-2022 Igor Pavlov : 2022-07-15

Scanning the drive for archives:
1 file, 502301224 bytes (480 MiB)

Extracting archive: C:\Users\ใใใงใ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5.tar.xz
--
Path = C:\Users\ใใใงใ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5.tar.xz
Type = xz
Physical Size = 502301224
Method = LZMA2:20 CRC64
Streams = 1
Blocks = 1

Everything is Ok

Size:       3002716160
Compressed: 502301224
Extracting ghc-9.2.5.tar...
Extracted total of 21 files from ghc-9.2.5.tar
GHC installed to C:\Users\ใใใงใ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5\
realgcc.exe: fatal error: cannot execute 'cc1': CreateProcess: No such file or directory
compilation terminated.

<no location info>: error:
    output was redirected with -o, but no output will be generated
because there is no StackSetupShim module.

C:\Users\ใใใงใ\AppData\Roaming\stack\setup-exe-src\setup-shim-sDt42OhJ.hs:1:1: error:
    `gcc.exe' failed in phase `C pre-processor'. (Exit code: 1)
  |
1 | {-# LANGUAGE CPP            #-}
  | ^

Error: [S-6374]
       While building simple Setup.hs (scroll up to its section to see the error) using:
       C:\Users\ใใใงใ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5\bin\ghc-9.2.5.exe -rtsopts -threaded -clear-package-db -global-package-db -hide-all-packages -package base -main-is StackSetupShim.mainOverride -package Cabal-3.6.3.0 C:\Users\ใใใงใ\AppData\Roaming\stack\setup-exe-src\setup-sDt42OhJ.hs C:\Users\ใใใงใ\AppData\Roaming\stack\setup-exe-src\setup-shim-sDt42OhJ.hs -o C:\Users\ใใใงใ\AppData\Roaming\stack\setup-exe-cache\x86_64-windows\tmp-Cabal-simple_sDt42OhJ_3.6.3.0_ghc-9.2.5.exe
       Process exited with code: ExitFailure 1

C:\Users\ใใใงใ\Documents\GitHub\haskell-practice>
```

๐ ็ฅใใใใชใใจใใ็็ฑใงใจใฉใผใซใชใฃใ  

๐ [Error in vscode: "gcc.exe' failed in phase C pre-processor'. (Exit code: 1)" #1519](https://github.com/haskell/haskell-ide-engine/issues/1519)  

ใใใใ็ฅ่ญใๆใฃใฆใใชใใใใชใจใฉใผใชใฎใงใใจใใใใ้ฒใใใจใซใใ  

Input:  

```shell
ghci
```

Output:  

```plaintext
GHCi, version 9.4.4: https://www.haskell.org/ghc/  :? for help
ghci> 
```

Input:  

```shell
import Control.Concurrent.Async
```

Output:  

```plaintext
<no location info>: error:
    Could not find module โControl.Concurrent.Asyncโ
    Perhaps you meant
      Control.Concurrent.Chan (from base-4.17.0.0)
      Control.Concurrent.STM (from stm-2.5.1.0)
      Control.Concurrent.MVar (from base-4.17.0.0)
ghci>
```

ใปใใใขใใใซๅคฑๆใใฆใใใฎใงใฏ๏ผ  
`[Ctrl]+[D]` ใงๆใใ  

Output:  

```plaintext
Leaving GHCi.
```

ๅๅบฆ cabal  

Input:  

```shell
cabal repl --build-depends async,say
```

Output:  

```plaintext
Resolving dependencies...
Build profile: -w ghc-9.4.4 -O1
In order, the following will be built (use -v for more details):
 - fake-package-0 (lib) (first run)
Configuring library for fake-package-0..
Warning: No exposed modules
GHCi, version 9.4.4: https://www.haskell.org/ghc/  :? for help
Loaded GHCi configuration from C:\\Users\\ใใใงใ\\AppData\\Local\\Temp\\cabal-repl.-28436\\setcwd.ghci
ghci> 
```

็ถใใฆ  

Input:  

```shell
import Control.Concurrent.Async
import Say
concurrently_ (sayString "Hello") (sayString "World")
```

Output:  

```plaintext
World
Hello
ghci>
```

ใใใใชใใจใซใใใฅใผใใชใขใซใซใใใจ  

```plaintext
Hello
World
```

ใจๅบใใฏใใ ใ  
ๅใใใชใใฎใงใใจใใใใๅใซ้ฒใ  
`[Ctrl]+[D]` ๆผไธ  

Input:  

```shell
cabal install --lib async say --package-env .
```

Output:  

```plaintext
Resolving dependencies...
Up to date
```

๐ ใชใใฎใใฃใกใ  

`Creating a proper package with modules` ใฎ็ฏใ่ชญใ  

๐ ไปฅไธใฎใใฃใฌใฏใใชใผใๆฐ่ฆไฝๆใใ  

```plaintext
    ๐ haskell-practice
๐  โโโ ๐ haskell-project
```

Input:  

```shell
cd haskell-project
cabal init --interactive
```

Output:  

```plaintext
What does the package build:
   1) Library
 * 2) Executable
   3) Library and Executable
   4) Test suite
Your choice? [default: Executable]
```

๐ ๅใใใชใใฎใงใใจใใใใใจใณใฟใผใปใญใผใๆผไธ  

Output:  

```plaintext
Do you wish to overwrite existing files (backups will be created) (y/n)? [default: n] 
```

Input:  

```shell
y
```

Output:  

```plaintext
Please choose version of the Cabal specification to use:
   1) 1.24  (legacy)
   2) 2.0   (+ support for Backpack, internal sub-libs, '^>=' operator)
   3) 2.2   (+ support for 'common', 'elif', redundant commas, SPDX)
   4) 2.4   (+ support for '**' globbing)
 * 5) 3.0   (+ set notation for ==, common stanzas in ifs, more redundant commas, better pkgconfig-depends)
   6) 3.4   (+ sublibraries in 'mixins', optional 'default-language')
Your choice? [default: 3.0]
```

๐ ๅใใใชใใฎใงใใจใใใใใจใณใฟใผใปใญใผใๆผไธ  

Output:  

```plaintext
Package name? [default: haskell-project]
```

๐ ๅใใใชใใฎใงใใจใใใใใจใณใฟใผใปใญใผใๆผไธ  

Output:  

```plaintext
Package version? [default: 0.1.0.0]
```

๐ ๅใใใชใใฎใงใใจใใใใใจใณใฟใผใปใญใผใๆผไธ  

Output:  

```plaintext
Please choose a license:
   1) BSD-2-Clause
   2) BSD-3-Clause
   3) Apache-2.0
   4) MIT
   5) MPL-2.0
   6) ISC
   7) GPL-2.0-only
   8) GPL-3.0-only
   9) LGPL-2.1-only
  10) LGPL-3.0-only
  11) AGPL-3.0-only
  12) GPL-2.0-or-later
  13) GPL-3.0-or-later
  14) LGPL-2.1-or-later
  15) LGPL-3.0-or-later
  16) AGPL-3.0-or-later
  17) Other (specify)
Your choice?
```

๐ ใใใใฏ `MIT ใฉใคใปใณใน` ๆดพใชใฎใง `4` ใๆผไธ  

Output:  

```plaintext
fd:4: hGetContents: invalid argument (invalid byte sequence)
```

๐ ใฉใใใใใฃใกใ๏ผ  

๐ [hGetContents: invalid argument (invalid byte sequence) #324](https://github.com/koalaman/shellcheck/issues/324)  

๐ ใใใใ็ฅ่ญใๆใฃใฆใใชใใใใชใจใฉใผใ   

Input:  

```shell
cabal build
```

Output:  

```plaintext
Error: cabal-3.8.1.0.exe: There is no <pkgname>.cabal package file or
cabal.project file. To build packages locally you need at minimum a
<pkgname>.cabal file. You can use 'cabal init' to create one.

For non-trivial projects you will also want a cabal.project file in the root
directory of your project. This file lists the packages in your project and
all other build configuration. See the Cabal user guide for full details.
```

๐ ใใใใ็ฅ่ญใๆใฃใฆใใชใใใใชใจใฉใผใ   

ๅใใชใใฎใงใใจใใใใๅใซ้ฒใ  

`Adding dependencies` ใฎ็ฏใ่ชญใ  

`haskell-project.cabal` ใใกใคใซใ็กใใฎใงใ้ฒใใชใ  

๐2023-01-22 sun 20:40 end  
