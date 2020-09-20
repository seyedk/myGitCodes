# myGitCodes
## How to use Github in multiple accounts
1. Create a new SSH Key
```
 ssh-keygen -t rsa -C "my-email-address"
```
for the id_rsa_xxx use the compnay name that I need to add as remote for instance, if ABC is my client, then I typically use id_rsa_ABC as the name, then I copy the content of the Id_rsa_ABC.pub pubic key

2. Paste the Id_rsa_xxx file content into my compnay `ABC` account profile
3. Then Add the entry to ssh config file at `~/.ssh/config`
here's how I add the ABC company as my git 
```
Host github-ABC
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_ABC
```

4. Test it
if I have a "test-project" repo in the company ABC git repo, then I use the following to add it to my remote 

```
git remote add ABC-origin git@github-ABC:abc/test-project.git

```

Then I try to push something to that repo:

```
git push -u ABC-origin master
```

Enjoy! 
