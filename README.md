# sshcd

### This is a fork of fraction/sshcd with support for remote command execution

Tired of having to type this janky command to [ssh](http://manpages.ubuntu.com/manpages/saucy/en/man1/ssh.1.html) and [cd](http://manpages.ubuntu.com/manpages/saucy/en/man1/cd.1posix.html) into unfamiliar remote servers?

```sh
ssh -t user@fraction.io "cd /foo/bar; exec \$SHELL --login"
```

Stop it. Connect with SSH and cd (change directory) with one command.

```sh
sshcd user@fraction.io:/foo/bar
```

## Requirements

- Bash shell (the script requires bash, not sh or zsh)
- curl (for installation via provided commands)

## Installation

Add the executable into your PATH and give it execute permissions.

Mac example:

```sh
sudo curl -Lo ~/.local/bin/sshcd https://raw.githubusercontent.com/romanesko/sshcd/refs/heads/master/sshcd
sudo chmod +x ~/.local/bin/sshcd
```

Linux example:

```sh
sudo curl -Lo /usr/local/bin/sshcd https://raw.githubusercontent.com/romanesko/sshcd/refs/heads/master/sshcd
sudo chmod +x /usr/local/bin/sshcd
```

## Usage

The default usage is pretty simple.

```sh
sshcd user@fraction.io:/foo/bar
```

Execute a remote command:

```sh
sshcd user@fraction.io:/foo/bar ls -la
```

The tool supports prepended ssh flags as well:

```sh
sshcd -v user@fraction.io:/foo/bar
```

### Spaces and special characters

Paths and remote commands with spaces or special characters are supported and properly escaped.

### Error handling

If you do not provide a target in the form [user@]host:/path, the script will print usage instructions and exit with an error.

## Support

Please [open an issue](https://github.com/romanesko/sshcd/issues/new) for questions and concerns.

## Contributing

Fork the project, commit your changes, and [open a pull request](https://github.com/romanesko/sshcd/compare/).
