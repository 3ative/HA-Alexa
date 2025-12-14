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

<div align="center">

### 💖 Support This Project

Found this useful? Want to say thanks and fuel future creations?

**Your support keeps the creativity flowing!** 🍺✨

<table>
  <tr>
    <td align="center">
      <a href="https://www.buymeacoffee.com/3ative">
        <img src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-Support-yellow.svg?style=for-the-badge&logo=buy-me-a-coffee&logoColor=white" alt="Buy Me A Coffee"/>
        <br/>
        <b>☕ Buy me a Coffee</b>
      </a>
    </td>
    <td align="center">
      <a href="https://www.patreon.com/3ative">
        <img src="https://img.shields.io/badge/Patreon-Become%20a%20Patron-red.svg?style=for-the-badge&logo=patreon&logoColor=white" alt="Patreon"/>
        <br/>
        <b>💖 Join on Patreon</b>
      </a>
    </td>
  </tr>
</table>

**Every contribution helps bring more awesome projects to life!** 🚀

</div>

---
