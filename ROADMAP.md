# Boom Local MCP — แผนงาน (Roadmap)

อัปเดต 2026-10-07 · รุ่นล่าสุดที่ปล่อยแล้ว: r42 · [English below](#english)

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

## ปล่อยแล้วใน r42: Claude, WorkBuddy และแอป AI อื่นใช้ Boom ได้

- **แอป AI บนเครื่องนี้ต่อ Boom ได้:** Claude Desktop, Claude Code, WorkBuddy, Antigravity และ Cline กดเชื่อมต่อที่ Boom Control → แอป AI แล้วเปิดแอปใหม่หนึ่งครั้ง
- **Boom ตัวเดียวกันทุกแอป:** Know-how, MCP ของแอป, การตรวจงาน, การ์ดงาน และการอนุมัติชุดเดียวกับ ChatGPT ทุกบันทึกบอกว่าแอปไหนสั่ง
- **การอนุมัติจากแอปที่ไม่มีการ์ด** ขึ้นใน Boom Control ทันทีพร้อมแจ้งเตือน
- **ปลอดภัย:** ตัวเชื่อมต่อได้เฉพาะ Boom ของผู้ใช้ Windows คนนี้ แอปที่ไม่ได้เชื่อมต่อถูกปฏิเสธ และเลิกเชื่อมต่อได้ทุกเมื่อ

## ปล่อยแล้วใน r41: งานมีเส้นทางและการตรวจ สร้างจากแบบแปลน และทำงานในโมเดลของคุณเอง

- **ค่าเริ่มต้นคือแบบละเอียด:** ไม่ต้องตอบเรื่องระดับรายละเอียดก่อนเริ่มแล้ว อยากได้เร็ว ๆ บอกในแชตว่า "ร่างคร่าวๆ" หรือ "ทำเร็วๆ" อยากเอาไปทำจริงบอก "ละเอียดพิเศษ"
- **งานมีเส้นทางและการตรวจ:** Boom บอก AI ว่างานนี้ต้องอ่าน Know-how อะไร ต้องผ่านการตรวจอะไร (เช่น แนวรับน้ำหนักของเก้าอี้ หรือเทียบกับรูปอ้างอิง) และต้องตอบสิ่งที่คุณขอทุกข้อก่อนปิดงาน การ์ดงานและ Boom Control แสดงครบ
- **สร้างจากแบบแปลน PDF หรือรูป Layout:** Boom เปิดแปลนให้ AI ดู AI หามาตราส่วนและเช็กกับอีกระยะ วางแปลนใต้โมเดลตามขนาดจริง แล้วสร้างทับ
- **ทำในโมเดลของคุณเอง:** แก้ อัปเดต หรือสร้างของใหม่แทนตำแหน่ง Object ตามชื่อ ของเดิมถูกซ่อนไว้ ไม่ได้ลบ
- **SketchUp ต่อเนื่อง:** กดดูหน้าต่างที่ AI ใช้อยู่ได้ AI ทำต่อในไฟล์เดิม และไฟล์ใหม่ไม่มีคนจำลองของ template
- **การตรวจของ Boom เร็วและแม่นขึ้น:** ไม่ค้างเกินเวลา ตรวจต่อจากเดิมได้ หาชิ้นที่ฝังในชิ้นอื่นเจอ และไม่ตัดสินชิ้นที่ยังตรวจไม่ครบ

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

## กำลังทำต่อ: AI ตัวอื่นใช้ Boom ได้ และ DeepSeek Harness

**v0.6.0 (Major update): ความสามารถของ DeepSeek Harness สร้างใหม่ใน Boom ใช้โมเดลเดียว**
1. **Code mode:** AI เขียนโปรแกรมเดียวที่เรียกเครื่องมือหลายตัว แทนการเรียกทีละครั้งหลายสิบรอบ
2. **งานเบื้องหลัง:** งานยาวไม่ติดเพดานเวลาของการเรียก ดูความคืบหน้าและรอได้
3. **กันวนซ้ำ และผลลัพธ์ใหญ่:** เตือนเมื่อเรียกเหมือนเดิมซ้ำ ผลยาวเก็บเป็นไฟล์ให้อ่านต่อ
4. ต่อจากนั้น: อ่านก่อนแก้ไฟล์, สรุปไฟล์ที่งานเปลี่ยน, Terminal ที่จำกัดการเขียน, ค้นงานเก่า และโหมด API สำหรับผู้ที่ใส่ API key เอง

ทดสอบด้วย ChatGPT, Codex, Claude และ WorkBuddy บนงานเดียวกัน ก่อนและหลัง

## ต่อจากนั้น

1. **Know-how ด้านศิลปะ:** วาด Anime, ขาวดำ, สีน้ำ, ลงสี, Illustration และ Line art
2. **Know-how ด้านเขียนโปรแกรม QA และออกแบบ:** วางไว้ในขั้นตอนการทำงานของ AI ให้หาจุดปัญหาจริงก่อน แล้วเลือก ออกแบบ และแก้ได้ถูก
3. **เขียนโค้ดด้วยโมเดลเดียว:** ใช้ ChatGPT ตัวที่คุยอยู่ทำงานเองผ่าน Boom ไม่ต้องจ่ายโมเดลที่สอง และลดจำนวนรอบด้วยเครื่องมือที่ทำหลายขั้นในครั้งเดียว
4. **Terminal:** หน้าต่างคำสั่งที่ AI ใช้ต่อเนื่องได้ คำสั่งที่มีผลจริงต้องอนุมัติ
5. **AI ตัวอื่นอีก:** Grok หรือ Local LLM ต่อพร้อมกันได้หลายตัว และทุกบันทึกบอกว่า AI ตัวไหนสั่ง
6. **AI ช่วยกันในเครื่อง:** ให้ AI ปรึกษา ตรวจงาน และส่งงานต่อกันในเครื่อง (เช่น GPT วางแผน Claude ตรวจ Gemini ลงมือ) ผ่านโปรแกรมของแต่ละเจ้าที่ใช้บัญชีเดิมของคุณ

## ก่อนปล่อย v0.5.0

ตัวติดตั้งที่มีลายเซ็นดิจิทัล, การเก็บรหัสลับอย่างปลอดภัย และการทดสอบติดตั้งบนเครื่องใหม่ตั้งแต่ต้นจนรีสตาร์ต

---

## English

Updated 2026-10-07 · latest release: r42

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

### Released in r42: Claude, WorkBuddy and other AI apps on Boom

- **AI apps on this PC connect to Boom:** Claude Desktop, Claude Code, WorkBuddy, Antigravity and Cline. Press connect in Boom Control → แอป AI, then open the app again once.
- **The same Boom for every app:** the same know-how, your apps' MCP, inspectors, task card and approvals as ChatGPT. Every record says which app asked.
- **Approvals from apps without Boom's card** come up in Boom Control at once, with a notification.
- **Safe:** the connector reaches only this Windows user's Boom. An app that is not connected is refused, and you can disconnect it at any time.

### Released in r41: routes and checks, building from plans, working in your own model

- **Detailed is the default level:** the level is no longer asked before starting. Want it quick? Say "mock-up" or "quick" in the chat. To make it for real, say "buildable".
- **Every piece of work has a route and checks:** Boom tells the AI which know-how to read, which checks to pass (for example a chair's load path, or matching the reference picture) and that every one of your requests must be answered before the work is done. The task card and Boom Control show them all.
- **From a PDF floor plan or a layout picture:** Boom shows the plan to the AI; the AI finds and checks its scale, lays it under the model at real size and builds on it.
- **In your own model:** edit, update, or make a new object in place of one you name; the old one is hidden, not deleted.
- **SketchUp carries on:** you can look and click in the AI's SketchUp window; the AI carries on in the same file, and new files come without the template's figure.
- **Boom's check is faster and sharper:** it always answers in time, continues where it stopped, finds a part buried inside another, and gives no verdict on parts it has not finished checking.

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

### Now: more AI apps on Boom, and the DeepSeek Harness

**v0.6.0 (major update): DeepSeek Harness capabilities rebuilt in Boom, one model**
1. **Code mode:** the AI writes one program that calls many tools, instead of dozens of separate calls.
2. **Background jobs:** long work is not cut off by a call's time limit; you can follow it and wait for it.
3. **Loop guard and big results:** a reminder when the same call repeats, and long output kept as a file to read on.
4. After that: read before editing a file, what each task changed, a confined terminal, searching earlier work, and an API mode for those who give their own key.

Tested on ChatGPT, Codex, Claude and WorkBuddy with the same work, before and after.

### After that

1. **Know-how for art:** anime, black and white, watercolour, colour, illustration and line art.
2. **Know-how for coding, QA and design:** built into the AI's workflow, so it finds the real problem first, then chooses, designs and fixes correctly.
3. **Coding with one model:** the ChatGPT you are chatting with does the work through Boom, with no second model to pay for. Tools that do several steps in one call cut the round-trips.
4. **Terminal:** a persistent terminal for the AI; consequential commands need approval.
5. **Still more AI apps:** Grok or a local LLM. Several can be connected at once, and every record says which AI asked.
6. **AIs working together on your PC:** AIs consult, review and hand work to each other (for example, GPT plans, Claude reviews and Gemini executes) through each vendor's own app on your existing account.

### Before v0.5.0

A code-signed installer, secure storage for secrets, and a full install test on a clean PC through restart.
