# groff 


## requirements

### debian/ubuntu
```
sudo apt install groff make
```

## generate a document

```
refer -p bibliography <file> | groff -ms -Tpdf > file.pdf
```

## install a vim autocommand

add this to your `~/.vimrc`:
```
if has("autocmd")
  au BufWritePost *.ms !refer -p $(dirname %:p)/biblio %:p |groff -ms -Tpdf > $(echo %:p | sed 's/.ms/.pdf/')
endif
```

if your pdf viewer can read from `stdin` you can replace 

- `$(echo %:p | sed 's/.ms/.pdf/')`  with
- `| tee $(echo %:p | sed 's/.ms/.pdf/') | viewer - `

 to open a render after a buffer has been written.
