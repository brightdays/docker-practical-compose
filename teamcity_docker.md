# Generate PEM Key
- enter command
- enter key name
- Get private and public key
- Copy public key
- Upload private key to Teamcity
```sh
    ssh-keygen -t rsa -m PEM
```

Optional - copy to server
```sh
    brew install ssh-copy-id
    ssh-copy-id demo@198.51.100.0
    // OR USE
    cat ~/.ssh/id_rsa.pub | ssh demo@198.51.100.0 "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >>  ~/.ssh/authorized_keys"

```

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