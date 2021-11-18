# MyELPA (Personal Emacs Package Mirror)

Due to a series of unfortunate events, installing packages from `MELPA` doesn't work on my work Emacs instance (Emacs doesn't use openssl and throws TLS errors, can't build the newest version of Emacs on our OS, etc).

Here is the collection of `*.el` package files (including dependencies) combined into archives which can be manually installed into `~/.emacs.d/packages` by cloning this repo or by importing this mirror to your list of `package-archives` to install via the package manager.

## Usage

### Use Mirror

To gain access to this mirror, simply add the following to your `~/.emacs` file:

```lisp
(add-to-list 'package-archives ("myelpa" . "https://raw.githubusercontent.com/Justintime50/myelpa/main/src/"))
```

### Create Mirror

Use the following tool to craft the mirror locally (must be done from an Emacs instance that can install packages - as is the case on my personal machine.) https://github.com/redguardtoo/elpa-mirror

```bash
mkdir -p ~/myelpa && emacs --batch -l ~/.emacs -l ~/.emacs.d/elpa-mirror.el --eval='(setq elpamr-default-output-directory "~/myelpa")' --eval='(elpamr-create-mirror-for-installed)'
```
