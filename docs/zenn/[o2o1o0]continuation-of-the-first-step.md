📅2023-01-09 mon (成人の日) 23:50  

♪[作業用BGM](https://www.youtube.com/watch?v=74EApHZde-8)  

📖[First steps](https://www.haskell.org/ghcup/steps/)  

👇 意味は分からないが、コンパイルエラーを出すコマンドが書いてあるので真似する  

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

そして `hello.hs` を修正しろ、ということらしい  

hello.hs:  

```shell
main :: IO ()
main = putStrLn "Hello, world!"
```

👇 再度、コマンドを打鍵  

```shell
ghc -Wall hello.hs -fforce-recomp
[1 of 2] Compiling Main             ( hello.hs, hello.o )
[2 of 2] Linking hello.exe [Objects changed]
```

エラーは出なかったが、何をやっているのか分からない  

# REPL

`ghci` というコマンドで REPL できるという話しがある。  
ディスプレイのメッセージを見ながら　キーボードを打鍵するのを繰り返すやつだ。  
インタープリター型のプログラミング言語でできるやつだ  

やってみる。  

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

REPL でけてる  

ところで 職場で「できました」と報告をして提出したあとにバグがあると 上長から「できたって言ったよね！」と返されたことがあったので 独り言は「できた」とも聞こえる「でけた」と言うようにしている  

```shell
double x = x + x
ghci> double 2
4
```

👆 分けわからんが Haskell の書き方らしい  
これはラムダ式の書き方をしていると考えると `double` は ただの名前で、  
２行目は `double` に 2 を渡す、という命令で、  
１行目は `double` に渡されたものを x で受け取って、 `x + x` をする、ということなのだろう  

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

👆 何やってるか　さっぱり分からん  
先に進む  

```shell
ghci> :load hello.hs
Ok, one module loaded.
ghci> main
Hello, world!
ghci>
```

👆 `:load` で、ファイルを読込むのかもしれない  

```shell
ghci> import Data.Bits
ghci> shiftL 32 1
64
ghci> clearBit 33 0
32
```

👆 `Data.Bits` という何かを読込んで、32 を 1 bit 論理左シフト演算をして 64 にしたのだろう。  
`clearBit` は 100001 の右端のビットを 0 で上書きして 100000 にしたのかもしれない。知らんけど  

```shell
:type pubStrLn

<interactive>:1:1: error:
    Variable not in scope: pubStrLn
    Suggested fix: Perhaps use ‘putStrLn’ (imported from Prelude)
```

👆 よく分からん。強制終了の方法も分からん  

```shell
Leaving GHCi.
```

いろいろ試すと `[Ctrl] + [D]` で止まった  

```shell
C:\Users\むずでょ\Documents\GitHub\haskell-practice>ghci
GHCi, version 9.4.4: https://www.haskell.org/ghc/  :? for help
ghci> :type putStrLn 
putStrLn :: String -> IO ()
ghci> quit

<interactive>:2:1: error:
    Variable not in scope: quit
    Suggested fix: Perhaps use ‘quot’ (imported from Prelude)
ghci> :quit
Leaving GHCi.
```

👆 頭のコロン `:` を忘れやすい  

まだ続きは長そうだ。ここで終わる  

📅2023-01-10 tue 00:21 end  

# 📅2023-01-22 sun 19:27 start

♪[作業用BGM](https://www.youtube.com/watch?v=oSBlfiO7jwM)  

`Using external packages in ghci` の節を読む。 GHCI はコンパイラか何かだろうか。  
コンパイラで　外部パッケージを使う方法だろうか  

`cabal` と `stack` というのがあって、それを使ってインストールできるらしい。  
とにかくコマンドを叩いてみよう  

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
Loaded GHCi configuration from C:\\Users\\むずでょ\\AppData\\Local\\Temp\\cabal-repl.-25248\\setcwd.ghci
ghci>
```

👆 何かは分からないが 何かされたようだ。  
`[Ctrl]+[D]` で抜ける  

Input:  

```shell
stack exec --package async --package say -- ghci
```

Output:  

```plaintext
Writing implicit global project config file to: C:\Users\むずでょ\AppData\Roaming\stack\global-project\stack.yaml
Note: You can change the snapshot via the resolver field there.
Using latest snapshot resolver: lts-20.8
Downloaded msys2-20221216.
Downloaded 7z.dll.
Downloaded 7z.exe.
Decompressing msys2-20221216.tar.xz...

7-Zip 22.01 (x64) : Copyright (c) 1999-2022 Igor Pavlov : 2022-07-15

Scanning the drive for archives:
1 file, 77407912 bytes (74 MiB)

Extracting archive: C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\msys2-20221216.tar.xz
--
Path = C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\msys2-20221216.tar.xz
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

'./.bashrc' -> '/home/むずでょ/.bashrc'
'./.bash_logout' -> '/home/むずでょ/.bash_logout'
'./.bash_profile' -> '/home/むずでょ/.bash_profile'
'./.inputrc' -> '/home/むずでょ/.inputrc'
'./.profile' -> '/home/むずでょ/.profile'
Preparing to install GHC to an isolated location.
This will not interfere with any system-level installation.
Downloaded ghc-9.2.5.
Already downloaded.
Already downloaded.
Decompressing ghc-9.2.5.tar.xz...

7-Zip 22.01 (x64) : Copyright (c) 1999-2022 Igor Pavlov : 2022-07-15

Scanning the drive for archives:
1 file, 502301224 bytes (480 MiB)

Extracting archive: C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5.tar.xz
--
Path = C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5.tar.xz
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
GHC installed to C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5\
realgcc.exe: fatal error: cannot execute 'cc1': CreateProcess: No such file or directory
compilation terminated.

<no location info>: error:
    output was redirected with -o, but no output will be generated
because there is no StackSetupShim module.

C:\Users\むずでょ\AppData\Roaming\stack\setup-exe-src\setup-shim-sDt42OhJ.hs:1:1: error:
    `gcc.exe' failed in phase `C pre-processor'. (Exit code: 1)
  |
1 | {-# LANGUAGE CPP            #-}
  | ^

Error: [S-6374]
       While building simple Setup.hs (scroll up to its section to see the error) using:
       C:\Users\むずでょ\AppData\Local\Programs\stack\x86_64-windows\ghc-9.2.5\bin\ghc-9.2.5.exe -rtsopts -threaded -clear-package-db -global-package-db -hide-all-packages -package base -main-is StackSetupShim.mainOverride -package Cabal-3.6.3.0 C:\Users\むずでょ\AppData\Roaming\stack\setup-exe-src\setup-sDt42OhJ.hs C:\Users\むずでょ\AppData\Roaming\stack\setup-exe-src\setup-shim-sDt42OhJ.hs -o C:\Users\むずでょ\AppData\Roaming\stack\setup-exe-cache\x86_64-windows\tmp-Cabal-simple_sDt42OhJ_3.6.3.0_ghc-9.2.5.exe
       Process exited with code: ExitFailure 1

C:\Users\むずでょ\Documents\GitHub\haskell-practice>
```

👆 知らんがな、という理由でエラーになった  

📖 [Error in vscode: "gcc.exe' failed in phase C pre-processor'. (Exit code: 1)" #1519](https://github.com/haskell/haskell-ide-engine/issues/1519)  

わたしが知識を持っていないようなエラーなので、とりあえず進むことにする  

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
    Could not find module ‘Control.Concurrent.Async’
    Perhaps you meant
      Control.Concurrent.Chan (from base-4.17.0.0)
      Control.Concurrent.STM (from stm-2.5.1.0)
      Control.Concurrent.MVar (from base-4.17.0.0)
ghci>
```

セットアップに失敗しているのでは？  
`[Ctrl]+[D]` で抜ける  

Output:  

```plaintext
Leaving GHCi.
```

再度 cabal  

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
Loaded GHCi configuration from C:\\Users\\むずでょ\\AppData\\Local\\Temp\\cabal-repl.-28436\\setcwd.ghci
ghci> 
```

続けて  

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

おかしなことに　チュートリアルによると  

```plaintext
Hello
World
```

と出るはずだ。  
分からないので　とりあえず先に進む  
`[Ctrl]+[D]` 押下  

Input:  

```shell
cabal install --lib async say --package-env .
```

Output:  

```plaintext
Resolving dependencies...
Up to date
```

👆 なんのこっちゃ  

`Creating a proper package with modules` の節を読む  

👇 以下のディレクトリーを新規作成する  

```plaintext
    📂 haskell-practice
👉  └── 📂 haskell-project
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

👆 分からないので、とりあえずエンター・キーを押下  

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

👆 分からないので、とりあえずエンター・キーを押下  

Output:  

```plaintext
Package name? [default: haskell-project]
```

👆 分からないので、とりあえずエンター・キーを押下  

Output:  

```plaintext
Package version? [default: 0.1.0.0]
```

👆 分からないので、とりあえずエンター・キーを押下  

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

👆 わたしは `MIT ライセンス` 派なので `4` を押下  

Output:  

```plaintext
fd:4: hGetContents: invalid argument (invalid byte sequence)
```

👆 どういうこっちゃ？  

📖 [hGetContents: invalid argument (invalid byte sequence) #324](https://github.com/koalaman/shellcheck/issues/324)  

👆 わたしが知識を持っていないようなエラーだ  

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

👆 わたしが知識を持っていないようなエラーだ  

動かないので、とりあえず先に進む  

`Adding dependencies` の節を読む  

`haskell-project.cabal` ファイルが無いので、進めない  

📅2023-01-22 sun 20:40 end  
