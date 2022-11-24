# Hex Virtualization [![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)
Developed by <a href="https://github.com/hexck">Hexk</a> and updated by <a href="https://github.com/HideakiAtsuyo">Hideaki</a>
<br><br>

## :guardsman: Why do you need Hex Virtualization ? 

Hex-Virtualization was built so that people can learn from it, for real-world use, other obfuscation techniques such as anti-tampering, mutations, controlflow, and renamer would bring this vm to its full potential.

<a href="https://help.gapotchenko.com/eazfuscator.net/30/virtualization#Virtualization_Introduction"> Eazfuscator</a> describes perfectly what a vm does:<br>
_"Many of us consider particular pieces of code especially important. May it be a license code check algorithm implementation, an innovative optimization method, or anything else equally important so we would want to protect it by any means possible. As we know, the traditional obfuscation techniques basically do renaming of symbols and encryption, thus leaving the actual algorithms — cycles, conditional branches and arithmetics potentially naked to eye of the skilled intruder._

_Here a radical approach may be useful: to remove all the .NET bytecode instructions from an assembly, and replace it with something completely different and unknown to an external observer, but functionally equivalent to the original algorithm during runtime — this is what the code virtualization actually is."_

<br>

## 📺 Preview

[Click Here](https://i.imgur.com/cVntYFD.mp4) if it doesn't show anything.
![](https://i.imgur.com/cVntYFD.gif)

## 🚀 Features

- [ ] __**[Released Full Update]**__

- [x] Virtualization: Virtualizes code into instructions which only Hex.VM can understand (Main one)
- [x] Obfuscated runtime (only renaming atm) (no more broken injection)
- [ ] Fix OpCodes
  - [ ] Not completed (see the [preview](https://github.com/HideakiAtsuyo/Hex-Virtualization#-preview))
- [ ] Improve Custom OpCodes
- [ ] Improve the Runtime Code
- [x] Add some OpCodes & Custom OpCodes
  - Will add list later
- [x] Modify methods encryption
  - Well only compressed now not encrypted anymore :)
- [x] Modify methods storage place (just moved to Runtime DLL Resources, will change later.)
  - Move to a array ?
- [ ] Add a few protections to the runtime ([StrawPoll](https://strawpoll.com/polls/e6Z2eQwOXgN))
  - [x] Strings (Runtime & Virtualized Methods)
  - [x] Import Protections (Runtime)
  - [x] Renaming (Runtime + Module)
  
## :star: How does it work ?

- MSIL to VMIL
- Methods are stored as resources
- Bytes are encrypted with xor cipher
<br>

## :fire: What does it do ?

- [x] Has support for a decent amount of opcodes, as said, this is made for educational purposes and as such I believe these opcodes are enough for people to learn and build on
- [x] Easy to use, understand, and build on

<br>

## :bookmark_tabs: Examples
#### Before:
```c#
    public int Add()
    {
        return this._x + this._y;
    }
```
#### After:
```c#
    public int Add()
    {
        return (int)Hex.VM.Runtime.VirtualMachine.RunVM("Hecker", 1337, new object[]
        {
            this
        });
    }
```


## Resources
https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf <br>



https://docs.microsoft.com/en-us/dotnet/api/system.reflection.emit.opcodes?view=netframework-4.8

_If you got any questions feel free to contact the original author via discord Hexk#0001_ or me on Telegram [@HideakiAtsuyo](https://t.me/HideakiAtsuyo)

[What does this hyperlink do ?](https://github.com/HideakiAtsuyo/Hex-Virtualization/edit/master/README.md#hex-virtualization-)
