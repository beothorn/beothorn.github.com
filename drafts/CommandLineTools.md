ohmyzsh
https://github.com/ohmyzsh/ohmyzsh

ripgrep 
sudo apt install ripgrep

fuzzy finder
sudo apt-get install fzf

htop
sudo apt-get install htop

bat
sudo apt install bat

lsd
https://github.com/Peltoche/lsd
needs nerd fonts to show icons
https://github.com/ryanoasis/nerd-fonts

tig
sudo apt install tig

echo "bind status P !git push origin" > ~/.tigrc

xclip


make rcs point to scriptsrc
.zshrc
.bashrc

source scriptsrc

aliases

alias l='lsd'
alias fd='fdfind'
alias f='fzf'
alias toClipboard='xclip -selection clipboard'
alias fromClipboard='xclip -o'


create ~/bin


delta differ
https://github.com/dandavison/delta
