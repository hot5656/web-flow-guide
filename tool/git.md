# Git 

*   [Root](../README.md)



>	set user
>	>	**git config --global user.name "John Doe"**  
>	>	**git config --global user.email johndoe@example.com**


>	clone 
>	>	**git clone https://github.com/hot5656/f2eW2Filter2nd.git**

>	see local branch
>	>	**git branch**  
>	>	* master

>	see all brance 
>	>	**git branch -a**  
>	>	* master  
>	>	  remotes/origin/HEAD -> origin/master  
>	>	  remotes/origin/develop  
>	>	  remotes/origin/master


>	pull remote develop
>	>	**git checkout develop**  
>	>	Switched to a new branch 'develop'  
>	>	Branch 'develop' set up to track remote branch 'develop' from 'origin'.  
>	>	
>	>	**git pull**  
>	>	Already up to date.

>	pull remote branch to local
>	>	**git branch develop origin/develop**

>	remove file
>	>	**git rm xxx.css**


>	reset 
>	>	**git reset --hard**

Discard all local changes to all files permanently
> git reset --hard


### issue
*	"gulp ghpage" --> Error in plugin 'gulp-gh-pages'
```
// include below message 
Details:
    killed: false
    code: 129
    signal: null
    cmd: git rev-list --pretty=raw --max-count=1
// ----------
--> remove floder then redo "gulp ghpage" success
```










	
