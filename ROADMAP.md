# Boom Local MCP — แผนงาน (Roadmap)

อัปเดต 2026-10-06 · รุ่นล่าสุดที่ปล่อยแล้ว: r40 · [English below](#english)

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

## ปล่อยแล้วใน r40: ตรวจว่าโครงสร้างรับน้ำหนักได้จริง

- **ของที่คนนั่ง ยืน พิง หรืออยู่อาศัย ตรวจแรงก่อนส่งงาน:** AI คิดแรงด้วยมือก่อน แล้วตรวจโครงด้วยโมเดลคานตามแรงทดสอบของมาตรฐาน (เช่น EN 16139 สำหรับเก้าอี้) และบอกเสมอว่าเป็นผลคำนวณ ไม่ใช่การทดสอบจริงหรือการรับรองของวิศวกร
- **บ้านและอาคาร:** น้ำหนักบรรทุกจรและแรงลมตามกฎกระทรวง พ.ศ. 2566 และงานที่กฎหมายให้วิศวกรโยธาที่มีใบอนุญาตออกแบบและรับรอง (เช่น อาคาร 3 ชั้นขึ้นไป หรือเสาห่างกันตั้งแต่ 5 เมตร)
- **เฟอร์นิเจอร์เหล็ก:** เหล็กไม่ทะลุเบาะ ข้อต่อเชื่อมแนบกันโดยตรงแทนหูยื่นที่หักง่าย พนักโค้งตามเบาะกลม และขนาดท่อมาจากการคำนวณ พร้อมตัวอย่างเก้าอี้เหล็กที่ทดสอบแล้วใน SketchUp 2026
- **เทียบกับรูปอ้างอิง:** วัดสัดส่วนจากรูปก่อนสร้าง และเทียบจากมุมกล้องเดียวกับรูป
- ชุดคำสั่งช่วยของ SketchUp เชื่อมโครงเหล็กได้เสถียรขึ้น และการตรวจของ Boom ไม่นับโครงเชื่อมเป็นตัวยึดแล้ว

## ปล่อยแล้วใน r39: MCP Hub และใช้เครื่องมือของแอป AI ก่อน

- **MCP Hub:** MCP ของโปรแกรม (SketchUp มีให้แล้ว, Blender และอื่น ๆ นำเข้าหรือเพิ่มได้) ต่อเข้า Boom ครั้งเดียว AI ทุกตัวที่ต่อ Boom ใช้ได้ ไม่ต้องตั้งในแต่ละแอป Boom เปิดโปรแกรมพร้อม MCP ให้เอง และตรวจการชนกันทุกครั้ง
- **SketchUp เร็วขึ้นมาก:** สั่งสคริปต์ผ่าน MCP ได้ผลหรือบรรทัดที่ผิดกลับมาทันที พร้อมชุดคำสั่งช่วยที่ทดสอบแล้ว (ท่อ ห่วง งานเชื่อม ฉาก บันทึก) ไม่ต้องเปิด Ruby Console
- **ใช้เครื่องมือของแอป AI ก่อน:** ถ้าแอป AI มีเครื่องมือของตัวเอง (เช่น Codex) ให้ใช้ของตัวเอง Boom ให้ Know-how, MCP ของแอป, การตรวจงาน และการอนุมัติ
- **เก็บงานในที่ที่คุณบอก:** ไม่ต้องตั้งรายการโฟลเดอร์ไว้ก่อน ถ้าไม่ได้บอก AI จะถาม Boom ยังไม่แตะ Windows โปรแกรม การตั้งค่าของแอปอื่น ข้อมูลของ Boom และไฟล์รหัสลับ
- **Know-how บอกวิธีเปิดทุกแอปให้พร้อมใช้:** เปิดยังไง ทำงานยังไง เมนูอยู่ตรงไหน และอะไรห้ามทำ
- การ์ดงานบอกเวลาของแต่ละขั้นจากนาฬิกาของ Boom เอง

## ปล่อยแล้วใน r38: Boom ตรวจงานเอง และบอกว่ากำลังทำอะไรจากที่เห็นจริง

- Boom ตรวจโมเดล SketchUp เอง: ชิ้นทับกัน ชิ้นลอย ตัวยึดที่ไม่ได้ยึดอะไร และรายการตัดไม้จากโมเดล
- งานละเอียดพิเศษยังไม่ถือว่าเสร็จจนกว่าผลตรวจของ Boom จะผ่าน
- การ์ดงานบอกสิ่งที่ Boom เห็นเองล่าสุด และบอกเมื่อ ChatGPT กำลังคิดหรือเขียนอยู่

## ปล่อยแล้วใน r37: ถามก่อนเริ่มงานจริง

- งานยังไม่เริ่มและยังไม่เปิด SketchUp หรือ Blender จนกว่าคำตอบของคุณเองจะตอบคำถามที่จำเป็นครบ AI เดาแทนไม่ได้
- ตอบว่า "แล้วแต่คุณ" หรือ "ไม่เอาแล้ว" ก็ได้ งานอื่นที่ไม่มีคำถามทำได้ตามปกติ
- ภาพหน้าจอ SketchUp ไม่ขาวแล้ว

## ปล่อยแล้วใน r36: ใช้ Know-how ทุกงาน ถามเฉพาะที่ยังไม่ชัด และหาโปรแกรมได้ทุกเครื่อง

- AI ดู Know-how ทุกครั้งที่เริ่มงาน ไม่ใช่แค่งาน 3D แล้วเลือกใช้ตามประเภทงาน
- ถามเฉพาะสิ่งที่ยังไม่ได้บอกชัด: บอกชัดแล้วไม่ถามซ้ำ บอกแต่ยังไม่ชัดอาจถามให้ชัด ไม่ได้บอกเลยถามก่อนเริ่ม
- เปิด SketchUp พร้อมเริ่ม MCP ในขั้นเดียว (เมื่อติดตั้งส่วนเสริม MCP Server for SketchUp)
- หาโปรแกรมในเครื่องของคุณเอง รวมถึงไดรฟ์อื่น และจำว่าแต่ละโปรแกรมเปิดจากที่ไหน

## กำลังทำต่อ: Know-how ของแต่ละแอป

- เพิ่มวิธีเปิดให้พร้อมใช้และแผนที่เมนูของแอปอื่น ๆ ทีละแอป (SketchUp และ Blender มีแล้ว)

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

Updated 2026-10-06 · latest release: r40

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

### Released in r40: checking that structures really hold

- **What people sit, stand, lean on or live in is checked before it is handed over:** the AI does a hand check first, then a beam model of the frame under the standard's test loads (for example EN 16139 for chairs), and always says it is a calculation, not a test or an engineer's approval.
- **Houses and buildings:** live loads and wind from Thailand's B.E. 2566 regulation, and the work the law reserves for a licensed civil engineer (for example 3 storeys or more, or columns 5 m or more apart).
- **Steel furniture:** no steel through the seat, welded joints that meet directly instead of short lugs that break, a back that follows a round seat, and tube sizes from the calculation, with a steel chair example tested in SketchUp 2026.
- **Matching a reference photo:** its proportions are measured before building, and the model is compared from the photo's own camera.
- SketchUp's helpers weld steel frames more reliably, and Boom's check no longer counts a welded frame as a fastener.

### Released in r39: the MCP hub, and the AI app's own tools first

- **MCP hub:** an app's MCP (SketchUp built in; Blender and others imported or added) is added to Boom once, and every AI app on Boom can use it with no setup in each. Boom opens the app with its MCP on and checks for conflicts every time.
- **Much faster SketchUp work:** scripts run through its MCP and return the result or the failing line at once, with tested helpers (tubes, rings, welds, scenes, saving). The Ruby Console is never needed.
- **The AI app's own tools first:** when the AI app has its own tools (for example Codex), it uses them; Boom brings know-how, the apps' MCP, checks and approvals.
- **Files where you said:** no folder list to set up; if you don't say where, the AI asks. Boom still never touches Windows, programs, other apps' settings, its own data or secret files.
- **Know-how says how to open every app ready:** how to open it, how to work in it, where its menus are, and what never to do.
- The task card shows each step's time from Boom's own clock.

### Released in r38: Boom checks the work itself and says what it saw

- Boom checks SketchUp models itself: overlapping parts, loose parts, fasteners that hold nothing, and the cut list from the model.
- Buildable work is not done until Boom's check passes.
- The task card shows what Boom itself saw last, and when ChatGPT is thinking or writing.

### Released in r37: asking before the work, for real

- The work does not start, and SketchUp or Blender does not open, until your own answers settle the questions it needs. The AI cannot guess them for you.
- You can answer "up to you" or drop the work. Work with no questions runs as usual.
- SketchUp screenshots are no longer blank white.

### Released in r36: know-how for every task, asking only what is unclear, apps found on every PC

- The AI checks know-how at the start of every task, not only 3D, and takes what fits the kind of work.
- It asks only what you have not said clearly. It does not ask again what you said clearly, may ask what you said unclearly, and asks before starting what you did not say.
- SketchUp opens with its MCP started in one step, when the MCP Server for SketchUp extension is installed.
- Boom finds apps on your PC, including other drives, and remembers where each app was opened from.

### Now: know-how for each app

- How to open each app ready and where its menus are, app by app (SketchUp and Blender are done).

### After that

1. **Know-how for art:** anime, black and white, watercolour, colour, illustration and line art.
2. **Know-how for coding, QA and design:** built into the AI's workflow, so it finds the real problem first, then chooses, designs and fixes correctly.
3. **Coding with one model:** the ChatGPT you are chatting with does the work through Boom, with no second model to pay for. Tools that do several steps in one call cut the round-trips.
4. **Terminal:** a persistent terminal for the AI; consequential commands need approval.
5. **More AI apps:** choose at setup to connect ChatGPT, Claude, Gemini/Antigravity, Grok or a local LLM. Several can be connected at once, and every record says which AI asked.
6. **AIs working together on your PC:** AIs consult, review and hand work to each other (for example, GPT plans, Claude reviews and Gemini executes) through each vendor's own app on your existing account.

### Before v0.5.0

A code-signed installer, secure storage for secrets, and a full install test on a clean PC through restart.
