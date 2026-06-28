# thai-humanizer 🇹🇭

Claude skill ที่ลบ "ความเป็น AI" ออกจากข้อความ **ภาษาไทย** ทำให้อ่านลื่นเหมือนคนไทยเขียนจริง

Humanizer ตัวอื่นบน GitHub ส่วนใหญ่ทำมาจาก pattern ภาษาอังกฤษ (ห้าม em dash, ห้ามคำว่า "delve") ซึ่งไม่ตรงกับ AI-tell ของภาษาไทย skill นี้สร้าง pattern ใหม่ที่ตรงกับปัญหาจริงเวลา LLM เขียนหรือแปลเป็นไทย เช่น คำเชื่อมหัวประโยคเกิน ("นอกจากนี้ อีกทั้ง ยิ่งไปกว่านั้น"), การยกความสำคัญเกินจริง ("ในยุคปัจจุบัน ถือเป็นก้าวสำคัญ"), และการแปลตรงตัวจากอังกฤษ

> เป้าหมายคือ "อ่านแล้วเหมือนคนเขียน" ไม่ใช่ "หลบ AI detector"

## ครอบคลุมอะไรบ้าง

- คำเชื่อมหัวประโยคเกินจำเป็น (AI-tell อันดับ 1 ของไทย)
- การยกความสำคัญเกินจริง / ภาษาโฆษณา
- การแปลตรงตัวจากอังกฤษ (translationese)
- โครงสร้าง "ไม่เพียงแค่...แต่ยัง...", การจัดกลุ่มสาม
- คำลงท้ายสรุปกำปั้นทุบดิน, เศษคำแชตบอต
- คำฟุ่มเฟือยและการกั๊กคำมากเกิน
- bullet หัวข้อหนา + อีโมจิประดับ

## วิธีติดตั้ง

### Claude Code
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/<your-username>/thai-humanizer.git ~/.claude/skills/thai-humanizer
```

### Claude.ai (Projects)
อัปโหลด `SKILL.md` และไฟล์ใน `references/` เข้าไปใน Project knowledge

### ใช้กับ system prompt / API
ก็อป `SKILL.md` ใส่ใน system prompt ได้เลย ไฟล์ references โหลดเมื่อต้องการ

## วิธีใช้

```
humanize ข้อความนี้ให้เป็นภาษาไทยธรรมชาติ:
[วางข้อความที่อยากแก้]
```

อยากให้เข้าเสียงตัวเอง ให้แนบตัวอย่างงานเขียนของคุณ:
```
humanize ข้อความนี้ ใช้สไตล์การเขียนของฉันจากตัวอย่างนี้: [วางตัวอย่าง]
```

## โครงสร้าง

```
thai-humanizer/
├── SKILL.md                      # กฎหลัก
├── references/
│   ├── banned-words-th.md        # ลิสต์คำต้องห้ามแบบเต็ม
│   └── examples-th.md            # ตัวอย่าง ก่อน/หลัง หลายประเภท
├── README.md
└── LICENSE
```

## เครดิต

ดัดแปลงแนวคิด structure จาก [blader/humanizer](https://github.com/blader/humanizer) และ [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — pattern ภาษาไทยทั้งหมดเขียนขึ้นใหม่

## License

MIT
