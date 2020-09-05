# Naive Prime Numbers Benchmark

Just a naive benchmark for Native C, JavaScript and WASM implementations of Prime Number Generator. Not intended to be serious or/and complete assessment of the performance of the mentioned technologies.

The benchmark is computing 10⁷th prime number using the algorithm the name of which I don't remember (check [./prime.c](./prime.c) for the implementation). If somebody knows the name please submit a PR fixing this README, thanks!

Implemented as a part of [tsoding/bng](https://github.com/tsoding/bng) project.

## Dependencies

- C compiler: [gcc] or [clang]
- [wabt]
- [node.js]

[gcc]: https://gcc.gnu.org/
[clang]: https://clang.llvm.org/
[wabt]: https://github.com/WebAssembly/wabt
[node.js]: https://nodejs.org/en/

## Quick Start

```console
$ make
$ time ./prime
$ time node prime-naive.js
$ time node prime-wasm.js
```

## Results on my machine

### Environment

``` console
$ neofetch
       _,met$$$$$gg.          rexim@rexim-B590
    ,g$$$$$$$$$$$$$$$P.       ----------------
  ,g$$P"     """Y$$.".        OS: Debian GNU/Linux 10 (buster) x86_64
 ,$$P'              `$$$.     Host: 20208 Lenovo B590
',$$P       ,ggs.     `$$b:   Kernel: 4.19.0-10-amd64
`d$$'     ,$P"'   .    $$$    Uptime: 1 day, 23 hours, 59 mins
 $$P      d$'     ,    $$P    Packages: 2354 (dpkg)
 $$:      $$.   -    ,d$$'    Shell: bash 5.0.3
 $$;      Y$b._   _,d$P'      Resolution: 1366x768, 1920x1080
 Y$$.    `.`"Y$$$$P"'         WM: i3
 `$$b      "-.__              CPU: Intel i5-3230M (4) @ 3.200GHz
  `Y$$                        GPU: NVIDIA GeForce 610M/710M/810M/820M / GT 620M/625M/630M/720M
   `Y$$.                      GPU: Intel 3rd Gen Core processor Graphics Controller
     `$$b.                    Memory: 2922MiB / 7816MiB
       `Y$$b.
          `"Y$b._                                     
              `"""
```

### Runs

  - [Native C Implementation](./prime.c)
    ```console
      $ time ./prime
      179424673

      real    0m52.964s
      user    0m52.766s
      sys     0m0.196s
    ```
  - [JavaScript Implementation](./prime-naive.js)
    ```console
      $ time node prime-naive.js
      179424673

      real    2m4.781s
      user    2m4.414s
      sys     0m0.208s
    ```
  - [WebAssembly Implemention](./prime.wat)
    ```console
      $ time node prime-wasm.js
      179424673

      real    1m17.061s
      user    1m16.844s
      sys     0m0.192s
    ```
