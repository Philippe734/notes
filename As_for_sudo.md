#### How to ask sudo password in script?

For one command:
```pkexec bash -c "apt update"```

For many commands:
```
pkexec bash -c "

    apt update

    apt full-upgrade
"
```

Or show another terminal to ask password:
```
xterm -fa 'Monospace' -fs 14 -geometry 150x24 -title "Title of your project" -e '
	echo -e "***\n\nSmall description, begin of your script"
	read
	clear
	# say to ask password
	echo -e "***\n\nPlease, type your password. It's hidden.\n\nsudo apt update..."
	# commands with sudo:
	sudo apt update
        sudo apt full-upgrade
'
```
