---
title: Using Modules
---

Premake can be extended through the use of third-party modules. Modules can add support for new toolsets, languages, and frameworks as well as entirely new features. We keep [a community-maintained list of modules here on the wiki](modules).

To use a module, download or clone the module's repository to [one of Premake's search paths](locating-scripts), making sure that the destination folder has the same name as the module's main script, e.g. **qt/qt.lua**.

````
$ git clone https://github.com/dcourtois/premake-qt qt
````

Then simply call `require()` from your project or [system script](system-scripts) to include it.

```lua
require "qt"
```

### Including a Module With Your Project ###

For convenience, you may wish to keep a copy of the modules you require in your project's source tree. In that case you may place them anywhere you wish, and provide the relative path when requiring it. For instance, if your main **premake5.lua** is located at the root of your project tree, and your modules are in a folder named **build**, you may load it like:

```lua
require "build/qt"
```

### System Modules ###

You may also put your modules anywhere on [Premake's search paths](locating-scripts), for example in **~/.premake**. In this case no path information is needed, and you can simply call:

```lua
require "qt"
```

If you wish to make a module always available to *all* of your projects, you may place the call to `require()` in your [system script](system-scripts). In that case, the module will be automatically loaded each time Premake runs, and all of its features will be available.


## Version Requirements

To ensure compatibility with your project script, it can sometimes be helpful to require a minimum version or range of versions for your module dependencies. Premake includes [a modified version Lua's `require()` function](require) which accepts a version test as its second argument.

```lua
require("qt", ">=1.1")
```

See [the `require()` documentation](require) for more information and examples.
