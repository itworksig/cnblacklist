# cnblacklist

给 **Clash / Clash Meta / OpenClash** 用的分流规则，按公司拆成多个文件。

| 文件 | 覆盖 |
|------|------|
| [`meta.txt`](meta.txt) / [`meta.yaml`](meta.yaml) | Facebook、Instagram、WhatsApp、Messenger、Threads、Oculus、Workplace 等 |
| [`google.txt`](google.txt) / [`google.yaml`](google.yaml) | Google、YouTube、Gmail、Play、Android、Chrome、Firebase 等 |
| [`telegram.txt`](telegram.txt) / [`telegram.yaml`](telegram.yaml) | Telegram 官网、Web、CDN、Bot API、Telegraph、Fragment 等 |
| [`openai.txt`](openai.txt) / [`openai.yaml`](openai.yaml) | ChatGPT、OpenAI API、Sora |
| [`x.txt`](x.txt) / [`x.yaml`](x.yaml) | X、Twitter、短链、图片视频 CDN、xAI / Grok |
| [`claude.txt`](claude.txt) / [`claude.yaml`](claude.yaml) | Claude、Anthropic 控制台 / API |

`.txt` 是 classical 文本（一行一条）。`.yaml` 是同样内容的 `payload` 格式。规则里**不写策略名**，引用时自己指定 `PROXY` 或 `DIRECT`。

## OpenClash

配置文件管理 → 在线订阅 / 自定义 → 或直接写进 Mihomo 配置：

```yaml
rule-providers:
  meta:
    type: http
    behavior: classical
    format: text
    url: "https://raw.githubusercontent.com/itworksig/cnblacklist/main/meta.txt"
    path: ./rule_provider/meta.txt
    interval: 86400
  google:
    type: http
    behavior: classical
    format: text
    url: "https://raw.githubusercontent.com/itworksig/cnblacklist/main/google.txt"
    path: ./rule_provider/google.txt
    interval: 86400
  telegram:
    type: http
    behavior: classical
    format: text
    url: "https://raw.githubusercontent.com/itworksig/cnblacklist/main/telegram.txt"
    path: ./rule_provider/telegram.txt
    interval: 86400
  openai:
    type: http
    behavior: classical
    format: text
    url: "https://raw.githubusercontent.com/itworksig/cnblacklist/main/openai.txt"
    path: ./rule_provider/openai.txt
    interval: 86400
  x:
    type: http
    behavior: classical
    format: text
    url: "https://raw.githubusercontent.com/itworksig/cnblacklist/main/x.txt"
    path: ./rule_provider/x.txt
    interval: 86400
  claude:
    type: http
    behavior: classical
    format: text
    url: "https://raw.githubusercontent.com/itworksig/cnblacklist/main/claude.txt"
    path: ./rule_provider/claude.txt
    interval: 86400

rules:
  - RULE-SET,telegram,PROXY
  - RULE-SET,meta,PROXY
  - RULE-SET,google,PROXY
  - RULE-SET,openai,PROXY
  - RULE-SET,x,PROXY
  - RULE-SET,claude,PROXY
```

用 yaml 时把 `format` 改成 `yaml`，URL 改成对应的 `.yaml`。

## Clash Verge / Mihomo

同上。也可把 `.txt` 里的行复制到自定义规则。

## 直链

```
https://raw.githubusercontent.com/itworksig/cnblacklist/main/meta.txt
https://raw.githubusercontent.com/itworksig/cnblacklist/main/google.txt
https://raw.githubusercontent.com/itworksig/cnblacklist/main/telegram.txt
https://raw.githubusercontent.com/itworksig/cnblacklist/main/openai.txt
https://raw.githubusercontent.com/itworksig/cnblacklist/main/x.txt
https://raw.githubusercontent.com/itworksig/cnblacklist/main/claude.txt
```
