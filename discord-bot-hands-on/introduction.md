---
description: >-
  หลาย ๆ คนคงเคยเล่น หรืออยู่ตาม community บน Discord กันมาบ้างแล้ว
  บล็อกนี้จะเล่าการทำ Discord Bot ตั้งแต่สร้างบอทก่อน และเขียน function
  การทำงานอย่างง่ายกัน
cover: ../.gitbook/assets/discord-bot-101.png
coverY: 0
---

# Introduction

เป็น hands-on ของ session "**Discord Bot from my Experience: Learn by Doing**" ที่งาน "National Coding Day 2024: workshop day"

Slide: [https://docs.google.com/presentation/d/1VVan98YNYIRvQkCbw6HmZvxM-bIeojawGDnhCELMU\_o/edit?usp=sharing](https://docs.google.com/presentation/d/1VVan98YNYIRvQkCbw6HmZvxM-bIeojawGDnhCELMU_o/edit?usp=sharing)

Github: [https://github.com/mikkipastel/discord-bot-workshop](https://github.com/mikkipastel/discord-bot-workshop)

<figure><img src="../.gitbook/assets/discord-bot-101.png" alt=""><figcaption></figcaption></figure>

### Discord คืออะไร?

เป็นแอพพลิเคชั่นหนึ่งในการสื่อสารกับเพื่อน ๆ เป็นที่นิยมในวงการเกมส์ คริปโต developer และบางที่ใช้ทำงานด้วยนะ

feature หลัก ๆ ที่ใช้กันมี

* **Text Channel**: แบ่งเป็นห้องพูดคุยต่าง ๆ
* **Voice Channel**: เป็นห้องพูดคุยเสียง สามารถเปิดกล้องเพื่อ video call และ stream จอได้

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcMvT_X0P7i0G_L_9z7qfpiWNJIP4bTH4IuMkdGYReCeu_j_l-QM2FIcjt4l-6K1fVLyfiHpDTcAsJKbjJKdjoqNLxFOi2kGpGdiKZcVCpDyCvDH3i7-cbtza5hpgEJa81dbhOX=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUf_j2Wm1mVyBQ_4FbT5gKjNfKIMPSbtgnyOqY5MQDyoZJNG0L1SQMOwE21dppXGxG2UHvXJoE-hr6JcyFzVSUQGna8_M6uZd5UlgyZ9ZRxSBoKsH2qzgCAjeerfjhRR6bFsRHW2Mg=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt="" width="563"><figcaption></figcaption></figure>

* **Stage**: เหมือน Clubhouse เลย ที่มี function ยกมือขอขึ้นพูด และมี feature อื่น ๆ เหมือน Voice Channel

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUd3eUrwZFz9cGvxOFEm7fYelX5fN0lrBDU4vVuxbNWdy6b62OVmZhlPCI--tnpoTsRs5YZYZdGZ6LvTdiHXg384pgWPHzZdIkr_EZe3JdrZfCsoUTM5_5sdi5bJ-keKrRXSkEcb4g=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt="" width="563"><figcaption></figcaption></figure>

และรองรับในหลาย ๆ อุปกรณ์ ไม่ว่าจะเป็น PC, MacOS, iOS, Android

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUfXZ3parj9prdMNziAERjqYSe6APSKVKGsM5knQ-4V6kPARx8rhglQlUrpHUPTfhCotc075TAVI88k9P57EAzfse0LRJCCk9caNQdgWkDOCLcesxYCURqXVWeStX-LMSr11uk8QHA=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt="" width="563"><figcaption></figcaption></figure>

และเชื่อว่าหลาย ๆ คนน่าจะใช้ได้ Discord ตอนที่ MidJourney กำลังดัง ซึ่งในนั้นก็เป็น Discord bot ด้วยเช่นกัน

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUesHBqfRy-EuVsIR6425p9Qvpe6tMKKbTUXyxhFZTMdSchjecEH6CzqCuiX3dckz7w9zYYrD_MHRxKAOyg6wA86HHBSvahGAcP5OzgBdQ7eLdRMjzfxtAHRzpczlvku-LAWxvHSvw=s2048?key=zouhIV8Fq_fCPxgqccmT5w" alt=""><figcaption></figcaption></figure>

