screeninfo
----------

Fetch location and size of physical screens.

### Supported environments

- MS Windows
- MS Windows: Cygwin
- GNU/Linux: X11 (through Xinerama)
- GNU/Linux: DRM (experimental)
- OSX: (through PyOBJus)

I don't plan on testing OSX or other environments myself. For this reason,
I strongly encourage pull requests.

### Installation

```
pip install screeninfo
```

If you install it from sources:

```
python3 setup.py install
```

### Usage

```python
from screeninfo import get_monitors
for m in get_monitors():
    print(str(m).split("-"))
```

**Output**:

>['1920','1080']

### Forcing environment

In some cases (emulating X server on Cygwin etc.) you might want to specify the
driver directly. You can do so by passing extra parameter to `get_monitors()`
like this:

```python
from screeninfo import get_monitors
for m in get_monitors('osx'):
    print(str(m).split("-"))
```

Available drivers: `windows`, `cygwin`, `x11`, `osx`.
