You can customize the way your terminal looks and works by finding a bash_profile file or just typing in certain commands in terminal. It's probably easier to customize via the bash_profile because you can see all of your customization commands in one file.

###Find your bash_profile file
type `ls -ad $HOME/.*` into terminal. This brings up all of your shells so you should see `bash_profile` or `bashrc` in that list. Once you open either of those files, here's a smattering of things you can add to customize terminal:

###Prompt components
`\u:` Display the current username
`\h:` Display the hostname
`\W:` Print the base of current working directory
`\$:` Display # (indicates root user) if the effective UID is 0, otherwise display a $.

###Add current git branch name to prompt
    parse_git_branch() {

        git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'

    }

    export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "

###Add colors to prompt
Use the following export command syntax:
`\e[x;ym $PS1 \e[m` where
    `\e[` means Start color scheme.
    `x;y` means Color pair to use (x;y)
    `$PS1` means Your shell prompt variable.
    `\e[m` means Stop color scheme.

###Color codes
    Black       0;30     Dark Gray   1;30     Blue         0;34     
    Light Blue  1;34     Green       0;32     Light Green  1;32     
    Cyan        0;36     Light Cyan  1;36     Red          0;31     
    Light Red   1;31     Purple      0;35     Light Purple 1;35     
    Brown       0;33     Yellow      1;33     Light Gray   0;37     
    White       1;37

So to set your prompt to always be in green, add:
    
    $ export PS1="\e[0;32m[\u@\h \W]\$ \e[m "

####Terminal Preferences
You can change certain things just by going into Preferences in Terminal if you're using the terminal app on a mac machine. In Terminal, go to Terminal-->Preferences. Under the Profiles tab, choose your theme and while it's highlighted, click the Default button on the bottom right of that box. This makes every terminal window you open that theme. 

####Further Reading
http://martinfitzpatrick.name/article/add-git-branch-name-to-terminal-prompt-mac/