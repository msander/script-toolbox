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

## Restore Postgres Backup for other user (execute as superuser "admin")
```bash
# Create superuser if it doesn't exist
sudo -u postgres createuser -s admin

# Restart pg service to force disconnect existing clients
service postgresql restart

echo dropping database
dropdb dbname

echo creating database
createdb -O pguser dbname

echo restoring
psql -w -d dbname -f ./backup.sql > /dev/null
psql -c "REASSIGN OWNED BY admin TO \"dbuser\"" dbname
echo finished restoring
```
