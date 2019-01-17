# Linux Ubuntu - Changes
Change the color of bash and show the branch that is working

## How it works for me:

**Root .bashrc**

> Steps:
1. Access your bash as a root;
2.  Access the file with the edtor of your choice (I use vim) and edit: \# vim /root/ .bashrc
3. For me these edits work! When you finish the edits, save the file and restart bash. Save: (button) Esc :x (force sabe with x:!)


        if [ "$color_prompt" = yes ]; then
            #COPIED FROM ELSE THAT IS NOT BEING USED
            PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
        else

            #NEW MODIFIED TO THE GIT
            PS1='${debian_chroot:+($debian_chroot)}\[\033[01;31m\]\u@\h\[\033[00m\]:\[\033[00;37m\]\w\[\033[01;36m\]$(parse_git_branch)\[\033[00;32m\]\[\033[00m\]\$ '

        fi
        unset color_prompt force_color_prompt
      

**User .bashrc**

> Steps:

1. Access your bash as a root;
2. Access the file with the edtor of your choice (I use vim) and edit: # vim /home/userName .bashrc
3. For me these edits work, when you finish the edits, save the file and restart bash.

        if [ "$color_prompt"  = yes ];  then
             #NEW MODIFIED TO THE GIT
         PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00;37m\] \w\[\033[01;36m\]$(__git_ps1 " (%s)")\[\033[01;34m\]$\[\033[00m\] '
    
        else
             PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
        fi
        unset color_prompt force_color_prompt

**PLUS PLUS:**

> Copy and paste in the end file .bashrc:

    #Open the Terminal to a specific Directory
    cd /workspaceDev
