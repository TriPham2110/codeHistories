# codeHistories

A VS Code extension that aims to capture the information needed to generate usable code histories (capturing code state and output). This work remains a prototype for research purposes.

## Demo

https://user-images.githubusercontent.com/44308446/158084110-06305b2c-af13-4664-8041-ec044a58efff.mp4

## Requirements

* VS Code Insiders version (https://code.visualstudio.com/insiders/) to use their proposed API
* Node JS + simple-git (https://github.com/steveukx/git-js) to incorporate git in the output tracking process
* Default Python extension for VS Code to use the top-right corner "run" button

## Extension Settings

Clone this reprository and run "npm i" to install all dependencies. Once you start running debugging (or F5), make sure to add "settings.json" inside the folder ".vscode" that contains the following information on the debugging VS Code window (the user's working folder and not the codeHistories repository). This ".vscode/settings.json" is not needed for Mac.

```
{
    "terminal.integrated.profiles.windows": {
        "PowerShell": {
            "source": "PowerShell",
            "args": [
                "-ExecutionPolicy",
                "Bypass"
            ]
        }
    },
    "terminal.integrated.defaultProfile.windows": "PowerShell",
}
```

In this new window, the user can start working on their project after initializing codeHistories (through Command Palette or Ctrl+Shift+P) and the intial VS Code will run in the background to capture the code state and output. Make sure to also install the default Python extension for VS Code for the debugging window.

## Release Notes

### V1

Initial release of codeHistories. Basic output capture of installed Python extension when the user uses "run" button option. Can utilize "gitk" to view the code state and output.

### V1.x

Added Mac support and revamped Windows support. It is recommended that user avoid directly interacting with VS Code terminal as some cases might lead to incorrect git commit. Output captured might contain a few additional/unnecessary path strings due to the proposed API's instability.

## Contact

p.tri@wustl.edu

**Thanks and enjoy!**
