
# Add build steps
- Prints out counter number and branch that was triggered
- Check project files 
```sh
#!/bin/sh
pwd
echo "Check Current dir"
echo Counter: %build.counter%
echo Branch: %teamcity.build.branch%
ls .

```


TODO : 

- Add SSH Key - Upload Require PEM 
    - Generate new Private key using pem command
    - copy public key to github repo > settings > deploy key
    - Uplad private key in TC Project
- Agents error ??
- Cannot filter changes from PR / other refs no selection

Branch filter Diff between 
- VCS Root filter -> base filter ?
- VCS Root -> below 
    Will filter visibility on UI 
    Only works on root settings filter if set +:*
- Trigger Filter
    Only works on root settings filter if set +:*


Add Key SSH: 
https://medium.com/@amaya30/integrating-teamcity-and-github-with-ssh-is-actually-as-easy-as-you-would-think-it-is-3429e01112ea