# Install NVChard  IDE 

[https://nvchad.com/](https://nvchad.com/)

``` sh linenums="1"  
sudo dnf install neovim ripgrep

rm -rf ~/.config/nvim
rm -rf ~/.local/state/nvim
rm -rf ~/.local/share/nvim

git clone https://github.com/NvChad/starter ~/.config/nvim && nvim

nvim
```
