📅2023-01-09 mon (成人の日) 23:50  

♪[作業用BGM](https://www.youtube.com/watch?v=74EApHZde-8)  

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

📅2023-01-10 tue 00:21  
