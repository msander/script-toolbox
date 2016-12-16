# script-toolbox

## Resize all images in the current folder
```bash
for file in *.jpg; do convert "$file" -quality 95 -resize 1280x720 "$file"; done
```

## Convert videos for serving using HLS (m3u8 playlist)
[HLS-Stream-Creator](https://github.com/bentasker/HLS-Stream-Creator/)

## Convert PDF to PNG
```bash
convert -density 300 input.pdf[0] output.png
```

## Make Postgres Dump as SQL
```bash
sudo -u postgres pg_dump --no-owner --no-acl --format plain --column-inserts --attribute-inserts dbname > dump.sql
```
