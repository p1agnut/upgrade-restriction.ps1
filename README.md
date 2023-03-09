### upgrade-restriction.ps1

ALL CREDITS for this script goes to [alkampfergit](https://gist.github.com/alkampfergit) & [nouseforname](https://gist.github.com/nouseforname).

This is just an step-by-step instruction for dumb people like me.

#### PowerShell script to exclude packages from 
```
> winget upgrade --all
```

Note: PowerShell Execution Policy must be set to **Unrestricted** or **RemoteSigned**.

1. Run PowerShell as **admin**
    
    -Check policy: 
`Get-ExecutionPolicy`

    -Set policy: 
`Set-ExecutionPolicy Unrestricted`
or
`Set-ExecutionPolicy RemoteSigned`

2. Create **.txt** file

     -Copy/Paste code
    
     -change/adjust desired **package ID** *(e.g. Winamp.Winamp)*
     
``` 
$skipUpdate = @(
'Winamp.Winamp',
'Github.Atom'
)  
```   
   -save file with file extension **.ps1** or save as **.txt**, then rename **.ps1** *(e.g. upgrade-restriction.ps1)*
    
3. Run PowerShell as **admin**

    -Change **directory**:
    `cd c:\path\to\script`
    
    -**Execute** script:
    `.\upgrade-restriction.ps1`

