# HA-Alexa
Code I used for Alexa and Node-Red

"node-red-contrib-amazon-echo": https://flows.nodered.org/node/node-red-contrib-amazon-echo

Main Video "**Home Assistant: Controlling Devices with Alexa**": https://youtu.be/l1as3tYVy64


- **Basic On/Off Code**
```yaml
if (msg.payload === "on") msg.payload = {"service":"turn_on"}
if (msg.payload === "off") msg.payload = {"service":"turn_off"}
return msg
```

- **Full Code for Lighting**
```
if (msg.payload === "on")
msg.payload =
{
    "service": "turn_on",
    data:
    {"rgb_color": msg.rgb, "brightness": msg.bri}
};
if (msg.payload === "off") msg.payload = {
    "service":"turn_off"
};
else if (msg.colormode === "ct")
msg.payload =
{
    "service": "turn_on",
    data:
    {"rgb_color": [254,254,254], "brightness": msg.bri}
}
return msg
```
Alternatively, technowizard79 came up with this solution: https://github.com/technowizard79/Node-Red-Alexa-RGBW-Code
---
### 🤝 Found this useful, want to say 'Thanks' and support my efforts. CHEERS🍺
| Buy me a Coffee | PATREON |
|-----------------|---------|
| [![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-donate-yellow.svg?style=flat-square&logo=buy-me-a-coffee)](https://www.buymeacoffee.com/3ative) | [![Patreon](https://img.shields.io/badge/Patreon-support-red.svg?style=flat-square&logo=patreon)](https://www.patreon.com/3ative) |
---
