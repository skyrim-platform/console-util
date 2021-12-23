## `@skyrim-platform/console-util`

(Unofficial) TypeScript library for the ConsoleUtil Skyrim modding utility

- ConsoleUtil on GitHub: https://github.com/Ryan-rsm-McKenzie/ConsoleUtilSSE
- ConsoleUtil on Nexus: https://www.nexusmods.com/skyrimspecialedition/mods/24858

## Getting Started

You can find an example Skyrim Platform plugin with documentation on how to get started using this library: https://github.com/skyrim-platform/example-plugin-using-libraries

> Papyrus source code conversion to TypeScript originally generated using [Papyrus-2-Typescript](https://github.com/CarlosLeyvaAyala/Papyrus-2-Typescript)

## Example

```ts
import { on, printConsole } from '@skyrim-platform/skyrim-platform'
import { GetSelectedReference } from '@skyrim-platform/console-util'

// Whenever anything is selected in the ~ Skyrim console, it prints out that object's name in the console
on('update', () => {
    const selectedReference = GetSelectedReference()
    if (selectedReference) {
        let name = selectedReference.getName()
        if (! name) name = selectedReference.getDisplayName()
        if (! name) name = selectedReference.getBaseObject()!.getName()
        printConsole(`Selected reference: ${name}`)
    }
})
```
