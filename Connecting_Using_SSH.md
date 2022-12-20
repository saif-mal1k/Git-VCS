
### open bash & run this command
```
ssh-keygen -b 4096 -t rsa
```


### then, run this command
```
cat .ssh/id_rsa.pub
```

### copy the output, goto github account settings, add new SSH key
<img src="https://user-images.githubusercontent.com/63545175/208660860-a5af0a16-b1df-4e47-8bad-16b6c852fd0b.png" width="420px">


### then, run this command
```
ssh -T git@github.com
```








<br/>


<br/>


<br/>


<br/>


---
***references:***
- https://docs.github.com/en/authentication/connecting-to-github-with-ssh



