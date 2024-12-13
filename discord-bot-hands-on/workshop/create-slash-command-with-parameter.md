# Create Slash Command with Parameter

ใน Github repo นี้มีไฟล์ json ที่ชื่อว่า `animal.json` เตรียมไว้ให้ เราจะนำไฟล์นี้มาเล่นกัน

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUd7om9QP6vO6Rj2xgtB8tJmbLj-TIon0f_66M7m-26ERVcRWlSWaqzzlALOvVMmL4pslfITLcnGsjFoP8CD1AxMeSFeyh5YLaw_100qGBVju4eOpgAINy0_8ruOwrcciJwc-VvxTQ=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt=""><figcaption></figcaption></figure>

กลับไปที่ `server.js` เรามาเพิ่มคำสั่งใหม่กัน

```javascript
// server.js
// Import dependency
const { ..., SlashCommandBuilder } = require('@discordjs/builders');
const { REST } = require('@discordjs/rest');

// Create slash command
const commands = [
   new SlashCommandBuilder()
       .setName('ping')
       .setDescription('Replies with Pong!'),
   // NEW: new command
   new SlashCommandBuilder()
       .setName('animal')
       .setDescription('Encyclopedia animal')
       .addStringOption(option =>
           option.setName('animal')
               .setDescription('role category')
               .setRequired(true)
               .addChoices(
                   { name: 'Hippopotamus', value: 'Hippopotamus'},
                   { name: 'Tiger', value: 'Tiger'},
                   { name: 'Asian Elephant', value: 'Asian Elephant'},
                   { name: 'Capybara', value: 'Capybara'},
               )
       )
 ].map(command => command.toJSON());
 
// NEW: Load json static beta
const animals = require('./data/animal.json');

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
   } else if (commandName === 'animal') {
       // NEW: add new command
       const animalInput = interaction.options.getString('animal');
       const animalOutput = animals.find(animal => animal.name_en == animalInput);
       await interaction.reply(animalOutput.name_th);
    }

});

```

* เราเพิ่มคำสั่งที่ชื่อว่า animal และต้องกรอก parameter ด้วย 4 ตัวเลือก คือ Hippopotamus, Tiger, Asian Elephant และ Capybara
* เอา `animal.json` เข้ามาเพื่อเรียกใช้ข้อมูล
* เพิ่ม condition การจัดการคำสั่ง animal โดยเราดึง parameter ที่ user ใส่เข้ามา จากนั้นดึงข้อมูลจาก `animal.json` แล้วมาเทียบชื่อ จากนั้นให้ bot reply เป็นชื่อสัตว์ภาษาไทยออกมา

เมื่อ code ทำงานใหม่ กลับไปดูที่ Discord พบว่าบอทของเราเพิ่มคำสั่ง animal มาแล้วพร้อมตัวเลือกทั้ง 4

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-12 at 22.06.46.png" alt=""><figcaption></figcaption></figure>





