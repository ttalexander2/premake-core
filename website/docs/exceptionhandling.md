Enable or disable exception handling.

```lua
exceptionhandling ("value")
```

### Parameters ###

`value` is one of:

|         |                                                   |
|---------|---------------------------------------------------|
| Default | Use the toolset's default setting for exceptions. |
| On      | Turn on exceptions.                               |
| Off     | Turn off exceptions.                              |
| SEH     | Turn on exceptions and use [structured exception handling](https://msdn.microsoft.com/en-us/library/windows/desktop/ms680657(v=vs.85).aspx) when available. |

More values may be added by [add-on modules](Modules.md).


### Applies To ###

Project configurations.


### Availability ###

Premake 5.0 or later.


### See Also ###

* [rtti](rtti.md)
