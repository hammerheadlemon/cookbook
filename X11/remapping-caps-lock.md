This is what I've put in `.Xmodmap` to remap the Caps Lock to Control.

Afterwards make sure you do `xmodmap` on the file to activate it.

```shell
 remove Lock = Caps_Lock
 keysym Caps_Lock = Control_L
 add Lock = Caps_Lock
 add Control = Control_L
```
