# Create First Slash Command

ไปที่ `server.js` เพิ่มโค้ดเหล่านี้กัน

```javascript
// server.js
// Import dependency
const { ..., SlashCommandBuilder } = require('@discordjs/builders');
const { REST } = require('@discordjs/rest');

// Create new slash command
const commands = [
   new SlashCommandBuilder()
       .setName('ping')
       .setDescription('Replies with Pong!')
 ].map(command => command.toJSON());
 
// Register command
const rest = new REST({ version: '10' }).setToken(process.env.token);
rest.put(Routes.applicationGuildCommands(
    process.env.clientId, 
    process.env.guildId
), { body: commands })
    .then(() => console.log('Successfully registered application commands.'))
    .catch(console.error);

// Reply command
client.on('interactionCreate', async interaction => {
   if (!interaction.isChatInputCommand()) return;
   const { commandName } = interaction;

   if (commandName === 'ping') {
       const timeTaken = Date.now() - interaction.createdTimestamp;
       await interaction.reply(`Pong! This message had a latency of ${timeTaken}ms.`);
   }
});

```

* `SlashCommandBuilder` ใช้เพิ่ม command
* `Routes` กับ `REST` ใช้ register command ของเรา
* สร้าง slash command โดยสร้าง `SlashCommandBuilder()` ขึ้นมา ใส่ชื่อ และ description ของคำสั่งนี้ว่าใช้ทำอะไร แล้วเอาทุกคำสั่งไป map เป็น json ในที่นี้ชื่อคำสั่งว่า ping
* register command โดยการสร้าง `REST` ขึ้นมา แล้วใส่ token เข้าไป จากนั้นให้ put คำสั่งทั้งหมดไปยัง server ของ Discord (ทำให้ตอนที่บอทไม่ online เรายังเห็น command นั้นอยู่นั่นเอง!)
* จัดการ reply command โดยดึงชื่อ command จาก interaction แล้วมา compare ถ้าเป็นคำสั่ง ping ให้เอาเวลาตอนนี้หักกับตอนพิมพ์คำสั่ง แล้ว return เป็น text กลับไป

จากนั้นพิมพ์คำสั่งนี้ เพื่อ deploy ขึ้นไป

```
npm run dev
```

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdsOEGibBojIfQBBj3DVTSOWJwkBQZUnMhe2MYEuqsM01_T8l2rll3F-_IvFrqD5x52SIsEqIN4ZPdVUyPXxfSWdkVmJD3GcyitY5uOWO_JoTHv45lEwCpSFF4amhUaUNXNH7j7=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt=""><figcaption></figcaption></figure>

เมื่อ deploy เรียบร้อยแล้วกลับไปดูที่ server พบว่าคำสั่งนี้มีให้เราใช้งานแล้ว

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 21.56.19.png" alt=""><figcaption></figcaption></figure>

ผลที่ได้

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 21.58.58.png" alt=""><figcaption></figcaption></figure>

เพิ่มเติม ถ้าบางครั้งเราต้องรอผลลัพธ์มากกว่า 3 วินาที ใช้คำสั่งนี้ได้นะ user จะได้ไม่รอนานเกินไป

```javascript
// waiting response long time
await interaction.deferReply();
await interaction.editReply(`Pong! This message had a latency of ${timeTaken}ms.`;
```



