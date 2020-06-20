# Sublime Syntax highlighting for RISC OS Command files.
A Sublime syntax definition for RISC OS command files to enable syntax highlighting.
This is suitable for use with Command, Obey, TaskExec, TaskObey and Desktop files.

## Colouring

The syntax colouring recognises many of the standard commands, and a few of the common library
and system commands. The processor is generally not context sensitive, so a sequence that looks like a command will be coloured as one.

The coloured features are:

* Comments, prefixed by | at the start of a line.
* Common commands from the standard RISC OS modules.
* System variables with `<`/`>` delimiters.
* GSTrans characters in the form `|` followed by a letter.
* Strings delimited by `"`.
* Filenames, where they are obviously anchored, are preceded by a variable, or are preceded by a filesystem name, or path name.
* A few special cases, like `*FX`, `*TV`, `*Key` which do not require a separating space, and the controls in `*If` statements (`Then`, `Else`).


## File recognition

RISC OS files commonly use the NFS encoding format of suffixing the filename with `,xxx` for the filetype. These are not supported by the Sublime Text extensions syntax, so it is recommended that the ApplySyntax package (or similar) be used to select the syntax mode.

The following configuration is suitable for use within `ApplySyntax.sublime-settings`:

```
        {
            // RISCOS Specific commands file (Obey, TaskObey, Command, TaskExec, Desktop)
            "syntax": "RISCOSCommand/RISCOSCommand",
            "rules": [
                {"file_path": ".*(\\\\|/)*,(ffe|feb|fd7|fd6|fea)$"},
            ]
        },
```


## Install manually

* Place the `RISCOSCommand.sublime-syntax` file inside the Sublime Text packages User folder (`Preferences | Browse Packages...`)
* Restart Sublime Text


## Install with Package Control

* Install [Package Control](http://wbond.net/sublime_packages/package_control)
* Run “Package Control: Install Package” command, find and install `RISCOSCommand` plugin.
* Restart Sublime Text if necessary

## License
This package is licensed under the MIT License.
