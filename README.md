# Steps for Installing Virtual Machine

These are the steps I followed:

1. From [this link](https://cdimage.ubuntu.com/jammy/daily-live/current/), I installed the 64-bit ARM desktop image. I used UTM and installed the ISO. I had some trouble with this, but after what I thought was a loaded image, I had to find the icon on my Linux desktop and load it from there. I then cleared the ISO image and restarted.

2. **Update and upgrade**:
    ```bash
    sudo apt update
    sudo apt upgrade
    ```

3. **Install Clang**:
    ```bash
    sudo apt install clang
    ```

4. **Install GCC**:
    ```bash
    sudo apt install gcc g++
    ```
    I installed both Clang and GCC for more flexibility down the road if needed.

5. **Install Zsh**:
    ```bash
    sudo apt install zsh
    ```

6. **Set Zsh as Default Shell**:
    ```bash
    chsh -s $(which zsh)
    ```

    I restarted my VM and now have Zsh as my default terminal. I didn’t have any Zsh startup files and was presented with options for creating these. I chose to “Populate your `~/.zshrc` with the configuration recommended by the system administrator and exit (you will need to edit the file by hand, if so desired).”

7. **Install Curl**:
    ```bash
    sudo apt install curl
    ```

8. **Install Git**:
    ```bash
    sudo apt install git
    ```

9. **Install Oh My Zsh**:
    ```bash
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```

10. **Install Powerlevel10k Theme**:
    - Command used:
      ```bash
      git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
      ```
    - I used a command to clone the Powerlevel10k repository into the custom themes directory of Oh My Zsh. I then edited my `.zshrc` file to set:
      ```bash
      ZSH_THEME="powerlevel10k/powerlevel10k"
      ```
    - I did this in order to keep my themes organized within my Oh My Zsh directory structure. Powerlevel10k is now a theme option that I can easily switch by changing the `ZSH_THEME` variable in the `.zshrc` file.

11. After I installed Powerlevel10k and edited the `.zshrc` file, I applied the changes with:
    ```bash
    source ~/.zshrc
    ```
    Then I entered the configuration wizard where I customized the appearance.

12. **Install zsh-syntax-highlighting**:
    ```bash
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
    ```

13. **Edit the `.zshrc` File**:
    - Change the line `plugins=(git)` to:
      ```bash
      plugins=(git zsh-syntax-highlighting)
      ```
    - Apply the changes:
      ```bash
      source ~/.zshrc
      ```

14. **Install NeoVim**:
    ```bash
    sudo apt update
    sudo apt install neovim
    ```

15. **Clone the Kickstart.nvim Repository**:
    ```bash
    git clone https://github.com/nvim-lua/kickstart.nvim.git ~/.config/nvim
    ```

16. **Add the Neovim PPA**:
    ```bash
    sudo add-apt-repository ppa:neovim-ppa/unstable -y
    ```

17. **Update the Package List**:
    ```bash
    sudo apt update
    ```

18. **Install Additional Tools**:
    ```bash
    sudo apt install make gcc ripgrep unzip git xclip neovim
    ```
    I found the last 3 commands from [Kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim) to install an unstable version.
