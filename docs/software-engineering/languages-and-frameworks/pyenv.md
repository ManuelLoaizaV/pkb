# pyenv

## Installing pyenv

To install `pyenv` on Debian or Ubuntu-based Linux distributions,
you have to install several libraries and packages necessary for building Python from scratch.
Enter the following command into your terminal to install all necessary packages:

```shell
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python-openssl \
git
```

To install `pyenv` you can clone it directly from the [GitHub](https://github.com/pyenv/pyenv) repository:

```shell
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

After cloning it,
you need to enter the following commands to add `pyenv` to your `$PATH`
and start it when a new terminal is opened (if you use a different shell than bash, you have to change `~/.bashrc` accordingly):

```shell
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
```

## Using pyenv

After you successfully installed `pyenv`,
it is time to take a look at the different commands that `pyenv` offers to manage different Python versions.

Probably the most important command is

```shell
pyenv install [PYTHON_VERSION]
```

With this command, you can install a specific Python version on your system.
To see all versions that are available to install, enter

```shell
pyenv install -l
```

This will print out a very long list on your terminal (depending on your operating system)
of Python versions you can install.
And it is not just the standard CPython versions.
There is also [pypy](https://en.wikipedia.org/wiki/PyPy),
which is an implementation of Python in Python itself.
Or `anaconda`, which is very popular in sciences and data mining.
Pick your preferred Python version and use `pyenv install` to install it on your system.

To see which versions you have already installed, enter the following command into your terminal:

```shell
pyenv versions
```

This command will list all the Python versions that you can choose from `pyenv`.
The version that is currently active has an asterisk (`*`) in front of it:

```shell
  system
  3.10.0rc1
* 3.9.6 (set by /home/manuel/.pyenv/version)
  pypy3.7-7.3.5
```

If you want to know which Python version is currently active in your shell, just type

```
pyenv version
```

Now, after you have installed several different versions,
how do you set a specific version?
To select a default Python version that is active when you open a new terminal,
you use the `global` command:

```shell
pyenv global [PYTHON_VERSION]
```

Ensure to enter the exact name of the installed Python version shown when you enter pyenv versions.
Alternatively to `pyenv global [PYTHON_VERSION]`,
you can also set an environment variable (Unix only) `PYENV_VERSION` with

```shell
export PYENV_VERSION=[PYENV_VERSION]
```

If you want to set a specific Python version for your current terminal session, use

```shell
pyenv shell [PYTHON_VERSION]
```

This will set the Python version only as long as your session is active.
So after you close your terminal, everything is back to default.

To set a project Python version that is active as soon as you `cd` into the project directory,
enter the following when you are inside of the project’s root directory:

```shell
pyenv local [PYTHON_VERSION]
```

This will create the file `.python-version` that contains the `[PYTHON_VERSION]`.
You can even check that by entering `pyenv versions`, it will tell you based on what setting the currently active Python version was selected.

Of course, there are more `pyenv` commands,
but I won’t go into those in this file. You can find a complete command reference over [here](https://github.com/pyenv/pyenv/blob/master/COMMANDS.md).