# docs

A general src dir for automated document generation


## requirements

### debian/ubuntu
```
apt install groff make
```

## generate a document

```
refer -p bibliography <file> |groff -ms -Tpdf > file.pdf
```

## install a vim autocommand

add this to your `~/.vimrc`:
```
if has("autocmd")
  au BufWritePost *.ms !refer -p bibliography %:p |groff -ms -Tpdf > %:p.pdf
endif
```
> if your pdf viewer can read from `stdin` you can replace `> %:p.pdf` with `| tee %:p.pdf | viewer - ` to open a render after a buffer has been written.
