# lian

docker run -d \
 --name subapi \
 --restart always \
 -p 25501:25500 \
 --sysctl net.ipv6.conf.all.disable_ipv6=1 \
 -e TZ=Africa/Abidjan \
 -e HTTP_PROXY=http://192.168.3.8:7890 \
 -e HTTPS_PROXY=http://192.168.3.8:7890 \
 -e http_proxy=http://192.168.3.8:7890 \
 -e https_proxy=http://192.168.3.8:7890 \
 -e NO_PROXY=127.0.0.1,localhost \
 -v /root/subapi/pref.toml:/base/pref.toml:ro \
 -v /root/subapi/cache:/base/cache \
 asdlokj1qpi23/subconverter:latest
