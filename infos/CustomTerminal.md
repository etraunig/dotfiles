# Zsh:
Install git, curl and zsh:
	
	sudo apt install git curl zsh

And then install OhMyZsh (and agree tochange the default shell to Zsh)
	
	sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

Now restart to apply the changes.

# Alacritty:
Install from terminal, and not the built-in store:
	
	sudo apt install Alacritty

To change the default terminal to Alacritty, use the next command and select the Alacritty option (usually /usr/bin/alacritty):
	
	sudo update-alternatives --config x-terminal-emulator

# Starship:
Start by choosing and downloading a nerdfont from
	
	https://www.nerdfonts.com/

And install it with the following commands:

	mv ~/Downloads/Font.zip ~/.local/share/fonts &&
	unzip ~/.local/share/fonts/Font.zip &&
	rm  ~/.local/share/fonts/Font.zip &&
	fc-cache -fv

Change the Alacritty configuration file ```(~/.config/alacritty/alacritty.toml)``` to use this nerdfont (example below using JetBrainsMono)

	[font]
	size = 11

	[font.normal]
	family = "JetBrainsMono Nerd Font"
	style = "Regular"

	[window]
	opacity = 0.95

Get a starship preset file (or one from the files folder) and place it at ```~/.config/starship.toml```, you can do it using nano to just copy-paste everything

	nano ~/.config/starship.toml

And finally, add these to the end of your Zsh configuration file (```(~/.zshrc)```)

	# ~/.zshrc
	eval "$(starship init zsh)"