## Список IP-адресов выборочного роутинга для проекта XKeen

Подробнее о проекте XKeen по ссылке <https://forum.keenetic.com/topic/16899-xray-на-entware-xkeen/>

Telegram <https://t.me/+SZWOjSlvYpdlNmMy>

Сборка содержит IP-подсети Cloudflare и Telegram, и рекомендуется, как дополнение к списку доменов <https://github.com/jameszeroX/zkeen-domains>

## Ссылка для загрузки крайней версии

- <https://github.com/jameszeroX/zkeen-ip/releases/latest/download/zkeenip.dat>

## Пример использования

```json
{
  "routing": {
    "domainStrategy": "IPOnDemand",
      "rules": [
      {
        "domain": [
          "ext:zkeen.dat:domains"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "block",
        "type": "field"
      },
      {
        "ip": [
          "ext:zkeenip.dat:cloudflare",
          "ext:zkeenip.dat:telegram"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "block",
        "type": "field"
      },
      {
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "direct",
        "type": "field"
      }
    ]
  }
}
```
