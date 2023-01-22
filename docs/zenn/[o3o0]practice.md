# 📅2023-01-22 sun 20:50 start  

チュートリアルが続行不能なので自習する  

📖 [とほほのHaskell入門](https://www.tohoho-web.com/ex/haskell.html)  

👆 Linux 前提で書いてあるが、とりあえず真似してみる  

Input:  

```shell
ghc --version
```

Output:  

```plaintext
The Glorious Glasgow Haskell Compilation System, version 9.4.4
```

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
Raw command: "C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Programs\\stack\\x86_64-windows\\ghc-9.2.5\\bin\\ghc-9.2.5.exe" "C:\\Users\\\12416\12378\12391\12423\\AppData\\Local\\Temp\\stack-sanity-check-d43b1844313e2751\\Main.hs" -no-user-package-db
Run from: C:\Users\むずでょ\AppData\Local\Temp\stack-sanity-check-d43b1844313e2751\
Standard output:

[1 of 1] Compiling Main             ( C:\Users\stack-2.9.3.exe: <stderr>: commitAndReleaseBuffer: invalid argument (invalid character)
```

👆 わたしが知識を持っていないようなエラーだ  
