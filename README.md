# script-toolbox

## Resize all images in the current folder
```bash
for file in *.jpg; do convert $file -quality 95 -resize 1280x720 $file; done
```
