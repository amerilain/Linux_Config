Steps for installing virtual machine:  these are the steps I followed:  1. from https://cdimage.ubuntu.com/jammy/daily-live/current/ I installed 64-bit ARM desktop image. I used UTM and installed the ISO. I had some trouble with this but after what I thought was a loaded image, I had to find the icon on my Linux desktop and load it from there. I then cleared the ISO image and restarted.

2. Update and upgrade: sudo apt update sudo apt upgrade
3. install clang: sudo apt install clang
4. install GCC: sudo apt install gcc g++  I installed both clang and GCC for more flexibility down the road if needed. 
5. Install Zsh: sudo apt install zsh
6. Set Zsh as default shell: chsh -s $(which zsh)

I restarted my VM and now have zsh as my default terminal. I didn’t have any zsh startup files and was presented with options for creating these. I chose to “Populate your ~/.zshrc with the configuration recommended by the system administrator and exit (you will need to edit the file by hand, if so desired).”

7. Install curl: sudo apt install curl
8. Install git: sudo apt install git
9. Install oh-my-zsh: sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
10. Install Powerlevel10k theme: your command is different: git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k  -  I used a command to clone the Powerlevel10k repository into the custom themes directory of Oh MY Zsh. I then edited my .zshrc file to set ZSH_THEME="powerlevel10k/powerlevel10k" (see screenshot). I did this in order to keep my themes organized within my Oh-My-Zsh directory structure. Powerlevel10k is now a theme option that I can easily switch by changing the ZSH_THEME variable in the .zshrc file.

11. After I installed Powerlevel10k and edited the .zshrc file, I I applied the changes with ‘source ~/.zshrc’ and entered the configuration wizard where I customized the appearance.
12. Install zsh-syntax-highlighting: git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
13. edit the .zshrc file and edit the follow line: plugins=(git) to plugins=(git zsh-syntax-highlighting) and then apply the changes (source ~/.zshrc).
14. install NeoVim:  sudo apt update sudo apt install neovim
15.  Clone the Kickstart.nvim Repository: git clone https://github.com/nvim-lua/kickstart.nvim.git ~/.config/nvim
16. sudo add-apt-repository ppa:neovim-ppa/unstable -y
17. sudo apt update
18. sudo apt install make gcc ripgrep unzip git xclip neovim  (I found the last 3 commands from https://github.com/nvim-lua/kickstart.nvim to install and unstable version)         

