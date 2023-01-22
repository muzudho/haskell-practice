とほほで自習  

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

Input:  

```shell
stack new sample
```

Output:  

```plaintext
Downloading template new-template to create project sample in directory sample\...
C:\UC:\UDownloaded C:\Users\むずでょ\AppData\Roaming\stack\templates\new-template.hsfiles.

Note: The following parameters were needed by the template but not provided: author-email, author-name, category, copyright and github-username.

      You can provide them in Stack's global YAML configuration file (C:\Users\むずでょ\AppData\Roaming\stack\config.yaml) like this:

      templates:
        params:
          author-email: value
          author-name: value
          category: value
          copyright: value
          github-username: value

      Or you can pass each one on the command line as parameters like this:

      stack new sample new-template -p "author-email:value" -p "author-name:value" -p "category:value" -p "copyright:value" -p "github-username:value"

Looking for Cabal or package.yaml files to use to initialise Stack's project-level YAML configuration file.

Using the Cabal packages:
* sample\

Selecting the best among 19 snapshots...


Note: Matches https://raw.githubusercontent.com/commercialhaskell/stackage-snapshots/master/lts/20/8.yaml

Selected the snapshot https://raw.githubusercontent.com/commercialhaskell/stackage-snapshots/master/lts/20/8.yaml.
Initialising Stack's project-level YAML configuration file using snapshot https://raw.githubusercontent.com/commercialhaskell/stackage-snapshots/master/lts/20/8.yaml.
Considered 1 user package.
Writing configuration to sample\stack.yaml.
Stack's project-level YAML configuration file has been initialised.
```

👆 なんだか分からん  

```plaintext
    📂 haskell-practice
    └── 📂 haskell-project
👉      └── 📂 sample
            ├── 📂 app
            │   └── 📄 Main.hs
            ├── 📂 src
            │   └── 📄 Lib.hs
            ├── 📂 test
            │   └── 📄 Spec.hs
            ├── 📄 .gitignore
            ├── 📄 CHANGELOG.md
            ├── 📄 LICENSE
            ├── 📄 package.yaml
            ├── 📄 README.md
            ├── 📄 sample.cabal
            ├── 📄 Setup.hs
            └── 📄 stack.yaml
```

👆 `sample` フォルダーができていた。中身が何か入っている  

sample/app/Main.hs:  

```haskell
module Main (main) where

import Lib

main :: IO ()
main = someFunc
```

sample/src/Lib.hs:  

```haskell
module Lib
    ( someFunc
    ) where

someFunc :: IO ()
someFunc = putStrLn "someFunc"
```

sample/test/Spec.hs:  

```haskell
main :: IO ()
main = putStrLn "Test suite not yet implemented"
```

sample/.gitignore:  

```
.stack-work/
*~
```

sample/CHANGELOG.md:  

```md
# Changelog for `sample`

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to the
[Haskell Package Versioning Policy](https://pvp.haskell.org/).

## Unreleased

## 0.1.0.0 - YYYY-MM-DD

```

sample/LICENSE:  

```
Copyright Author name here (c) 2023

All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright
      notice, this list of conditions and the following disclaimer.

    * Redistributions in binary form must reproduce the above
      copyright notice, this list of conditions and the following
      disclaimer in the documentation and/or other materials provided
      with the distribution.

    * Neither the name of Author name here nor the names of other
      contributors may be used to endorse or promote products derived
      from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

sample/package.yaml:  

```yaml
name:                sample
version:             0.1.0.0
github:              "githubuser/sample"
license:             BSD3
author:              "Author name here"
maintainer:          "example@example.com"
copyright:           "2023 Author name here"

extra-source-files:
- README.md
- CHANGELOG.md

# Metadata used when publishing your package
# synopsis:            Short description of your package
# category:            Web

# To avoid duplicated efforts in documentation and dealing with the
# complications of embedding Haddock markup inside cabal files, it is
# common to point users to the README.md file.
description:         Please see the README on GitHub at <https://github.com/githubuser/sample#readme>

dependencies:
- base >= 4.7 && < 5

ghc-options:
- -Wall
- -Wcompat
- -Widentities
- -Wincomplete-record-updates
- -Wincomplete-uni-patterns
- -Wmissing-export-lists
- -Wmissing-home-modules
- -Wpartial-fields
- -Wredundant-constraints

library:
  source-dirs: src

executables:
  sample-exe:
    main:                Main.hs
    source-dirs:         app
    ghc-options:
    - -threaded
    - -rtsopts
    - -with-rtsopts=-N
    dependencies:
    - sample

tests:
  sample-test:
    main:                Spec.hs
    source-dirs:         test
    ghc-options:
    - -threaded
    - -rtsopts
    - -with-rtsopts=-N
    dependencies:
    - sample
