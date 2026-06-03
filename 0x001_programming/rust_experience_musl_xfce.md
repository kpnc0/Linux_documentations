## C was no longer pure in my eyes.

The binaries compiled against `gilbc` would not work in `musl`. 
My OS happened to be void linux musl. That means, most of the compiled programs written in C (made to be compatible with gilbc) won't work in my computer.

Basically, musl and gilbc are two different C packages runtimes. Binaries compiled against musl don't seem to be that heavy in size. I don't know why, but musl has lesser attack vectors in their runtimes.

By design, musl rejects many features of gilbc, marking it's own viewpoint onto this earth.

## If a binary doesn't work in my computer.

I would have to compile the code from the source (if the codebase is opensource). 
If the codebase is written in C, with hardcoded gilbc calls, then I will have to take a while, rewriting the codebase.

But then, if the codebase is written in `rust`..

```bash
cargo build --release --package --target x86_64-unknown-linux-musl
```

Note that the compilation step is a bit.. compute intensive, and will take a long time. Best to have a powerful computer do it remotely.

Maybe using `google colab` wink wink..

## Rust is amazing just because of that

Not to mention that most of the binaries are being **rewritten** in Rust. I wish to learn the art of rewriting things in Rust. And literally manually writing in Rust.

I installed a nice pdf on Rust. Will get back here soon.
