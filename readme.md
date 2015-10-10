
Installing Chocolatey

1. Install `Visual Studio Code`
1. Open folder
1. Ctrl-Shift-C for Command Prompt
    - > `powershell_ise`
	    - $ Ctrl-N
1. Issue the following command to install Chocolatey 

```PowerShell
$policy = Get-ExecutionPolicy -Scope CurrentUser
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser
iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))
Set-ExecutionPolicy -ExecutionPolicy $policy -Scope CurrentUser
```
2. Press F5 to execute
2. Alt-F4 to close powershell
2. > `exit` to close command prompt

Install node (back in VS Code)
3. Ctrl-Shift-C for command prompt
3. > `cd %AllUsersProfile%\chocolatey`
3. > `choco install node`

Install dnx

4. Ctrl-Shift-C for Command Prompt
```cmd
cmd > @powershell -NoProfile -ExecutionPolicy unrestricted -Command "&{$Branch='dev';$wc=New-Object System.Net.WebClient;$wc.Proxy=[System.Net.WebRequest]::DefaultWebProxy;$wc.Proxy.Credentials=[System.Net.CredentialCache]::DefaultNetworkCredentials;Invoke-Expression ($wc.DownloadString('https://raw.githubusercontent.com/aspnet/Home/dev/dnvminstall.ps1'))}"
cmd > dnvm upgrade
```

Install Yeoman
5. Ctrl-Shift-C for command prompt
5. > `npm install -g yo grunt-cli generator-aspnet bower`

Use Yeoman to create asp.net mvc app
5. > `yo aspnet`
5. select you app type and name
5. > cd <name_of_your_app>'
5. > `dnu restore`
5. > `dnu build`
5. > `dnx web`

6. Last time, Ctrl-Shift-C for command prompt
6. > `"%ProgramFiles%\Internet Explorer\iexplore.exe" http://localhost:5000/`
6. > `exit`

Install Git
7. Ctrl-Shift-C for command prompt
8. `choco install git.install`