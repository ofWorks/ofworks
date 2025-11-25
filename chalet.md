## Chalet

**Chalet** is a modern build system that works with organized recipes.  
It supports both `.json` and `.yaml` formats.  

ofWorks favors **.yaml** syntax because it is much cleaner to read and accepts comments (for commenting out parts of the structure).

Chalet can be used in multiple ways and is used extensively to build [ofLibs, ofWorks libraries](https://github.com/dimitre/ofLibs/).  
Libraries are all compiled as static libs for all platforms.

In **ofWorks** projects, Chalet replaces the openFrameworks make system, becoming the default build system for all platforms.

---

### Useful Chalet Commands

| Command                                     | Description                                        |
| :------------------------------------------ | :------------------------------------------------- |
| `chalet buildrun`                           | Builds project and runs it                         |
| `chalet clean --all`                        | Cleans project and intermediate files              |
| `chalet bundle`                             | Bundles for distribution; exports to the `dist` folder |
| `chalet export vssolution`                  | Exports Visual Studio Project                      |
