# What's this?

It's just me our of curiosity playing around with Visual Studio Code, Chocolatey, Yeoman, DNX, MVC6 and what not.

## Keyboard only

Trying to do it all without grabbing the mouse. Here we go.

### Key combos
`Open CMD` = Ctrl-Shift-C

# Day 1

## Installing Chocolatey

1. Install `Visual Studio Code`
1. Open folder
1. `Open CMD`
    - > `powershell_ise`
	    - $ Ctrl-N
1. Issue the following command to install Chocolatey 

```PowerShell
$policy = Get-ExecutionPolicy -Scope CurrentUser
Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser
iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))
Set-ExecutionPolicy -ExecutionPolicy $policy -Scope CurrentUser
```
1. Press F5 to execute
1. Alt-F4 to close powershell
1. > `exit` to close command prompt

## Install node (back in VS Code)
2. `Open CMD`
2. > `cd %AllUsersProfile%\chocolatey`
2. > `choco install node`

## Install dnx

3. `Open CMD`
```cmd
cmd > @powershell -NoProfile -ExecutionPolicy unrestricted -Command "&{$Branch='dev';$wc=New-Object System.Net.WebClient;$wc.Proxy=[System.Net.WebRequest]::DefaultWebProxy;$wc.Proxy.Credentials=[System.Net.CredentialCache]::DefaultNetworkCredentials;Invoke-Expression ($wc.DownloadString('https://raw.githubusercontent.com/aspnet/Home/dev/dnvminstall.ps1'))}"
cmd > dnvm upgrade
```

## Install Yeoman
4. `Open CMD`
4. > `npm install -g yo grunt-cli generator-aspnet bower`

## Use Yeoman to create asp.net mvc app
5. > `yo aspnet`
5. select you app type and name
5. > cd <name_of_your_app>'
5. > `dnu restore`
5. > `dnu build`
5. > `dnx web`

## Run MVC6

6. `Open CMD`
6. > `"%ProgramFiles%\Internet Explorer\iexplore.exe" http://localhost:5000/`
6. > `exit`

## Install Git
7. `Open CMD`
7. > `choco install git.install`
7. > `set path=C:\Program Files\Git\bin;%path%`
7. > exit

## Adding your project to Github
8. git init
8. git add README.md
8. git commit -m "first commit"
8. git remote add origin https://github.com/codepic/vs-code-mvc6-cmd.git
8. git push -u origin master