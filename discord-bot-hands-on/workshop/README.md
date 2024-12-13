# Workshop

### Fork Github Repo

ก่อนอื่นมา setup project กัน โดย fork repo นี้จาก Github มาก่อน

{% embed url="https://github.com/mikkipastel/discord-bot-workshop" %}

จากนั้นเปิด CodeSpaces ในนั้นรองรับ node 20 แล้วด้วยนะ เราใช้ library Discord version ล่าสุดเลย ที่รองรับ node 18

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 20.33.24.png" alt=""><figcaption></figcaption></figure>

หน้าตาของ Codesapces

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUe3P_5Vc73h6gb6zxOON9--s50DSsih7yqsKu84J3127q8OU97dPv26INP7dQImiT2RoeZYEgEB1PFVeQKc-q-2u-by7KQyeWtnGdyZ46SCXNeGf7mJPSr0KeTeAEG4cgZzuvjx=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt=""><figcaption></figcaption></figure>

อธิบายโค้ดกันก่อน

```javascript
// server.js
require('dotenv').config();

// Import dependency
const { Client, Events, GatewayIntentBits } = require('discord.js');

// Create a new client instance
const client = new Client({ intents: [GatewayIntentBits.Guilds] });

// If ready, run this node
client.once(Events.ClientReady, readyClient => {
   console.log(`Ready! Logged in as ${readyClient.user.tag}`);
});

// Log in to Discord with your client's token
client.login(process.env.token);

```

* Import library discord.js เรียก `Client`, `Events`, `GatewayIntentBits` สามอันนี้เป็น default ที่เราต้องเรียกใช้
* สร้าง client instance ที่เป็นตัว intent เป็น `GatewayIntentBits.Guilds` เป็นตัวที่จำเป็นในการทำงาน
* เมื่อ client พร้อมแล้ว ให้ run `client.once()`
* และอย่าลืม logic ก่อนใช้งาน

### สร้าง .env file

ต่อมาสร้างไฟล์ .env แล้วใส่ตามนี้

```
// .env
token=...
clientId=...
guildId=...

```

* `token` ไปที่ Bot แล้วกดปุ่ม _Reset Token_ แล้วเราจะได้ token มาใช้

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 20.47.52.png" alt=""><figcaption></figcaption></figure>

* `clientId` เอามาจาก APPLICATION ID ที่ได้หลังจากแอพเสร็จ

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 20.48.13.png" alt=""><figcaption></figcaption></figure>

* `guildId` คือ server id ที่เราต้องการเทส วิธีการเอาไปใช้ ไปที่ server setting -> Widget แล้วทำการ copy ออกมา

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 20.48.48.png" alt=""><figcaption></figcaption></figure>

สุดท้ายพิมพ์ command นี้เพื่อ install package ต่าง ๆ เข้ามาในโปรเจกต์

```
npm install
```



