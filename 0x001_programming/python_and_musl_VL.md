## Act 1: musl pain aurggh. Gotta make venv

Tried running this:

```bash
pip install numpy
```

got Error: pip is an externally managed program. Use venv and install packages in virtual environments.

* So, I did the follows

```bash
python3 -m venv ./
```

then run pip inside the environment

```bash
./bin/pip install numpy
```

## Act 2: tryna run a python script

Be my script `script.py`:

```python
import numpy
```

running it:

```python
./bin/python script.py
```

I GOT an error: numpy not running for my old CPU. So, I am supposed to install an older package support.

I should stop expecting python to work perfectly on musl. However, rust and nodejs seems to run just fine.
