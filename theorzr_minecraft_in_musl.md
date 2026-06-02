## Anyways, I wanted to play minecraft in my Void Linux PC

Prism launcher seemed to run, but I didn't really have an official account. I just wanted to play minecraft locally.

So, I opened the good old theorzr/portablemc repository.

> Turns out, there was not a single distribution that supported musl linux.

So, I agressively queried Deepseek, GeminiCLI (for technical process)

And, I got a crucial insight:

1. theorzr/portablemc was written in rust.

2. Rust source code can be compiled against musl runtime. The process was pretty simple, scripted by geminiCLI agent.

3. As a result, the compiled binary could execute in musl system

## The pipeline

Install the necessary if it is your first time

```bash
sudo xbps-install -S base-devel rustc cargo pkg-config openssl-devel
```


Now compile:
```bash
export OPENSSL_STATIC=1

cargo build --release --package portablemc=cli --target x86_64-unknown-linux-musl
```

The artifact will be found in `target/x86_64-unknown-linux-musl/release/`

## The execution:

Install the void compatible JDK to be used to run minecraft.
```bash
sudo xbps-install -S openjdk8
```

Then, run the executable from inside the directory:

```bash
./portablemc start 1.16.5 --jvm /usr/lib/jvm/openjdk8/jre/bin/java
```

`--jvm /usr/lib/jvm/openjdk8/jre/bin/java` ensures that our rust binary launches the game using our system compatible java, rather than Mojang exported java.

Also, use modern versions of minecraft.


## Reflection

1. Apparently, Rust can be compiled against musl library. This will prove a useful knowledge in the future ventures of mine.

2. Most of production level code are being rewritten in `rust`

3. I must stop expecting the existance of musl compatible binaries in most distributions, which means, I am a bit **stuck** if the code is proprietary, or I would have to compile from source.

4. The process of compiling was pretty fun.



