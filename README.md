# go-gen-test

[![License GPL 3](https://img.shields.io/badge/license-GPL_3-green.svg)](http://www.gnu.org/licenses/gpl-3.0.txt)
[![MELPA](https://melpa.org/packages/go-gen-test-badge.svg)](https://melpa.org/#/go-gen-test)

`go-gen-test` is package for generating tests for go code from
emacs. It is simple wrapper around [`gotests`](https://github.com/cweill/gotests).

[![asciicast](https://asciinema.org/a/142648.png)](https://asciinema.org/a/142648)

## Usage

### Commands

#### `go-gen-test-dwim`
Generate tests for functions you want to.
If you call this function while region is active it extracts
functions defined in this region and generate tests for it.
Else it generates tests for exported or all functions.
You can customize this behavior with `go-gen-test-default-functions`.

#### `go-gen-test-all`
Generate tests for all functions.

#### `go-gen-test-exported`
Generate tests for all exported functions.

### Customization

<kbd>M-x</kbd> `customize-group` <kbd>Enter</kbd> `go-gen-test` <kbd>Enter</kbd>

## Setup

You can now install package `go-gen-test` from
[MELPA](https://melpa.org/#/getting-started). Just `M-x`
`package-install`<kbd>Enter</kbd> `go-gen-test` <kbd>Enter</kbd>.

Also you should install
[`gotests`](https://github.com/cweill/gotests):

``` shell
$ go get -u github.com/cweill/gotests/...
```

Then you can bind needed commands to preffered keys:

``` emacs-lisp
(defun my-go-gen-test-setup ()
  "My keybindings for generating go tests."
  (interactive)
  (local-set-key (kbd "C-c C-g") #'go-gen-test-dwim))

(add-hook 'go-mode-hook #'my-go-gen-test-setup)
```
