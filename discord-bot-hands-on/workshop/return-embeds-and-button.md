# Return Embeds and Button

อยากให้มันแสดงอย่างอื่นที่ไม่ใช่ text ได้ไหม? ได้! เราสามารถใช้ Embed และ Button ในการแสดงผลที่สวยงามขึ้นได้นะ

### Embed

ก่อนอื่นเพิ่ม EmbedBuilder กันก่อน

```javascript
const { ..., EmbedBuilder } = require('discord.js');
```

ไปที่เรา handle คำสั่ง animal

```javascript
// Reply command
client.on('interactionCreate', async interaction => {
   ...
   if (commandName === 'ping') {
       ...
   } else if (commandName === 'animal') {
       const animalInput = interaction.options.getString('animal');
       const animalOutput = animals.find(animal => animal.name_en == animalInput);
       const embed = new EmbedBuilder()
            .setColor(0x0099FF)
            .setTitle(animalOutput.name_en)
            .setURL(animalOutput.reference_url)
            .setAuthor({ 
                name: 'zookeeper', 
                iconURL: "https://i.imgur.com/dxeXsqc.jpeg", 
                url: 'https://khaokheow.zoothailand.org/intro.php' 
            })
            .setDescription(animalOutput.description)
            .setThumbnail(animalOutput.image_url)
            .addFields(
                 { name: 'Scientific Name', value: animalOutput.scientific_name, inline: true },
                 { name: 'Food', value: animalOutput.diet },
                 { name: 'Zoo Place', value: animalOutput.place, inline: true },
            )
            .setImage(animalOutput.image_url)
            .setTimestamp()
            .setFooter({ text: '❤️', iconURL: "https://i.imgur.com/dxeXsqc.jpeg" }
       );   
       await interaction.reply({ embeds: [embed] });
    }
});

```

มาอธิบายแต่ละส่วนกัน

<figure><img src="../../.gitbook/assets/Screenshot 2567-12-13 at 09.50.31.png" alt=""><figcaption></figcaption></figure>

* `setColor()`: set สีของตัว Embed ซึ่งจะแสดงเป็นเส้นด้านซ้าย
* `setTitle()`: ใส่ title ในที่นี้เป็น Tiger
* `setURL()`: กดที่ title แล้วไปหน้าเว็บไหนต่อ
* `setAuthor()`: ส่งโดยใคร ในที่นี้ชื่อ zookeeper เป็นรูปหมูเด้ง กดที่ author แล้วไปหน้าเว็บไหนต่อ
* `setDescription()`: ใส่รายละเอียด ในที่นี้บอกรายละเอียดเสือโคร่ง
* `setThumbnail()`: รูป thumbnail ซึ่งจะแสดงที่มุมขวาล่าง
* `addFields()`: เพิ่มการแสดง text ในส่วนหัวข้อย่อย ในที่นี้จะเป็น Scientific Name, Food และ Zoo Place
* `setImage()`: ใส่รูปใหญ่ ๆ ด้านล่าง
* `setTimestamp()`: บอกว่าข้อความนี้ถูกส่งมาเวลาไหน
* `setFooter()`: ด้านล่างจะแสดง text หรือ icon อะไร

เกี่ยวกับ Embed สามารถอ่านเพิ่มเติมได้[ที่นี่](https://discordjs.guide/popular-topics/embeds.html#embed-preview)

### Button



เพิ่ม Button กัน เพิ่ม `ButtonBuilder`, `ActionRowBuilder`, `ButtonStyle`

```javascript
const { ..., ButtonBuilder, ActionRowBuilder, ButtonStyle} = require('discord.js');

// Reply command
client.on('interactionCreate', async interaction => {
   ...
   if (commandName === 'ping') {
       ...
   } else if (commandName === 'animal') {
       const animalInput = interaction.options.getString('animal');
       const animalOutput = animals.find(animal => animal.name_en == animalInput);
       const embed = new EmbedBuilder()
            .setColor(0x0099FF)
            .setTitle(animalOutput.name_en)
            .setURL(animalOutput.reference_url)
            .setAuthor({ 
                name: 'zookeeper', 
                iconURL: "https://i.imgur.com/dxeXsqc.jpeg", 
                url: 'https://khaokheow.zoothailand.org/intro.php' 
            })
            .setDescription(animalOutput.description)
            .setThumbnail(animalOutput.image_url)
            .addFields(
                 { name: 'Scientific Name', value: animalOutput.scientific_name, inline: true },
                 { name: 'Food', value: animalOutput.diet },
                 { name: 'Zoo Place', value: animalOutput.place, inline: true },
            )
            .setImage(animalOutput.image_url)
            .setTimestamp()
            .setFooter({ text: '❤️', iconURL: "https://i.imgur.com/dxeXsqc.jpeg" }
       );
       const button = new ButtonBuilder()
            .setLabel('ข้อมูลเพิ่มเติม')
            .setStyle(ButtonStyle.Link)
            .setURL(animalOutput.reference_url);
       const row = new ActionRowBuilder().addComponents(button);
       await interaction.reply({ embeds: [embed], components: [row] });
    }
});

```

* `setLabel()`: เราอยากให้แสดง text อะไร
* `setStyle()`: style ของปุ่ม ในที่นี้คลิกเพื่อเข้าหน้า website จึงเป็น ButtonStyle.Link
* `setURL()`: เราอยากให้เปิดหน้าเว็บไหน

ตอนที่ bot reply ให้แสดง Embed และสร้าง component row ที่ข้างในมี Button ที่เราเพิ่งสร้างนั่นเอง

เกี่ยวกับ Button อ่านเพิ่มเติมได้[ที่นี่](https://discordjs.guide/message-components/buttons.html#building-buttons)

