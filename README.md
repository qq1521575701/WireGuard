# WireGuard

## 拉取镜像
    docker pull ghcr.io/wg-easy/wg-easy

## 运行容器
    docker run -d \
      --name wg-easy \
      -e WG_HOST=35.241.90.48 \
      -e PASSWORD_HASH='$2a$10$cqPTWsPvRrU6TCODNfMtZu8KV6BiNnoKNYlYa/pWhCsz.twzO5TNa' \
      -e WG_DEFAULT_DNS=1.1.1.1 \
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
      ghcr.io/wg-easy/wg-easy

## 后台管理
    http://ip:51821

## WireGuard UDP 端口
    51820/udp
