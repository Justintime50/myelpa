# MyELPA (Personal Emacs Package Mirror)

Due to a series of unfortunate events, installing packages from `MELPA` doesn't work on my work Emacs instance (Emacs doesn't use openssl and throws TLS errors, can't build the newest version of Emacs on our OS, etc).

Here is the collection of `*.el` package files (including dependencies) combined into archives which can be manually installed into `~/.emacs.d/packages` by cloning this repo or by importing this mirror to your list of `package-archives` to install via the package manager.

## Usage

### Use Mirror

To gain access to this mirror, add the mirror reference to your `package-archives` in your `~/.emacs` file, a basic config may look like this:

```lisp
(require 'package)

(setq package-archives '(("melpa" . "https://melpa.org/packages/")
                         ("myelpa" . "https://raw.githubusercontent.com/Justintime50/myelpa/main/src/")))

(package-initialize)
```

Then run the following to refresh your package list with the packages from the mirror:

```lisp
M-x package-refresh-contents
```

### Create and Update the Mirror

Use the following tool to craft the mirror locally (must be done from an Emacs instance that can install packages - as is the case on my personal machine.)

Tool GitHub: <https://github.com/redguardtoo/elpa-mirror>

```bash
mkdir -p ~/myelpa && emacs --batch -l ~/.emacs -l ~/.emacs.d/elpa-mirror.el --eval='(setq elpamr-default-output-directory "~/myelpa")' --eval='(elpamr-create-mirror-for-installed)'
```
