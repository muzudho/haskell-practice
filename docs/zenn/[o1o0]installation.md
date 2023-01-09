📅2023-01-09 mon (成人の日) 21:30  

わたしは、プログラム言語のHaskell（ハスケル）への知見はない。  
ググりながら試す。  

🔍 `ハスケル インストール`  

📖[Haskell のインストール（Windows 上）](https://www.kkaneko.jp/tools/win/haskellinstwindows.html)  

グーグル検索上位のサイトを読むと、📖[Haskell.org](https://www.haskell.org/) がハスケルの公式サイトかもしれない。  
ひとまず検索で見つけたサイトではなく、公式サイトのトップページからインストーラーを探してみる。  
すると 👇別のページに着いた  

📖[GHCup](https://www.haskell.org/ghcup/)  

なんだか分からないが Power Shell のコマンドが置いてあった。
そこで Visual Studio Code の Terminal を開き Power Shell を選ぶ。  

```powershell
PS C:\Users\むずでょ\Documents\GitHub\haskell-practice> Set-ExecutionPolicy Bypass -Scope Process -Force;[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; try { Invoke-Command -ScriptBlock ([ScriptBlock]::Create((Invoke-WebRequest https://www.haskell.org/ghcup/sh/bootstrap-haskell.ps1 -UseBasicParsing))) -ArgumentList $true } catch { Write-Error $_ }
Picked C:\ as default Install prefix!
Welcome to Haskell!

This script can download and install the following programs:
  * ghcup - The Haskell toolchain installer
  * ghc   - The Glasgow Haskell Compiler
  * msys2 - A linux-style toolchain environment required for many operations
  * cabal - The Cabal build tool for managing Haskell software
  * stack - (optional) A cross-platform program for developing Haskell projects
  * hls   - (optional) A language server for developers to integrate with their editor/IDE

Please note that ANTIVIRUS may interfere with the installation. If you experience problems, consider
disabling it temporarily.

Where to install to (this should be a short Path, preferably a Drive like 'C:\')?
If you accept this path, binaries will be installed into 'C:\ghcup\bin' and msys2 into 'C:\ghcup\msys64'.
Press enter to accept the default [C:\]:
```

ん？  

Dockerコンテナの中へインストールする方がいいか？  
しかし めんどくさいので このままインストールすることにする  
Enter キーを打鍵する  

```powershell
Setting env variable GHCUP_INSTALL_BASE_PREFIX to 'C:\'
Preparing for GHCup installation...
Specify Cabal directory (this is where haskell packages end up)
Press enter to accept the default [C:\\cabal]:
```

`Cabal` が何だかわからないが Enter キーを打鍵する  

```powershell
Install HLS
Do you want to install the haskell-language-server (HLS) for development purposes as well?
[Y] Yes  [N] No  [A] Abort  [?] ヘルプ (既定値は "N"):
```

`HLS` も何だかわからないが Y キーを打鍵する  

```powershell
Install stack
Do you want to install stack as well?
[Y] Yes  [N] No  [A] Abort  [?] ヘルプ (既定値は "N"): 
```

`stack` も何だかわからないが Y キーを打鍵する  

```powershell
First checking for Msys2...

Install MSys2
Do you want GHCup to install a default MSys2 toolchain (recommended)?
[Y] Yes  [N] No  [?] ヘルプ (既定値は "Y"):
```

`MSys2` も何だかわからないが Y キーを打鍵する  

```powershell
...Msys2 doesn't exist, installing into C:\\ghcup\msys64    
Starting installation in 5 seconds, this may take a while...
Downloading Msys2 archive 20221216...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 57.0M  100 57.0M    0     0  1125k      0  0:00:51  0:00:51 --:--:-- 1676k
Extracting Msys2 archive...
Processing MSYS2 bash for first time use...
Copying skeleton files.
These files are for the users to personalise their msys2 experience.

They will never be overwritten nor automatically updated.

'./.bashrc' -> '/home/むずでょ/.bashrc'
'./.bash_logout' -> '/home/むずでょ/.bash_logout'
'./.bash_profile' -> '/home/むずでょ/.bash_profile'
'./.inputrc' -> '/home/むずでょ/.inputrc'
'./.profile' -> '/home/むずでょ/.profile'
'C:\WINDOWS\system32\drivers\etc\hosts' -> '/etc/hosts'
'C:\WINDOWS\system32\drivers\etc\protocol' -> '/etc/protocols'
'C:\WINDOWS\system32\drivers\etc\services' -> '/etc/services'
'C:\WINDOWS\system32\drivers\etc\networks' -> '/etc/networks'
gpg: /etc/pacman.d/gnupg/trustdb.gpg: trustdb created
gpg: no ultimately trusted keys found
gpg: starting migration from earlier GnuPG versions
gpg: porting secret keys from '/etc/pacman.d/gnupg/secring.gpg' to gpg-agent
gpg: migration succeeded
==> Generating pacman master key. This may take some time.
gpg: Generating pacman keyring master key...
gpg: directory '/etc/pacman.d/gnupg/openpgp-revocs.d' created
gpg: revocation certificate stored as '/etc/pacman.d/gnupg/openpgp-revocs.d/56BAC218994D73470A2B5575C98DC0A1F938A74D.rev'
gpg: Done
==> Updating trust database...
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 1u
==> Appending keys from msys2.gpg...
==> Locally signing trusted keys in keyring...
  -> Locally signed 5 keys.
==> Importing owner trust values...
gpg: setting ownertrust to 4
gpg: setting ownertrust to 4
gpg: setting ownertrust to 4
gpg: setting ownertrust to 4
gpg: setting ownertrust to 4
==> Disabling revoked keys in keyring...
  -> Disabled 4 keys.
==> Updating trust database...
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   1  signed:   5  trust: 0-, 0q, 0n, 0m, 0f, 1u
gpg: depth: 1  valid:   5  signed:   7  trust: 0-, 0q, 0n, 5m, 0f, 0u
gpg: depth: 2  valid:   4  signed:   2  trust: 4-, 0q, 0n, 0m, 0f, 0u
gpg: next trustdb check due at 2023-04-22
gpg: error retrieving 'alexey.pawlow@gmail.com' via WKD: No data
gpg: error reading key: No data
gpg: refreshing 1 key from hkps://keyserver.ubuntu.com
gpg: key F40D263ECA25678A: "Alexey Pavlov (Alexpux) <alexey.pawlow@gmail.com>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
gpg: error retrieving 'david.macek.0@gmail.com' via WKD: No data
gpg: error reading key: No data
gpg: refreshing 1 key from hkps://keyserver.ubuntu.com
gpg: key 790AE56A1D3CFDDC: "David Macek (MSYS2 master key) <david.macek.0@gmail.com>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
gpg: error retrieving 'martellmalone@gmail.com' via WKD: No data
gpg: error reading key: No data
gpg: refreshing 1 key from hkps://keyserver.ubuntu.com
gpg: key DA7EF2ABAEEA755C: "Martell Malone (martell) <martellmalone@gmail.com>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
gpg: error retrieving 'reiter.christoph@gmail.com' via WKD: No data
gpg: error reading key: No data
gpg: refreshing 1 key from hkps://keyserver.ubuntu.com
gpg: key 755B8182ACD22879: "Christoph Reiter (MSYS2 master key) <reiter.christoph@gmail.com>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
gpg: error retrieving 'icquinteiro@gmail.com' via WKD: No data
gpg: error reading key: No data
gpg: refreshing 1 key from hkps://keyserver.ubuntu.com
gpg: key 9F418C233E652008: "Ignacio Casal Quinteiro <icquinteiro@gmail.com>" not changed
gpg: Total number processed: 1
gpg:              unchanged: 1
gpg: error retrieving 'mingw.android@gmail.com' via WKD: No data
gpg: error reading key: No data

情報: 指定された条件のタスクは実行されていません。
Upgrading full system...
:: Synchronizing package databases...
 mingw32                                                                                              1731.8 KiB   846 KiB/s 00:02 [##############################################################################] 100%
 mingw64                                                                                              1784.1 KiB   534 KiB/s 00:03 [##############################################################################] 100%
 ucrt64                                                                                               1829.4 KiB   692 KiB/s 00:03 [##############################################################################] 100%
 clang32                                                                                              1713.1 KiB   768 KiB/s 00:02 [##############################################################################] 100%
 clang64                                                                                              1773.3 KiB   677 KiB/s 00:03 [##############################################################################] 100%
 msys                                                                                                  417.7 KiB   988 KiB/s 00:00 [##############################################################################] 100%
:: Starting core system upgrade...
warning: terminate other MSYS2 programs before proceeding
resolving dependencies...
looking for conflicting packages...

Packages (3) mintty-1~3.6.3-1  msys2-runtime-3.4.3-4  pacman-6.0.1-28

Total Download Size:    9.16 MiB
Total Installed Size:  44.89 MiB
Net Upgrade Size:      -1.63 MiB

:: Proceed with installation? [Y/n] 
:: Retrieving packages...
 mintty-1~3.6.3-1-x86_64                                                                               811.2 KiB   708 KiB/s 00:01 [##############################################################################] 100%
 pacman-6.0.1-28-x86_64                                                                                  5.9 MiB  4.73 MiB/s 00:01 [##############################################################################] 100%
 msys2-runtime-3.4.3-4-x86_64                                                                            2.4 MiB   885 KiB/s 00:03 [##############################################################################] 100%
 Total (3/3)                                                                                             9.2 MiB  2.81 MiB/s 00:03 [##############################################################################] 100%
(3/3) checking keys in keyring                                                                                                     [##############################################################################] 100%
(3/3) checking package integrity                                                                                                   [##############################################################################] 100%
(3/3) loading package files                                                                                                        [##############################################################################] 100%
(3/3) checking for file conflicts                                                                                                  [##############################################################################] 100%
(3/3) checking available disk space                                                                                                [##############################################################################] 100%
:: Processing package changes...
(1/3) upgrading mintty                                                                                                             [##############################################################################] 100%
(2/3) upgrading msys2-runtime                                                                                                      [##############################################################################] 100%
(3/3) upgrading pacman                                                                                                             [##############################################################################] 100%
:: To complete this update all MSYS2 processes including this terminal will be closed. Confirm to proceed [Y/n] 
Upgrading full system twice...
:: Synchronizing package databases...
 clangarm64                                                                                           1040.3 KiB   514 KiB/s 00:02 [##############################################################################] 100%
 mingw32 is up to date
 mingw64 is up to date
 ucrt64 is up to date
 clang32 is up to date
 clang64 is up to date
 msys is up to date
:: Starting core system upgrade...
 there is nothing to do
:: Starting full system upgrade...
resolving dependencies...
looking for conflicting packages...

Packages (16) brotli-1.0.9-5  bsdtar-3.6.2-3  curl-7.87.0-2  gawk-5.2.1-2  heimdal-libs-7.8.0-3  libcurl-7.87.0-2  libksba-1.6.3-1  liblzma-5.4.0-1  libopenssl-3.0.7-2  libpcre2_8-10.42-1  libpsl-0.21.2-1
              libsqlite-3.40.1-1  libssh2-1.10.0-3  nano-7.1-1  openssl-3.0.7-2  xz-5.4.0-1

Total Download Size:    8.17 MiB
Total Installed Size:  23.20 MiB
Net Upgrade Size:       1.79 MiB

:: Proceed with installation? [Y/n] 
:: Retrieving packages...
 openssl-3.0.7-2-x86_64                                                                                661.0 KiB   982 KiB/s 00:01 [##############################################################################] 100%
 gawk-5.2.1-2-x86_64                                                                                  1224.1 KiB  1751 KiB/s 00:01 [##############################################################################] 100% 
 curl-7.87.0-2-x86_64                                                                                  916.2 KiB  1124 KiB/s 00:01 [##############################################################################] 100% 
 heimdal-libs-7.8.0-3-x86_64                                                                           832.6 KiB   981 KiB/s 00:01 [##############################################################################] 100% 
 libopenssl-3.0.7-2-x86_64                                                                            1603.9 KiB  1615 KiB/s 00:01 [##############################################################################] 100% 
 libsqlite-3.40.1-1-x86_64                                                                             658.7 KiB  1572 KiB/s 00:00 [##############################################################################] 100%
 bsdtar-3.6.2-3-x86_64                                                                                 323.6 KiB   741 KiB/s 00:00 [##############################################################################] 100%
 nano-7.1-1-x86_64                                                                                     640.8 KiB   848 KiB/s 00:01 [##############################################################################] 100% 
 brotli-1.0.9-5-x86_64                                                                                 339.4 KiB   375 KiB/s 00:01 [##############################################################################] 100% 
 libcurl-7.87.0-2-x86_64                                                                               253.2 KiB   630 KiB/s 00:00 [##############################################################################] 100% 
 xz-5.4.0-1-x86_64                                                                                     319.0 KiB   624 KiB/s 00:01 [##############################################################################] 100% 
 libksba-1.6.3-1-x86_64                                                                                125.6 KiB   368 KiB/s 00:00 [##############################################################################] 100% 
 libssh2-1.10.0-3-x86_64                                                                               192.5 KiB   290 KiB/s 00:01 [##############################################################################] 100% 
 libpcre2_8-10.42-1-x86_64                                                                             125.0 KiB   355 KiB/s 00:00 [##############################################################################] 100% 
 liblzma-5.4.0-1-x86_64                                                                                 85.3 KiB   244 KiB/s 00:00 [##############################################################################] 100% 
 libpsl-0.21.2-1-x86_64                                                                                 69.4 KiB   216 KiB/s 00:00 [##############################################################################] 100% 
 Total (16/16)                                                                                           8.2 MiB  3.49 MiB/s 00:02 [##############################################################################] 100% 
(16/16) checking keys in keyring                                                                                                   [##############################################################################] 100%
(16/16) checking package integrity                                                                                                 [##############################################################################] 100% 
(16/16) loading package files                                                                                                      [##############################################################################] 100% 
(16/16) checking for file conflicts                                                                                                [##############################################################################] 100% 
(16/16) checking available disk space                                                                                              [##############################################################################] 100% 
:: Processing package changes...
( 1/16) upgrading brotli                                                                                                           [##############################################################################] 100% 
( 2/16) upgrading liblzma                                                                                                          [##############################################################################] 100%
( 3/16) upgrading libopenssl                                                                                                       [##############################################################################] 100%
( 4/16) upgrading bsdtar                                                                                                           [##############################################################################] 100%
( 5/16) upgrading libsqlite                                                                                                        [##############################################################################] 100%
( 6/16) upgrading heimdal-libs                                                                                                     [##############################################################################] 100%
( 7/16) upgrading libpsl                                                                                                           [##############################################################################] 100%
( 8/16) upgrading openssl                                                                                                          [##############################################################################] 100%
( 9/16) upgrading libpcre2_8                                                                                                       [##############################################################################] 100%
(10/16) upgrading libssh2                                                                                                          [##############################################################################] 100%
(11/16) upgrading libcurl                                                                                                          [##############################################################################] 100%
(12/16) upgrading curl                                                                                                             [##############################################################################] 100%
(13/16) upgrading gawk                                                                                                             [##############################################################################] 100%
(14/16) upgrading libksba                                                                                                          [##############################################################################] 100%
(15/16) upgrading nano                                                                                                             [##############################################################################] 100%
(16/16) upgrading xz                                                                                                               [##############################################################################] 100%
:: Running post-transaction hooks...
(1/1) Updating the info directory file...
Installing Dependencies...
warning: curl-7.87.0-2 is up to date -- skipping
resolving dependencies...
looking for conflicting packages...

Packages (7) autoconf2.13-2.13-5  autoconf2.69-2.69-2  autoconf2.71-2.71-1  diffutils-3.8-4  m4-1.4.19-2  autoconf-wrapper-15-1  mingw-w64-x86_64-pkgconf-1~1.8.0-2

Total Download Size:   1.40 MiB
Total Installed Size:  6.54 MiB

:: Proceed with installation? [Y/n] 
:: Retrieving packages...
 autoconf2.13-2.13-5-any                                                                               136.3 KiB  84.3 KiB/s 00:02 [##############################################################################] 100%
 autoconf2.71-2.71-1-any                                                                               326.6 KiB   198 KiB/s 00:02 [##############################################################################] 100% 
 autoconf2.69-2.69-2-any                                                                               284.0 KiB   171 KiB/s 00:02 [##############################################################################] 100% 
 m4-1.4.19-2-x86_64                                                                                    238.1 KiB   143 KiB/s 00:02 [##############################################################################] 100% 
 diffutils-3.8-4-x86_64                                                                                363.9 KiB   185 KiB/s 00:02 [##############################################################################] 100% 
 mingw-w64-x86_64-pkgconf-1~1.8.0-2-any                                                                 79.1 KiB   235 KiB/s 00:00 [##############################################################################] 100% 
 autoconf-wrapper-15-1-any                                                                               4.7 KiB  12.4 KiB/s 00:00 [##############################################################################] 100% 
 Total (7/7)                                                                                          1432.6 KiB   670 KiB/s 00:02 [##############################################################################] 100% 
(7/7) checking keys in keyring                                                                                                     [##############################################################################] 100%
(7/7) checking package integrity                                                                                                   [##############################################################################] 100% 
(7/7) loading package files                                                                                                        [##############################################################################] 100% 
(7/7) checking for file conflicts                                                                                                  [##############################################################################] 100% 
(7/7) checking available disk space                                                                                                [##############################################################################] 100%
:: Processing package changes...
(1/7) installing m4                                                                                                                [##############################################################################] 100% 
(2/7) installing diffutils                                                                                                         [##############################################################################] 100%
(3/7) installing autoconf2.71                                                                                                      [##############################################################################] 100% 
(4/7) installing autoconf2.69                                                                                                      [##############################################################################] 100%
(5/7) installing autoconf2.13                                                                                                      [##############################################################################] 100%
(6/7) installing autoconf-wrapper                                                                                                  [##############################################################################] 100% 
(7/7) installing mingw-w64-x86_64-pkgconf                                                                                          [##############################################################################] 100%
:: Running post-transaction hooks...
(1/1) Updating the info directory file...
Updating SSL root certificate authorities...
warning: ca-certificates-20211016-2 is up to date -- reinstalling
resolving dependencies...
looking for conflicting packages...

Packages (1) ca-certificates-20211016-2

Total Download Size:   0.32 MiB
Total Installed Size:  0.86 MiB
Net Upgrade Size:      0.00 MiB

:: Proceed with installation? [Y/n] 
:: Retrieving packages...
 ca-certificates-20211016-2-any                                                                        324.8 KiB   200 KiB/s 00:02 [##############################################################################] 100%
(1/1) checking keys in keyring                                                                                                     [##############################################################################] 100%
(1/1) checking package integrity                                                                                                   [##############################################################################] 100% 
(1/1) loading package files                                                                                                        [##############################################################################] 100% 
(1/1) checking for file conflicts                                                                                                  [##############################################################################] 100% 
(1/1) checking available disk space                                                                                                [##############################################################################] 100% 
:: Processing package changes...
(1/1) reinstalling ca-certificates                                                                                                 [##############################################################################] 100%
Setting default home directory...
Creating shortcuts...
Adding C:\\ghcup\bin to Users Path...
Setting CABAL_DIR to 'C:\cabal'
Starting GHCup installer...
PS C:\Users\むずでょ\Documents\GitHub\haskell-practice> 
```

放置したら終わってたがエラーが出てないか？  
とりあえず先に進む  

📖[First steps](https://www.haskell.org/ghcup/steps/)  

```powershell
C:\Users\むずでょ\Documents\GitHub\haskell-practice>ghc --version
ghc : 用語 'ghc' は、コマンドレット、関数、スクリプト ファイル、または操作可能なプログラムの名前として認識されません。名前が正しく記述されていることを確認し、パスが含まれている場合はそのパスが正しいことを確認してから
、再試行してください。
発生場所 行:1 文字:1
+ ghc --version
+ ~~~
    + CategoryInfo          : ObjectNotFound: (ghc:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

じゃあ Visual Studio Code を一旦閉じて 開き直す  

```shell
C:\Users\むずでょ\Documents\GitHub\haskell-practice>ghc --version
The Glorious Glasgow Haskell Compilation System, version 9.2.5

C:\Users\むずでょ\Documents\GitHub\haskell-practice>
```

インストールはできたのだと思う。  

ところで、 `MinGW x64` というコマンドプロンプト・ウィンドウが開いていることに気づいた  

```shell
To do so, you may want to run 'source /c/ghcup/env' in your current terminal
session as well as your shell configuration (e.g. ~/.bashrc).

===============================================================================

All done!

In a new powershell or cmd.exe session, now you can...

Start a simple repl via:
  ghci

Start a new haskell project in the current directory via:
  cabal init --interactive

Install other GHC versions and tools via:
  ghcup list
  ghcup install <tool> <version>

To install system libraries and update msys2/mingw64,
open the "Mingw haskell shell"
and the "Mingw package management docs"
desktop shortcuts.

If you are new to Haskell, check out https://www.haskell.org/ghcup/steps/
Press any key to exit
```

Enter キーを打鍵すると消えた  

📅2023-01-09 mon (成人の日) 22:27  
