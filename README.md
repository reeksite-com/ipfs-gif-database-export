# ipfs-gif-database-export

This repository includes exports of the searchable GIF database from https://gif.reeksite.com in an easy to consume JSON format.

Each `export-*.json` file contains at most 1000 GIFs. Exports are numbered, where 0 is the first export and it increases as more GIFs are added to the database.

## Help Us Host GIFs

GIFs are hosted on a distributed network called [IPFS](https://docs.ipfs.tech/). Please consider running your own [Kubo Server](https://docs.ipfs.tech/install/command-line/) and pin the contents of `pins.txt`.

Pin lists may be imported into Kubo with the following command:

```sh
cat pins.txt | xargs -n 1 ipfs pin add
```

Alternatively with a bash script: 

```bash
while IFS= read -r cid; do
    [[ -z "$cid" || "$cid" =~ ^# ]] && continue
    ipfs pin add "$cid"
done < pins.txt
```