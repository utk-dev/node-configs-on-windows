# node-on-windows
My checklist for setting up Node on Windows

Embrace multi-platformism! Given below is a list of instructions/tips that I use to setup a basic cross-platform development environment for Node projects.

1. Use the cross-platform powershell as your execution environment if possible. 
   - [https://github.com/PowerShell/PowerShell](https://github.com/PowerShell/PowerShell)
2. Set Powershell as your default execution engine for `npm` scripts.
   - `npm config set script-shell "powershell"` if you are using the closed source built-in Windows Powershell (Powershell <6).
   - `npm config set script-shell "pwsh"` if you are using the new open source Powershell (Powershell >6)
3. Use verbose Powershell commands e.g. use `Set-Location` and `Copy-Item` instead of `cd` and `cp` respectively.
4. `run-script-os` is an npm package that let's you make your package.json scripts platform-independent.
   - [https://www.npmjs.com/package/run-script-os](https://www.npmjs.com/package/run-script-os)
5. Use a separate config file for each platform you might be developing your project on to differentiate between file path inconsistencies.
   - [https://stackoverflow.com/a/12584017](https://stackoverflow.com/a/12584017)
6. Tip: Avoid WSL2 for now (It has some nasty bugs). Prefer native windows environment if you are on windows.
7. Go to `Settings > Update & Security > For Developers` 
   - Toggle ON "Install apps from any source, including loose files."
   - Enable all checkboxes and hit "Apply" under the heading "File Explorer" 
   - Also enable the only checkbox available uner heading "Powershell" and hit "Apply"
8. Installing node on windows means installing a lot of components of Visual Studio, Python, Chocolatey and a few more things in a specific sequence. Although the installer takes care of this, it doesn't show the progress very well. BE PATIENT.
9. Prefer cross-platform packages over anything else.
10. VS Code + pwsh + nodejs = ♥
11. MySql driver for nodejs doesn't support the new multiple-handshaking authentication. Configure your MySql installation to use the old password authentication.
12. Use VS Code's [https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack](live-share extension pack) for cross-platform communication-over-code.