```

sample/README.md:  

```md
# sample

```

sample/sample.cabal:  

```cabal
cabal-version: 1.12

-- This file has been generated from package.yaml by hpack version 0.35.1.
--
-- see: https://github.com/sol/hpack

name:           sample
version:        0.1.0.0
description:    Please see the README on GitHub at <https://github.com/githubuser/sample#readme>
homepage:       https://github.com/githubuser/sample#readme
bug-reports:    https://github.com/githubuser/sample/issues
author:         Author name here
maintainer:     example@example.com
copyright:      2023 Author name here
license:        BSD3
license-file:   LICENSE
build-type:     Simple
extra-source-files:
    README.md
    CHANGELOG.md

source-repository head
  type: git
  location: https://github.com/githubuser/sample

library
  exposed-modules:
      Lib
  other-modules:
      Paths_sample
  hs-source-dirs:
      src
  ghc-options: -Wall -Wcompat -Widentities -Wincomplete-record-updates -Wincomplete-uni-patterns -Wmissing-export-lists -Wmissing-home-modules -Wpartial-fields -Wredundant-constraints
  build-depends:
      base >=4.7 && <5
  default-language: Haskell2010

executable sample-exe
  main-is: Main.hs
  other-modules:
      Paths_sample
  hs-source-dirs:
      app
  ghc-options: -Wall -Wcompat -Widentities -Wincomplete-record-updates -Wincomplete-uni-patterns -Wmissing-export-lists -Wmissing-home-modules -Wpartial-fields -Wredundant-constraints -threaded -rtsopts -with-rtsopts=-N
  build-depends:
      base >=4.7 && <5
    , sample
  default-language: Haskell2010

test-suite sample-test
  type: exitcode-stdio-1.0
  main-is: Spec.hs
  other-modules:
      Paths_sample
  hs-source-dirs:
      test
  ghc-options: -Wall -Wcompat -Widentities -Wincomplete-record-updates -Wincomplete-uni-patterns -Wmissing-export-lists -Wmissing-home-modules -Wpartial-fields -Wredundant-constraints -threaded -rtsopts -with-rtsopts=-N
  build-depends:
      base >=4.7 && <5
    , sample
  default-language: Haskell2010

```

sample/Setup.hs:  

```haskell
import Distribution.Simple
main = defaultMain

```

sample/stack.yaml:  

```yaml
# This file was automatically generated by 'stack init'
#
# Some commonly used options have been documented as comments in this file.
# For advanced use and comprehensive documentation of the format, please see:
# https://docs.haskellstack.org/en/stable/yaml_configuration/

# Resolver to choose a 'specific' stackage snapshot or a compiler version.
# A snapshot resolver dictates the compiler version and the set of packages
# to be used for project dependencies. For example:
#
# resolver: lts-3.5
# resolver: nightly-2015-09-21
# resolver: ghc-7.10.2
#
# The location of a snapshot can be provided as a file or url. Stack assumes
# a snapshot provided as a file might change, whereas a url resource does not.
#
# resolver: ./custom-snapshot.yaml
# resolver: https://example.com/snapshots/2018-01-01.yaml
resolver:
  url: https://raw.githubusercontent.com/commercialhaskell/stackage-snapshots/master/lts/20/8.yaml

# User packages to be built.
# Various formats can be used as shown in the example below.
#
# packages:
# - some-directory
# - https://example.com/foo/bar/baz-0.0.2.tar.gz
#   subdirs:
#   - auto-update
#   - wai
packages:
- .
# Dependency packages to be pulled from upstream that are not in the resolver.
# These entries can reference officially published versions as well as
# forks / in-progress versions pinned to a git hash. For example:
#
# extra-deps:
# - acme-missiles-0.3
# - git: https://github.com/commercialhaskell/stack.git
#   commit: e7b331f14bcffb8367cd58fbfc8b40ec7642100a
#
# extra-deps: []

# Override default flag values for local packages and extra-deps
# flags: {}

# Extra package databases containing global packages
# extra-package-dbs: []

# Control whether we use the GHC we find on the path
# system-ghc: true
#
# Require a specific version of Stack, using version ranges
# require-stack-version: -any # Default
# require-stack-version: ">=2.9"
#
# Override the architecture used by Stack, especially useful on Windows
# arch: i386
# arch: x86_64
#
# Extra directories used by Stack for building
# extra-include-dirs: [/path/to/dir]
# extra-lib-dirs: [/path/to/dir]
#
# Allow a newer minor version of GHC than the snapshot specifies
# compiler-check: newer-minor
```

👆 さっぱり分からないが、先に進む  

Input:  

```shell
cd ./sample
```

👇 ビルドする  

Input:  

```shell
stack build
```

Output:  

```plaintext
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
```

👆 ビルドでエラー  
