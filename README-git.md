             Tips on how to use GIT
===================================================
         written by Yu Zhang (clarazhang@gmail.com)
         updated by King Zevin (king.zevin@qq.com)


1. Useful URLs:
   http://gitref.org/
   http://www.kernel.org/pub/software/scm/git/docs/
   http://blog.csdn.net/csdlbn/article/details/5834002
   https://www.liaoxuefeng.com
   
2. Useful GIT Commands

   - Clone a repository named git-repo
     git clone git@202.38.79.111:git-repo

   - Configure your git to set some brief alias command names
     You can edit .gitconfig file in your home directory, 
     which may contains:

[alias]
        up = pull
        st = status
        di = diff
        ci = !sh -c 'git pull && git commit "$@" && git push' -
        syn = !git pull && git push[gui]
[user]
        email = yourname@youremail

   - Add files to a repo
     cd git-repo
     git branch -a      // list all local/remote branches in git-repo
     git log		// list commit logs of the current branch
     git add files	// add files to the current branch

   - Find other commands
     git help

   - Check what you have done on the current branch
     git status -s

   - Track your changes:
     git diff --no-prefix >patchfile	// save changes into a patchfile
     patch -p0 < patchfile		// apply a patch
     patch -p0 -R < patchfile		// reverse a patch

   - Commit your changes to the local repo
     git commit -am 'info about this revision'

     You can modify your commit if it is wrong:
     git commit --amend

   - Commit your changes to the remote repo
     git push origin
  or
     git push origin branchname

   - Undo your commits permanently
     git reflog		// check the status of your local branch
     git reset --hard HEAD@{1}	// select one revision to reset

   - Switch to other branch
     git checkout -b newlocalbranch remotebranch
     git checkout existedlocalbranch

   - Delete a local/remote branch
     git branch -D localbranch
     git branch -rD remotebranch

3. Wonderful git plugin for zsh

   - Zsh is a shell designed for interactive use, although it is also a powerful scripting language. 

   - With the oh-my-zsh(https://github.com/robbyrussell/oh-my-zsh), you can get the git plugin for zsh automatically. There are lots of useful aliases, such as 
  
        ga = for git add
        gp = for git push
        gl = for git pull
        gd = for git diff
        gst = for git status
        glg = for git log
  
   - What's more, you'll get a most beautiful terminal which may show the current status for the PWD(if there is a git repository). (Actually, My favorite theme is the 'ys', which you can get through oh-my-zsh.)
