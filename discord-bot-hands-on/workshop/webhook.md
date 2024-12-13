# Webhook

เราสามารถสร้างบอทที่ยิงข้อความเข้าไปใน text channel บน server ได้นะ โดยใช้ webhook

ไปที่ Server Settings -> Integations -> Create Webhook

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 20.57.23.png" alt=""><figcaption></figcaption></figure>

จากนั้นเข้าไปที่ webhook ที่สร้าง โดยกดที่ตัว webhook เราสามารถใส่ชื่อ รูป เพื่อให้เราจำได้ แล้วก็ channel ที่เราต้องการ แล้วก็ Copy Webhook URL เพื่อเอาไปใช้ต่อ โดยหน้าตัว url นี้ จะเป็น `https://discord.com/api/webhooks/{id}/{token}`

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 21.38.52.png" alt=""><figcaption></figcaption></figure>

กลับไปที่ server.js แล้วเพิ่มโค้ดเหล่านี้

```javascript
// server.js
const { ..., WebhookClient } = require('discord.js');

const webhookClient = new WebhookClient(
    { url: 'https://discord.com/api/webhooks/{id}/{token}'}
);
const webhookClient = new WebhookClient({ id: 'id', token: 'token' });

client.once(Events.ClientReady, readyClient => {
   console.log(`Ready! Logged in as ${readyClient.user.tag}`);

   // send message webhook
   try {
       webhookClient.send({
           username: 'BB-8',
           avatarURL: 'https://i.imgur.com/PHnLYAm.png',
           content: 'Webhook test',
       })
   } catch (error) {
       common.error('Error trying to send: ', error);
   }
});
```

* เพิ่ม `webhookClient` มาด้วย ตอน import library มา
* `webhookClient` สามารถสร้างเพิ่มได้ 2 วิธีด้วยกัน

ใช้ url โดยตรง

<pre class="language-javascript"><code class="lang-javascript"><strong>const webhookClient = new WebhookClient(
</strong>    { url: 'https://discord.com/api/webhooks/{id}/{token}'}
);
</code></pre>

ใช้ id และ token จาก url จาก format นี้ `https://discord.com/api/webhooks/{id}/{token}`

```javascript
const webhookClient = new WebhookClient({ id: 'id', token: 'token' });
```

* ที่ `client.once()` ใส่การส่งข้อความที่ให้ webhook ส่งข้างใน

เมื่อ code ทำงานใหม่ บอทจะส่งข้อความนี้มาที่ text channel ที่เราต้องการ

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcyrANtQgPifZ0ObgTFyUZkYFbPHCqBf7XrkEVc0HsPyAxBeRAu4dqTVH3kJjUtTYNr8uGvFhu1tgVy3p0I0972DdNLCggiao7B2q-9sAkDptg8v9Xhao2PGneABEb9l_DRazKWsw=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt=""><figcaption></figcaption></figure>

เราสามารถส่งข้อความแบบ Embed ได้ด้วยนะ

```javascript
// server.js
client.once(Events.ClientReady, readyClient => {
   console.log(`Ready! Logged in as ${readyClient.user.tag}`);

   // send message webhook
   try {
       const embed = new EmbedBuilder()
           .setTitle('Some Title')
           .setColor(0x00FFFF);

       webhookClient.send({
           username: 'BB-8',
           avatarURL: 'https://i.imgur.com/PHnLYAm.png',
           content: 'Webhook test',
           embeds: [embed]
       })
   } catch (error) {
       common.error('Error trying to send: ', error);
   }
});

```

ผลที่ได้

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUfELXDK1AOdMVDxgiB1f-KxyKEv7n3k8FCCW1_oWHQkho8lLRXNNBVYbrBcougcMDHmWwFCNa01aOlUHQQnuFUmNg5RBPlBLxXBNUqLquGwO_1RvpizYwYmMdJ8D7WSSeUTY6gsUA=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt=""><figcaption></figcaption></figure>

เกี่ยวกับ webhook สามารถอ่านเพิ่มเติมได้[ที่นี่](https://discordjs.guide/popular-topics/webhooks.html)
