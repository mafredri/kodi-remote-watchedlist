# kodi-remote-watchedlist

This is a fork of [SchapplM/xbmc-addon-service-watchedlist](https://github.com/SchapplM/xbmc-addon-service-watchedlist) which allows performing WatchedList syncing against a remote Kodi instance using a remote WatchedList MySQL database. It was quickly put together so currently only supports MySQL but it would be trivial to add support for local files (sqlite3).

## Why?

Because MrMC does not support plugins and my previous project ([mafredri/kodi-watchedlist-sync](https://github.com/mafredri/kodi-watchedlist-sync)) only supported one-way sync.

## Installation and running

See configuration before running.

```
git clone https://github.com/mafredri/kodi-remote-watchedlist
cd kodi-remote-watchedlist
pip3 install -r requirements.txt
python3 manual.py
```

## Configuration

Configuration is done via environment variables:

```
export MYSQL_HOST=my.mysql.host
export MYSQL_PORT=3307
export MYSQL_DB=watchedlist
export MYSQL_USER=kodi
export MYSQL_PASS="supersecret password"

export KODI_URL="http://my.kodi.host:8080/jsonrpc"
export KODI_USER=kodi
export KODI_PASS=kodi
```

## Docker

TODO.

## Notes

- The database structure was slightly altered, dates are now stored as unix (integers) instead of timestamps for compatibility with [mafredri/kodi-watchedlist-sync](https://github.com/mafredri/kodi-watchedlist-sync)
