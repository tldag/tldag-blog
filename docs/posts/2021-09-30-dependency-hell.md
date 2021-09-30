## Dependency Hell

Some thirty-something years ago we called it the "DLL Hell". In the meantime it has spread over all software development.

Within the .Net world we differentiate various target frameworks and various platforms. The target framework declares which .Net variant to use,
the platform declares the supported OS or hardware.

The TLDAG project tries to be platform independent and its components try not to limit themselves to a platform. Some components are except
from this rule, as for instance a Linux system just doesn't have a Windows registry.

There are still the target frameworks. The "current" target framework is ```net5.0```. The next one (```net6.0```) is on its way.
With ```net5.0``` you can write tools and even windowed applications. But if you want to write custom tasks for your build process
```net5.0``` is not supported yet.

To write custom targets for CLI usage (like ```dotnet build```), the target framework needs to be ```netstandard2.0``` (maybe 2.1 is possible,
I'm not sure yet.)

To write custom targets that work within Visual Studio, the target framework needs to be ```net472```.

Not all packages support these additional "old" target frameworks. For me right now, the killer is the package ```System.Management.Automation```.
It supports ```net5.0``` only...
