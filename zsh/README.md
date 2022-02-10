# Follow the instruction to setup zsh without ***"oh-my-zsh"*** in WSL Ubuntu.

### *Ensure that the ***"Ubuntu for WSL"*** is [configured](/UbuntuWSL/README.md) properly before proceding.*

Install zsh.
```
sudo apt install zsh -y
```

>**Do not set zsh as default yet.**

*Follow these steps first.*

1. Type zsh in the terminal.

2. Select 2 for now. This will create the zsh_history, zshrc and zcompdump.

3. Type **exit** in the zsh terminal to return to bash terminal.

4. Delete zshrc by navigating to the %home% directory.

5.  Install subversion to enable **svn** command.
    ```
    sudo apt install subversion -y
    ```

6. Use this [link](https://github.com/ChristianChiarulli/Machfiles/tree/master/zsh) to copy its content to the **home** directory. Refer the screenshot to place the files accordingly. ![Screenshot](Screenshot.png#gh-dark-mode-only)
    - For this there are several ways to do it:
        - Paste this on terminal
            ```
            svn export https://github.com/ChristianChiarulli/Machfiles/trunk/zsh
            ```
            ***OR***
            ```
            svn export https://github.com/madhavchoudhary0911/my-configuration-setup/trunk/zsh
            ```
            and remove the "***README.md***" file.
        - This will make **.config** folder and **.zshrc** file in the **%home%** directory.
        - These plugins are already available in the folder.
            - conda-zsh-autocompletions
            - zsh-autopair
            - zsh-autosuggestions
            - zsh-syntax-highlighting

    - Refer [:arrow_down:](https://youtu.be/bTLYiNvRIVI) video to know more.
    [![zsh - create a minimal config (autosuggestions, syntax highlighting etc..) no oh-my-zsh required](https://i.ytimg.com/vi/bTLYiNvRIVI/maxresdefault.jpg)](https://youtu.be/bTLYiNvRIVI?list=LL "zsh - create a minimal config (autosuggestions, syntax highlighting etc..) no oh-my-zsh required")

7. Copy the commands in the zsh terminal.
    **Make sure you are in the home directory.**
    ```
    sudo apt install curl -y
    sudo apt install zip unzip -y
    mkdir .local
    cd .local
    mkdir bin
    cd bin
    ```

8. Make sure you are in %home%/.local/bin. Install ***fnm*** here and return to the home directory once completed.Refer command below to do it.
    ```
    curl -fsSL https://fnm.vercel.app/install | bash -s -- --install-dir $HOME/.local/bin
    cd ..
    cd ..
    curl -fsSL https://fnm.vercel.app/install | bash -s -- --install-dir $HOME/.local/bin --skip-shell
    ```

9. Install ***zoxide***. You can use the following command.
    ```
    curl -sS https://webinstall.dev/zoxide | bash -s -- --install-dir $HOME/.local/bin
    ```

10. Install other necessary packages
    ```
    sudo apt-get install x11-xkb-utils -y
    sudo apt-get install x11-xserver-utils -y
    sudo apt-get install ranger -y
    sudo apt-get install ncdu -y
    ```

11. Install fzf
    ```
    git clone --depth 1 https://github.com/junegunn/fzf.git 
    ~/.fzf
    ~/.fzf/install
    ```

12. Now you can change your default shell to ***ZSH***. In order to do that, put this command in **.bashrc** file.
    ```
    chsh -s $(which zsh)
    ```

# ***Features:***

- **Ctrl + R** to get list of old commands to choose.

- **Ctrl + S** for starting ncdu.
    - Its is a GUI navigator that works within the terminal. (*Use ? to know the controls*.)

- **Ctrl + O** for starting **Ranger**. Ranger is a ***Terminal File Manager***.

- **Ctrl + F** to start **zi**. ***ZI*** is a ***Directory Navigator*** or you can also type **zi** in terminal to get optional directory to navigate.

## ***For competitive programming:***

- **run _filename.cpp_** to compile cpp instantly.

- **rerun _filename.cpp_** to build using sanitizers.
    
Note: ***run*** and ***rerun*** are functions defined by me as I couldn't think of a better name. You can make you own by modifying in the file like [here](https://github.com/madhavchoudhary0911/Setup/blob/eb4d235f1fd9360cc257d1e26addcfd8460fd546/zsh/.config/zsh/.zshrc#L108). Refer [this](https://usaco.guide/general/cpp-command#adding-shortcuts-mac) column of the amazing **UNACO Guide** for concept behind it.
