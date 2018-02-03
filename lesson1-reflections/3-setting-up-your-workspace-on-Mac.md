# Downloading necessary files
- Save this file in your home directory with the name `git-completion.bash`.
- Save this file in your home directory with the name git-prompt.sh.
Download `bash_profile_course` here.
- If you already have a file in your home directory named `.bash_profile`, copy the content from bash_profile_course and paste it at the bottom of `.bash_profile`. Otherwise, move `bash_profile_course` to your home directory and rename it to `.bash_profile`. If you use Linux, you may need to name this file .bashrc instead of .bash_profile. (If you're curious to learn more about how bash prompts work, see this page.)

##### Make sure you can start your editor from the terminal!

If you use Sublime, you can do this by add the following line to your .bash_profile (you may need to change the path if Sublime is installed in a different location for you):

```sh
alias subl="/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl"
```

## Making Git configurations
Run the following Git configuration commands. The first one will need to be modified if you are using a text editor other than Sublime, or if Sublime is installed in another location for you. See this page for the correct command for a couple of other popular text editors. For any other editor, you'll need to enter the command you use to launch that editor from the terminal.

```git
git config --global core.editor "'/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl' -n -w"
git config --global push.default upstream
git config --global merge.conflictstyle diff3
```

(Instead of the first command, you may be able to use the simpler `git config --global core.editor "subl -n -w"` as shown in the video, but many students have found this does not work for them.)

## Restart the terminal
You'll need to close and re-open the terminal before all your changes take effect.

