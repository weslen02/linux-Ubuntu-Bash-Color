# Linux Ubuntu - Changes
Change the color of bash and show the branch that is working

> **Note**: Before you begin, make the **Backup** your files!

## How it works for me:

**Root .bashrc**

> Steps:
1. Access your bash as a root;

2.  Access the file with the edtor of your choice (I use vim) and edit:

        # vim /root/.bashrc

![enter image description here](https://raw.githubusercontent.com/weslen02/linux-Ubuntu-Bash-Color/master/img/rootImg/02.png)

3. For me these edits work! When you finish the edits, save the file and restart bash. Save: (button) Esc to exit the insert, and :x to save.

![enter image description here](https://raw.githubusercontent.com/weslen02/linux-Ubuntu-Bash-Color/master/img/rootImg/03.png)


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
2. Access the file with the edtor of your choice (I use vim) and edit: # vim /home/userName/.bashrc

![enter image description here](https://raw.githubusercontent.com/weslen02/linux-Ubuntu-Bash-Color/master/img/userImg/01.png)

3. For me these edits work! When you finish the edits, save the file and restart bash. Save: (button) Esc to exit the insert, and :x to save.

![enter image description here](https://raw.githubusercontent.com/weslen02/linux-Ubuntu-Bash-Color/master/img/userImg/02.png)

        if [ "$color_prompt"  = yes ];  then
             #NEW MODIFIED TO THE GIT
         PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00;37m\] \w\[\033[01;36m\]$(__git_ps1 " (%s)")\[\033[01;34m\]$\[\033[00m\] '
    
        else
             PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
        fi
        unset color_prompt force_color_prompt

**PLUS PLUS:**
1. Open the Terminal to a specific Directory
> Copy and paste at the end of the user's file .bashrc:

![enter image description here](https://raw.githubusercontent.com/weslen02/linux-Ubuntu-Bash-Color/master/img/userImg/03.png)

        #Open the Terminal to a specific Directory
        cd /myDirectory
        
2. autocomplete from bash to git may not be working for ROOT
> uncomment autocomplete option the end of the **Root's** file .bashrc:

        # enable programmable completion features (you don't need to enable
        # this, if it's already enabled in /etc/bash.bashrc and /etc/profile
        # sources /etc/bash.bashrc).
        if [ -f /etc/bash_completion ] && ! shopt -oq posix; then
            . /etc/bash_completion
        fi

![enter image description here](https://raw.githubusercontent.com/weslen02/linux-Ubuntu-Bash-Color/master/img/rootImg/04.png)


- Info Bash tips: [Colors and formatting](https://misc.flogisoft.com/bash/tip_colors_and_formatting) (ANSI/VT100 Control sequences)
