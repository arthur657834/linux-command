curl https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash -o ~/.git-completion.bash


vi profile 
if [ -f ~/.git-completion.bash ]; then
    source ~/.git-completion.bash
fi

source profile

git 命令就会自动补全