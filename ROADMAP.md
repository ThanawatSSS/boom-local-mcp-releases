# Boom Local MCP — แผนงาน (Roadmap)

อัปเดต 2026-10-06 · รุ่นล่าสุดที่ปล่อยแล้ว: r37 · [English below](#english)

แผนนี้บอกลำดับงาน ไม่ใช่วันที่ แต่ละเรื่องจะออกแบบให้เสร็จก่อนเขียนโค้ด และไม่มีเรื่องไหนลดความปลอดภัยของ Boom: การอนุมัติ การบันทึกทุกคำสั่ง และการตัดสินใจสุดท้ายของคุณยังอยู่ใน Boom เสมอ

## ปล่อยแล้วใน r35: วิธีทำงานของช่าง (Know-how) สำหรับงาน 3D

ให้ AI ทุกตัวทำงานแบบช่างฝีมือเหมือนกัน งานจึงออกมาเป็นของที่ใช้จริงได้ ไม่ใช่แค่กล่องต่อกัน:
- ความรู้สร้างจากมาตรฐานอาชีพที่หน่วยงานรับรองแล้ว (TPQI ของไทย และ ESCO ของยุโรป) แยกตามประเภทงาน ได้แก่ การมองแบบเปอร์สเปกทีฟและการคิดเป็นสามมิติ, การสร้างโมเดล 3 มิติ, ตัวละคร (สำหรับเกมและแอนิเมชัน), สถาปัตยกรรม, งานก่อสร้าง และการออกแบบผลิตภัณฑ์
- วิธีทำในแต่ละโปรแกรมแยกจากความรู้: Blender (ตัวละคร งานออร์แกนิก สิ่งของ) และ SketchUp (บ้าน อาคาร เฟอร์นิเจอร์)
- ก่อนเริ่ม AI ถามว่าต้องการละเอียดระดับไหน: Mock-up, ละเอียด หรือละเอียดพิเศษที่ถอดเป็นชิ้นไปทำจริงได้ (ตัดไม้ตามขนาด เจาะร่องตามโมเดล หรือพิมพ์ 3D แยกชิ้นแล้วประกอบ)
- โมเดลรู้ว่าแต่ละชิ้นต่อกันอย่างไรและเพราะอะไร (เดือย ร่อง สลัก น็อต สกรู ข้อต่อสำหรับงานพิมพ์)
- ทุกโมเดลถูกตรวจครบทุกด้าน (บน ล่าง ซ้าย ขวา หน้า หลัง Iso และระดับสายตา) มีจุดย้อนกลับทุกขั้น และมีบันทึกส่งต่อให้คุณหรือ AI ตัวอื่นทำต่อได้

ทดลองแล้ว: เก้าอี้ตัวเดียวกันทำสองแบบ แบบที่ใช้ Know-how ได้งานที่ใช้จริงได้ ส่วนแบบที่ไม่ใช้ได้แค่ Mock-up และรุ่นละเอียดพิเศษ ข้อต่อทุกจุดเข้ากันพอดี ไม่มีชิ้นไหนทับกัน ถอดเข้าออกได้ครบทุกขั้น

ดูวิธีใช้ในคู่มือ หัวข้อ 7

## ปล่อยแล้วใน r37: ถามก่อนเริ่มงานจริง

- งานยังไม่เริ่มและยังไม่เปิด SketchUp หรือ Blender จนกว่าคำตอบของคุณเองจะตอบคำถามที่จำเป็นครบ AI เดาแทนไม่ได้
- ตอบว่า "แล้วแต่คุณ" หรือ "ไม่เอาแล้ว" ก็ได้ งานอื่นที่ไม่มีคำถามทำได้ตามปกติ
- ภาพหน้าจอ SketchUp ไม่ขาวแล้ว

## ปล่อยแล้วใน r36: ใช้ Know-how ทุกงาน ถามเฉพาะที่ยังไม่ชัด และหาโปรแกรมได้ทุกเครื่อง

- AI ดู Know-how ทุกครั้งที่เริ่มงาน ไม่ใช่แค่งาน 3D แล้วเลือกใช้ตามประเภทงาน
- ถามเฉพาะสิ่งที่ยังไม่ได้บอกชัด: บอกชัดแล้วไม่ถามซ้ำ บอกแต่ยังไม่ชัดอาจถามให้ชัด ไม่ได้บอกเลยถามก่อนเริ่ม
- เปิด SketchUp พร้อมเริ่ม MCP ในขั้นเดียว (เมื่อติดตั้งส่วนเสริม MCP Server for SketchUp)
- หาโปรแกรมในเครื่องของคุณเอง รวมถึงไดรฟ์อื่น และจำว่าแต่ละโปรแกรมเปิดจากที่ไหน

## กำลังทำต่อ: MCP Hub (ต่อโปรแกรมอื่นผ่าน Boom ทางเดียว)

- โปรแกรมที่มี MCP ของตัวเอง (เช่น SketchUp, Blender) ต่อเข้า ChatGPT ผ่าน Boom ทางเดียว ไม่ต้องเปิด Tunnel แยกต่อโปรแกรม
- สั่งแค่ "ทำงานนี้ใน SketchUp" Boom เปิดโปรแกรม เริ่ม MCP และต่อให้ใช้ได้ทันที (r36 เปิดพร้อมเริ่ม MCP ได้แล้ว)
- คำสั่งที่มีผลจริงของโปรแกรมเหล่านั้นผ่านการอนุมัติของ Boom

## ต่อจากนั้น

1. **Know-how ด้านศิลปะ:** วาด Anime, ขาวดำ, สีน้ำ, ลงสี, Illustration และ Line art
2. **Know-how ด้านเขียนโปรแกรม QA และออกแบบ:** วางไว้ในขั้นตอนการทำงานของ AI ให้หาจุดปัญหาจริงก่อน แล้วเลือก ออกแบบ และแก้ได้ถูก
3. **เขียนโค้ดด้วยโมเดลเดียว:** ใช้ ChatGPT ตัวที่คุยอยู่ทำงานเองผ่าน Boom ไม่ต้องจ่ายโมเดลที่สอง และลดจำนวนรอบด้วยเครื่องมือที่ทำหลายขั้นในครั้งเดียว
4. **Terminal:** หน้าต่างคำสั่งที่ AI ใช้ต่อเนื่องได้ คำสั่งที่มีผลจริงต้องอนุมัติ
5. **AI ตัวอื่น:** เลือกได้ตอนติดตั้งว่าจะต่อ ChatGPT, Claude, Gemini/Antigravity, Grok หรือ Local LLM ต่อพร้อมกันได้หลายตัว และทุกบันทึกบอกว่า AI ตัวไหนสั่ง
6. **AI ช่วยกันในเครื่อง:** ให้ AI ปรึกษา ตรวจงาน และส่งงานต่อกันในเครื่อง (เช่น GPT วางแผน Claude ตรวจ Gemini ลงมือ) ผ่านโปรแกรมของแต่ละเจ้าที่ใช้บัญชีเดิมของคุณ

## ก่อนปล่อย v0.5.0

ตัวติดตั้งที่มีลายเซ็นดิจิทัล, การเก็บรหัสลับอย่างปลอดภัย และการทดสอบติดตั้งบนเครื่องใหม่ตั้งแต่ต้นจนรีสตาร์ต

---

## English

Updated 2026-10-06 · latest release: r37

This plan gives the order, not dates. Each item is designed before it is coded. None of them weakens Boom's safety: approvals, the record of every command and your final decision always stay in Boom.

### Released in r35: craft know-how for 3D work

Every AI works the same craftsperson's way, so the results are things you can use, not boxes stuck together:
- **Knowledge from validated standards.** It comes from occupational standards that national bodies have validated (Thailand's TPQI, the EU's ESCO), per kind of work:
  - perspective and thinking in 3D;
  - 3D modelling;
  - characters, for games and animation;
  - architecture;
  - construction;
  - product design.
- **Software procedures kept apart from the knowledge:** Blender for characters, organic forms and objects; SketchUp for houses, buildings and furniture.
- **The level of detail is asked first:** mock-up, detailed, or super-detailed. A super-detailed model can be taken apart and made for real: cut the wood to size and cut the joints as modelled, or print the parts separately and assemble them.
- **How the parts connect, and why:** tenons and mortises, slots, dowels, bolts, screws, and joints for printed parts.
- **Every model checked from every side:** top, bottom, left, right, front, back, iso and eye level. Each stage has a checkpoint, and a hand-over note lets you or another AI continue.

Tried already: the same chair built both ways. With know-how it was usable; without it, a mock-up. The buildable version fits at every joint, no two parts overlap, and it comes apart and goes back together at every step.

See section 7 of the guide.

### Released in r37: asking before the work, for real

- The work does not start, and SketchUp or Blender does not open, until your own answers settle the questions it needs. The AI cannot guess them for you.
- You can answer "up to you" or drop the work. Work with no questions runs as usual.
- SketchUp screenshots are no longer blank white.

### Released in r36: know-how for every task, asking only what is unclear, apps found on every PC

- The AI checks know-how at the start of every task, not only 3D, and takes what fits the kind of work.
- It asks only what you have not said clearly. It does not ask again what you said clearly, may ask what you said unclearly, and asks before starting what you did not say.
- SketchUp opens with its MCP started in one step, when the MCP Server for SketchUp extension is installed.
- Boom finds apps on your PC, including other drives, and remembers where each app was opened from.

### Now: the MCP hub (other apps through one Boom connection)

- Apps that have their own MCP (for example SketchUp and Blender) reach ChatGPT through Boom's single connection, with no tunnel per app.
- Say "do this in SketchUp", and Boom opens the app, starts its MCP and connects it, ready to use. r36 already opens it with the MCP started.
- The apps' consequential commands go through Boom's approvals.

### After that

1. **Know-how for art:** anime, black and white, watercolour, colour, illustration and line art.
2. **Know-how for coding, QA and design:** built into the AI's workflow, so it finds the real problem first, then chooses, designs and fixes correctly.
3. **Coding with one model:** the ChatGPT you are chatting with does the work through Boom, with no second model to pay for. Tools that do several steps in one call cut the round-trips.
4. **Terminal:** a persistent terminal for the AI; consequential commands need approval.
5. **More AI apps:** choose at setup to connect ChatGPT, Claude, Gemini/Antigravity, Grok or a local LLM. Several can be connected at once, and every record says which AI asked.
6. **AIs working together on your PC:** AIs consult, review and hand work to each other (for example, GPT plans, Claude reviews and Gemini executes) through each vendor's own app on your existing account.

### Before v0.5.0

A code-signed installer, secure storage for secrets, and a full install test on a clean PC through restart.
