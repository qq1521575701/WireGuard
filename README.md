# WireGuard

## 拉取镜像
    docker pull weejewel/wg-easy

## 运行容器
    docker run -d \
      --name wg-easy \
      -e WG_HOST=你的ip \
      -e PASSWORD=1521575701 \
      -e WG_DEFAULT_DNS=8.8.8.8 \
      -e WG_ALLOWED_IPS=10.8.0.0/24 \
      -e WG_PERSISTENT_KEEPALIVE=25 \
      -v ~/.wg-easy:/etc/wireguard \
      -p 51820:51820/udp \
      -p 51821:51821/tcp \
      --cap-add=NET_ADMIN \
      --cap-add=SYS_MODULE \
      --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
      --sysctl="net.ipv4.ip_forward=1" \
      --restart unless-stopped \
      weejewel/wg-easy

## 后台管理
    ip:51821

## port
    51820
