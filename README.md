## Список IP-адресов выборочного роутинга для проекта XKeen

Подробнее о проекте XKeen по ссылке <https://forum.keenetic.com/topic/16899-xray-на-entware-xkeen/>

Telegram <https://t.me/+SZWOjSlvYpdlNmMy>

Сборка содержит IP-подсети Cloudflare, Telegram, России, Беларуси и Украины, и рекомендуется, как дополнение к списку доменов <https://github.com/jameszeroX/zkeen-domains>

Может использоваться как в режиме "всё напрямую кроме..", так и в режиме "всё через dummy кроме..." Примеры кода ниже.

## Ссылка для загрузки крайней версии

- <https://github.com/jameszeroX/zkeen-ip/releases/latest/download/zkeenip.dat>

## Примеры использования

```json
{
  "routing": {
    "domainStrategy": "IPOnDemand",
      "rules": [
      {
        "domain": [
          "ext:zkeen.dat:bypass"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "direct",
        "type": "field"
      },
      {
        "domain": [
          "ext:zkeen.dat:domains",
          "ext:zkeen.dat:politic",
          "ext:zkeen.dat:youtube",
          "ext:zkeen.dat:other"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "dummy",
        "type": "field"
      },
      {
        "ip": [
          "ext:zkeenip.dat:cloudflare",
          "ext:zkeenip.dat:telegram",
          "ext:zkeenip.dat:google",
          "ext:zkeenip.dat:ua"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "dummy",
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
```json
{
  "routing": {
    "domainStrategy": "IPOnDemand",
      "rules": [
      {
        "domain": [
          "4pda.ru",
          "abook-club.ru",
          "amdm.ru",
          "avast.ru",
          "imgpng.ru",
          "livesurf.ru",
          "onlinesim.ru",
          "rutracker.ru",
          "pcbway.ru",
          "php.su"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "dummy",
        "type": "field"
      },
      {
        "domain": [
          "regexp:^([\\w\\-\\.]+\\.)su$",
          "regexp:^([\\w\\-\\.]+\\.)ru$",
          "regexp:^([\\w\\-\\.]+\\.)xn--p1ai$",
          "regexp:^([\\w\\-\\.]+\\.)xn--p1acf$",
          "regexp:^([\\w\\-\\.]+\\.)xn--80asehdb$",
          "regexp:^([\\w\\-\\.]+\\.)xn--c1avg$",
          "regexp:^([\\w\\-\\.]+\\.)xn--80aswg$",
          "regexp:^([\\w\\-\\.]+\\.)xn--80adxhks$",
          "regexp:^([\\w\\-\\.]+\\.)xn--d1acj3b$",
          "regexp:^([\\w\\-\\.]+\\.)moscow$",
          "regexp:^([\\w\\-\\.]+\\.)by$"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "direct",
        "type": "field"
      },
      {
        "ip": [
          "ext:zkeenip.dat:ru",
          "ext:zkeenip.dat:by"
        ],
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "direct",
        "type": "field"
      },
      {
        "inboundTag": ["redirect", "tproxy"],
        "outboundTag": "dummy",
        "type": "field"
      }
    ]
  }
}
```
