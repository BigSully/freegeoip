





# start geoip server
```
cd cmd/freegeoip/
go build
export KEY=<Your Maxmind License Key>
PORT=8090
./freegeoip -http :$PORT -use-x-forwarded-for -public ./public -quota-backend map -quota-max 0
curl http://localhost:$PORT/json/8.8.8.8
```


# build linux binary
```
GOARCH=amd64 GOOS=linux CGO_ENABLED=0 go build -ldflags '-w -s' -o freegeoip-linux
```


```
## for original
export INITIAL_DATABASE_URL="https://download.maxmind.com/app/geoip_download?edition_id=GeoLite2-City&suffix=tar.gz&license_key=nZnOPrucKQ3t1chO"
./freegeoip -http :8090 -use-x-forwarded-for -public ./public -quota-backend map -quota-max 0
```

# merge & customization  
2020-01-09 - https://github.com/voyagin/freegeoip  
2018-07-02 - https://github.com/apilayer/freegeoip