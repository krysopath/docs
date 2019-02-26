# docs

A general src dir for automated document generation


## requirements

### debian/ubuntu
```
apt install groff make
```

## generate a document

```
```

## install a vim autocommand

add this to your `~/.vimrc`:
```
if has("autocmd")
  au BufWritePost *.ms !refer -p bibliography %:p |groff -ms -Tpdf | tee %:p.pdf | zathura -
endif
```
> if your xdg-open pdf viewer can read from `stdin` you can use that instead of zathura
else you need to install `zathura` for this command to work.
