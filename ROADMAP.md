# Boom Local MCP — แผนงาน (Roadmap)

อัปเดต 2026-10-10 · รุ่นล่าสุดที่ปล่อยแล้ว: r50 (0.5.5-2) · [English below](#english)

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

## ปล่อยแล้วใน r50 (0.5.5-2): AI ใช้ Boom ได้เต็มความสามารถขึ้นใน ChatGPT, Codex และ Claude

- **ChatGPT อ่านผลลัพธ์ครั้งเดียว ไม่ซ้ำสองรอบ** ChatGPT อ่านทั้ง content และ structuredContent ผลของการดูหน้าจอจึงถูกอ่านซ้ำ ประมาณ 15,000 ตัวอักษรต่อครั้ง ตอนนี้ส่งชุดเดียว งานหน้าจอยาว ๆ เร็วขึ้น และคำตอบโหลดขึ้นง่ายขึ้น
- **คำแนะนำของ Boom อ่านได้ครบใน Claude Code** Claude Code ตัดคำแนะนำของเซิร์ฟเวอร์ที่ 2,048 ตัวอักษร ของเดิมยาว 3,006 กฎใหม่ (โหมดการอนุมัติ งานเบื้องหลัง run_code) จึงหายไป ตอนนี้เหลือ 1,857 ตัวอักษร และเรื่องสำคัญอยู่ช่วงต้นตามคำแนะนำของ OpenAI
- **ผลลัพธ์ใหญ่ไม่ถูก Codex ตัดทิ้ง** Codex ตัดผลลัพธ์ที่เกินประมาณ 10,000 token โดยอ่านส่วนที่เหลือไม่ได้ Boom จึงนับเป็น token (ข้อความภาษาไทยใช้ token มากกว่า) และบอก result_id ไว้บรรทัดแรก ให้ AI อ่านส่วนที่เหลือได้เสมอ
- **คำอธิบายเครื่องมือตรงกับโหมดการอนุมัติ** เดิมบอก AI ว่ากดส่งหรือยืนยันไม่ได้ ต้องขออนุมัติทุกครั้ง ตอนนี้บอกว่าโหมด Automation ทำได้เลย และขออนุมัติเมื่อเห็นว่าเสี่ยง
- **รายการเครื่องมือสั้นและชัดขึ้น** ซ่อนเครื่องมือรุ่นเก่า 9 ตัวที่ Computer Use ทำแทนได้ครบ (input_*, accessibility_tree, accessibility_set_text, window_list, window_activate)
- **ไฟล์ทดสอบ 3 งานสำหรับเทียบ ChatGPT, Codex และ Claude** อยู่ใน docs/testing/AI_TEST_PROMPTS.md

## ปล่อยแล้วใน r49 (0.5.5-1): AI ทำงานได้เองมากขึ้น ไม่ต้องกดยืนยันซ้ำ ๆ และทำงานเบื้องหลังได้จริง

- **โหมดการอนุมัติ: Automation หรือ Strict** (ตั้งค่า > โหมดการอนุมัติ) ค่าเริ่มต้นเป็น Automation ให้ AI ตัดสินใจเองและทำได้ทันที ไม่ต้องกดยืนยันซ้ำ ๆ ถ้า AI เห็นว่าขั้นไหนเสี่ยง (ย้อนกลับไม่ได้ มีค่าใช้จ่าย หรือส่งถึงคนอื่น) จะขออนุมัติคุณเอง การลบไฟล์ยังขออนุมัติเสมอ ทุกอย่างที่ทำยังบันทึกไว้ในประวัติ ถ้าต้องการให้รอคุณทุกครั้ง เลือก Strict
- **ปุ่มอนุมัติเป็นสีเขียว** ทั้งบนแถบ overlay และใน Boom Control
- **AI เห็นหน้าต่างที่มันทำงานอยู่ ไม่ใช่หน้าจอของคุณ** เดิมถ้าหน้าต่างที่ AI ใช้ถูกหน้าต่างของคุณบัง ภาพที่ส่งให้ AI อาจเป็นหน้าจอที่คุณกำลังใช้ ตอนนี้ Boom ไม่ถ่ายหน้าจอของคุณแทนเด็ดขาด หน้าต่างที่ย่อไว้จะถูกเปิดกลับไว้ด้านหลังงานของคุณโดยไม่แย่งหน้าจอ และ AI จะดึงหน้าต่างขึ้นมาก็ต่อเมื่ออยากให้คุณดู พร้อมบอกในแชต
- **ให้เบราว์เซอร์ทำงานต่อแม้ถูกบังหรือย่อ** (ตั้งค่า) Brave, Chrome และ Edge หยุดวาดหน้าต่างที่ถูกบัง เปิดสวิตช์นี้แล้ว AI ทำงานในเบราว์เซอร์ข้างหลังงานของคุณได้ต่อเนื่อง ตรวจได้ที่ brave://policy
- **Code mode (เลือกติดตั้งเพิ่ม)** ให้ AI เขียนโปรแกรมที่ใช้เครื่องมือของ Boom หลายขั้นในครั้งเดียว เร็วกว่าและได้ผลครบกว่าทีละคำสั่ง โปรแกรมทำงานในกล่องแยก MXC ของ Microsoft ที่ไม่มีอินเทอร์เน็ตและเข้าถึงไฟล์ได้เฉพาะโฟลเดอร์ที่อนุญาต ติดตั้งได้จากตั้งค่า > Code mode (ดาวน์โหลดประมาณ 12 MB) หรือติ๊กตอนติดตั้ง Boom ไม่ติดตั้งให้ถ้าไม่เลือก Boom ตรวจเครื่องมือเขียนโค้ดที่ขาด (Git, Node.js, Python) และติดตั้งให้เมื่อคุณกด ตอนถอนการติดตั้งเลือกลบได้
- **งานยาวไม่ค้าง** งานที่ใช้เวลานาน (ตรวจโมเดล ทดสอบ build เรียกแอป) ทำต่อเบื้องหลังเมื่อเกิน 45 วินาที AI รับผลด้วย job_output ไม่ต้องเริ่มใหม่ แม้แชตเลิกรอไปแล้ว
- **ผลลัพธ์ใหญ่ไม่ทำให้คำตอบโหลดไม่ขึ้น** Boom ส่งส่วนต้นและท้าย พร้อมบรรทัดที่มีข้อผิดพลาดหรือคำเตือนจากส่วนกลาง และเก็บทั้งหมดไว้ให้ AI อ่านต่อ (result_read)
- **AI เห็นเหตุผลเมื่อคำสั่งไม่สำเร็จเสมอ** และได้รับการเตือนเมื่อเรียกคำสั่งเดิมซ้ำ ๆ
- **อัปเดต MCP Python SDK เป็น 2.2.0**

ควรรีเฟรชปลั๊กอินใน ChatGPT และ Codex: มีเครื่องมือใหม่ run_code, job_output, job_kill, result_read, ask_user

## ปล่อยแล้วใน r48 (แก้ด่วนของ r47): ทำงานเบื้องหลังได้จริง และคำตอบโหลดได้

- **ภาพหน้าจอที่ส่งให้ AI เล็กลงมาก** เดิมทุกครั้งที่ AI ดูหรือกดอะไรบนหน้าจอ Boom ส่งภาพ PNG สูงสุด 900 KB งานยาว ๆ จึงมีภาพหลายสิบ MB ในคำตอบเดียว ChatGPT แสดง "This response couldn't load" หรือไม่ส่งข้อความกลับทั้งที่ทำเสร็จแล้ว ตอนนี้เป็น JPEG ไม่เกินราว 200 KB และหลังกดปุ่มผ่าน UI Automation จะส่งเฉพาะรายการที่เปลี่ยน ไม่ส่งภาพ (ขอภาพได้ถ้าต้องการ)
- **เบราว์เซอร์ไม่เด้งขึ้นมาบังงานของคุณซ้ำ ๆ** การเปิดแท็บใหม่ในเบราว์เซอร์ของคุณเคยรายงานว่าล้มเหลวทั้งที่เปิดได้ (แถบที่อยู่ซ่อน "www.") AI จึงเปิดซ้ำและเบราว์เซอร์เด้งขึ้นมาทุกครั้ง ตอนนี้หาแท็บเจอ และคืนหน้าต่างที่คุณใช้อยู่กลับมาด้านหน้าทันทีหลังเปิดแท็บ
- **เครื่องมือคลิกและพิมพ์รุ่นเก่าไม่ใช้เมาส์จริงอีกแล้ว** กดผ่าน UI Automation เท่านั้น ไม่ดึงหน้าต่างขึ้นมา ถ้าต้องใช้เมาส์จริงต้องผ่าน Computer Use ซึ่งขออนุญาตคุณก่อน
- **ถ้าคำตอบโหลดไม่ขึ้น บอก AI ว่า "สรุป"** AI จะอ่านสิ่งที่ Boom ทำไปแล้วก่อนตอบ ไม่ต้องทำใหม่
- **หน้าภาพรวมใน Boom Control แสดงโปรแกรมที่ Boom เปิดให้** พร้อมปุ่มแสดงหน้าต่างและปุ่มบังคับปิด (เฉพาะโปรแกรมที่ Boom เปิดเอง)

## ปล่อยแล้วใน r47: งานที่ส่งมอบต้องใช้ได้จริง

- **เริ่มงานได้เสมอ คำถามที่ยังไม่ได้ตอบขึ้นบนการ์ดงาน** เดิมถ้ายังตอบไม่ครบ Boom ไม่ยอมเริ่มงาน แล้ว AI ก็ทำต่อโดยไม่มีการ์ดและไม่มีการตรวจ ตอนนี้ล็อกเฉพาะการเปิดหรือแก้งานใน SketchUp และ Blender ก่อนได้คำตอบ
- **ปัญหาที่คุณชี้ระหว่างทำงานติดอยู่บนการ์ดจนกว่าจะแก้** AI จะปิดงานว่า "เสร็จ" ไม่ได้ถ้ายังไม่ได้ตอบทุกข้อ
- **งานหน้าเว็บ 3 มิติจบได้เมื่อ Boom ตรวจหน้าสุดท้ายเองแล้วสะอาด** AI รายงานเองแทนไม่ได้
- **ตรวจหน้าเว็บได้ละเอียดขึ้น** ชิ้นที่ไม่มีตำแหน่ง (ไม่ถูกวาด), ชิ้นที่ขนาดผิดกลุ่ม, ชิ้นที่หันผิดทาง, ชิ้นที่ไม่มีชื่อ และทดสอบปุ่มหรือคีย์ได้โดยไม่ยุ่งกับหน้าจอของคุณ
- **ความรู้ใหม่:** แกนโลก แกนวัตถุ การย้ายและการหมุนใน 3 มิติ และการตรวจความปลอดภัยของซอฟต์แวร์ (นำสกิลของ Cloudflare มาใช้ตามต้นฉบับ ถ้า AI มีสกิลของตัวเองให้ใช้ของตัวเองก่อน)
- **Computer Use:** การคลิกปุ่มใช้ UI Automation ก่อน ไม่แย่งเมาส์ของคุณ ถ้าต้องใช้เมาส์และคีย์บอร์ดจริงจะขออนุญาตหนึ่งครั้งต่อหนึ่งงานและหนึ่งแอป
- **Ask first:** เข้าใจคำว่า "ทำเป็นอีกไฟล์" แล้ว และงานต่อเนื่องจะใช้ไฟล์เดิม ไม่เปิดไฟล์ใหม่ทุกครั้ง

## ปล่อยแล้วใน r46 (แก้ด่วนของ r45): อัปเดตไม่ติดแม้ปิดเบราว์เซอร์แล้ว

- **Boom ปิดตัวขับเบราว์เซอร์ (node.exe ของ Playwright) เมื่อปิดเบราว์เซอร์ตัวสุดท้ายที่เปิดให้ AI** เดิมตัวขับยังค้างอยู่หลังปิดเบราว์เซอร์ Boom จึงยังไม่ยอมอัปเดตหรือหยุด เปิดเบราว์เซอร์ครั้งต่อไป Boom เริ่มตัวขับใหม่ให้เอง
- **ถ้ายังอัปเดตจาก r43–r45 ไม่ได้:** ปิดเบราว์เซอร์ที่ค้างในหน้าภาพรวม แล้วเริ่ม Boom ใหม่ จากนั้นอัปเดตมารุ่นนี้

## ปล่อยแล้วใน r45 (แก้ด่วนของ r44): อัปเดตไม่ติดเพราะเบราว์เซอร์ที่ค้างไว้

- **เบราว์เซอร์ที่ Boom เปิดให้ AI แล้วไม่มีใครใช้ Boom ปิดเองเมื่อครบ 15 นาที** เดิมถ้า AI (เช่น WorkBuddy) เปิดแล้วไม่ปิด Boom จะไม่ยอมอัปเดตหรือหยุดไปตลอด
- **หน้าภาพรวมแสดงเบราว์เซอร์ที่ค้างทุกตัว พร้อมปุ่มปิด** รวมถึงตัวที่ปิดหน้าต่างไปแล้วแต่ Boom ยังไม่ได้ปิดให้เรียบร้อย
- **ข้อความตอนอัปเดตไม่ได้** บอกว่าดูและปิดงานค้างได้ที่หน้าภาพรวม

## ปล่อยแล้วใน r44: แอป AI ครบ งานที่ใช้ได้จริงบนเครื่องทั่วไป และใช้หน้าจอเบาลง

จากการใช้งานจริงกับ WorkBuddy (เก้าอี้ใน SketchUp, หอไม้จีนแบบ Three.js สองแบบ และวาดรูปใน Paint):
- **แอป AI:** Cline และ Freebuff เชื่อมต่อจาก Boom Control ได้แล้ว และแอปอื่น ๆ กด "สร้างการเชื่อมต่อ" ตั้งชื่อ แล้วคัดลอกไปวางในการตั้งค่า MCP ของแอปนั้น แต่ละแอปมีรหัสของตัวเอง
- **การ์ดงานบอกชื่อแอปที่ทำงานจริง** เช่น "ขั้นที่ WorkBuddy บอกว่าเสร็จ" แทนที่จะเป็น ChatGPT ทุกงาน
- **Know-how ใหม่:** ความสะอาดและน้ำหนักของโมเดล, โมเดล 3 มิติเป็นหน้าเว็บด้วย Three.js (วาดใหม่เฉพาะตอนมีอะไรเปลี่ยน ตรวจทุกด้านด้วย Chrome ที่ใช้การ์ดจอ), อาคารเครื่องไม้จีนตาม 营造法式 (โครงหลังคาครบทุกด้าน เต้ากงครบทุกมุม ความโค้งหลังคาคำนวณตามกฎ ประตูหมุนบนเดือย) และวาดรูปใน Paint
- **ทำตามคำสั่งของงาน** และประตูแสดงแบบเปิดค้างไว้บางส่วน
- **Solid Tools เป็นคำแนะนำ ไม่ใช่ข้อบังคับ:** AI เลือกเครื่องมือของ SketchUp ที่เหมาะกับแต่ละชิ้นเอง
- **Boom ตรวจโมเดล SketchUp แล้วบอกน้ำหนักด้วย:** จำนวนหน้า สามเหลี่ยม เท็กซ์เจอร์ เงา และเศษเส้นจากการตัด
- **Boom ตรวจโมเดลบนหน้าเว็บเอง (web_inspect):** ภาพทุกด้านและแบบโปร่ง นับชิ้นส่วนตามชนิดพร้อมตำแหน่ง และภาระตอนไม่ได้ใช้งาน ในครั้งเดียว ไม่ต้องให้ AI เขียนตัวทดสอบเอง
- **ใช้หน้าจอเบาและแม่นขึ้น:** หลังแต่ละคำสั่ง AI ได้เฉพาะปุ่มที่เปลี่ยน (ใน Paint ข้อมูลเล็กลงประมาณ 97%) คลิกบนพื้นที่วาดรูปได้ผลจริง และค้นปุ่มด้วยชื่อได้

## ปล่อยแล้วใน r43 (แก้ด่วน): แอป AI เชื่อมต่อได้จริง

- **WorkBuddy:** Boom เขียนลงไฟล์ที่ WorkBuddy อ่านจริง (`.workbuddy-ai\mcp.json`) ถ้าเคยกดเชื่อมต่อใน r42 ให้กดเชื่อมต่อใหม่หนึ่งครั้ง
- **Claude Desktop จาก Microsoft Store:** Boom หาเจอแล้ว และเขียนลงในโฟลเดอร์ของแอป
- **MCP ของแอป:** รายการ "boom" ของแอปอื่นไม่ขึ้นให้นำเข้าแล้ว เพราะจะทำให้ Boom เรียกตัวเองวนไม่จบ และ Boom ปฏิเสธถ้ามีคนพยายามเพิ่ม

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

Updated 2026-10-10 · latest release: r50 (0.5.5-2)

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

### Released in r50 (0.5.5-2): the AI gets more out of Boom in ChatGPT, Codex and Claude

- **ChatGPT reads each result once.** ChatGPT reads content and structuredContent both, so screen results were read twice (about 15,000 characters each). Now one copy goes to ChatGPT and Codex.
- **Claude Code reads all of Boom's instructions.** It cuts server instructions at 2,048 characters; Boom's were 3,006, so the newest rules were lost. Now 1,857, key rules first (OpenAI's guidance too).
- **Big results are no longer silently cut by Codex.** Codex cuts tool output over about 10,000 tokens. Boom's budget is now in tokens (Thai text costs more), and the result_id is on the first line.
- **Tool descriptions match the approval mode.** They no longer tell the AI that Send or Confirm always needs approval.
- **A shorter, clearer tool list**: 9 old tools replaced by Computer Use are hidden from the AI.
- **Three test prompts to compare ChatGPT, Codex and Claude**: docs/testing/AI_TEST_PROMPTS.md.

### Released in r49 (0.5.5-1): the AI works on its own, without repeated confirmations, and really works in the background

- **Approval modes: Automation or Strict** (Settings). Automation, the default, lets the AI decide and act without repeated confirmations. It asks you itself before a step it judges risky (hard to undo, costly, or sent to other people). Deleting files always asks, and everything is still recorded. Choose Strict to approve each action.
- **Green approve buttons**, on the overlay and in Boom Control.
- **The AI sees the window it works in, never your screen.** A covered window is never pictured from your screen. A minimized window comes back behind your work without taking the front. The AI brings a window forward only when it wants you to look, and says so.
- **Browsers keep working when covered or minimized** (Settings switch, Brave, Chrome, Edge; check brave://policy).
- **Code mode (optional)**: the AI writes one program that calls many Boom tools, in Microsoft's MXC sandbox (no network, only allowed folders). Install it from Settings (about 12 MB) or in Setup. Boom lists missing coding tools (Git, Node.js, Python) and installs them when you click. Uninstall can remove them.
- **Long work goes on in the background** past 45 s (job_output), even if the chat stopped waiting.
- **Big results** keep their start, end, errors and warnings in view; the rest is kept for result_read.
- **The AI always sees why a call failed**, and is reminded when it repeats the same call.
- **MCP Python SDK 2.2.0.**

Refresh the plugin in ChatGPT and Codex: new tools run_code, job_output, job_kill, result_read, ask_user.

### Released in r48 (patch for r47): background work that stays in the background, replies that load

- **Much smaller screen pictures for the AI.** Before, every look or press on the screen sent a PNG of up to 900 KB, so a long job put tens of MB of pictures into one reply, and ChatGPT showed "This response couldn't load" or sent nothing back after finishing. Now they are JPEG of about 200 KB at most, and a press through UI Automation returns only what changed, without a picture (one can be asked for).
- **The browser no longer jumps over your work again and again.** Opening a tab in your browser was reported as failed although it opened (the address bar hides "www."), so the AI opened it again and the browser came forward each time. Now the tab is found, and the window you were using comes back to the front right after the tab opens.
- **The old click and text tools no longer use the real mouse.** They press through UI Automation only and never bring a window forward; the real mouse goes through Computer Use, which asks you first.
- **If a reply does not load, tell the AI "summarize".** It reads what Boom already did before answering, instead of doing it again.
- **The overview in Boom Control lists the programs Boom started**, with Show window and Force close (only programs Boom started itself).

### Released in r47: work that is delivered must work

- **Work always starts; open questions go on the task card.** Before, Boom refused to start until every question was answered, and the AI went on without a card or checks. Now only opening or changing SketchUp and Blender waits for the answer.
- **Problems you point out during the work stay on the card until fixed.** The AI cannot finish as "done" while one is unanswered.
- **A 3D web page's work finishes only after Boom's own clean look at the final page.** The AI's own report is not enough.
- **Web pages are checked more closely:** parts with no position (not drawn), parts sized unlike their group, parts facing the wrong way, unnamed parts, and buttons and keys played without touching your screen.
- **New know-how:** world and local axes, moving and turning in 3D; security audits (Cloudflare's skill as published; an AI with its own skill uses its own first).
- **Computer Use:** a click on a control goes through UI Automation first and leaves your mouse alone; the real mouse and keyboard are asked for once per task and app.
- **Ask first:** understands "make it another file", and a follow-up keeps working in the same file.

### Released in r46 (patch for r45): updates no longer wait on the browser driver

- **Boom stops the browser driver (Playwright's node.exe) when the last browser it opened for an AI closes.** Before, the driver stayed after the browser closed, so Boom still would not update or stop. The next browser starts it again.
- **If r43–r45 still cannot update:** close the open browser on the overview, restart Boom, then update to this release.

### Released in r45 (patch for r44): updates no longer wait on a forgotten browser

- **A browser Boom opened for an AI and nobody uses is closed after 15 minutes.** Before, one an AI (WorkBuddy) opened and never closed kept Boom from updating or stopping for good.
- **The overview lists every such browser with a Close button**, including one whose window was closed by hand but not yet closed by Boom.
- **The "could not update" message** says where to see and close the open work.

### Released in r44: every AI app, work that runs on an ordinary PC, lighter screen work

From real use with WorkBuddy (a chair in SketchUp, two Chinese timber halls in Three.js, and a drawing in Paint):
- **AI apps:** Cline and Freebuff connect from Boom Control, and any other app gets a named connection to paste into its MCP settings, with its own key.
- **The task card names the app that did the work**, for example "WorkBuddy reported", instead of ChatGPT for every task.
- **New know-how:** clean, light models; a 3D model as a Three.js web page (drawn only when something changes, checked from every side with Chrome on the graphics card); Chinese timber halls by the 营造法式 (the frame on every slope, bracket sets at every corner, the roof curve computed by its rule, doors on pivots); and drawing in Paint.
- **Your brief decides**, and doors are shown partly open.
- **Solid Tools are a recommendation, not a rule:** the AI picks SketchUp's own tool that fits each part.
- **Boom's SketchUp check also reports the model's weight:** faces, triangles, textures, shadows and slivers left by cuts.
- **Boom checks 3D web pages itself (web_inspect):** every side and X-ray, parts counted by type with their positions, and the idle cost, in one call, with no test harness for the AI to write.
- **Lighter, surer screen work:** after each action the AI gets only the controls that changed (about 97% less in Paint), clicks work on drawing canvases, and controls can be found by name.

### Released in r43 (patch): AI apps really connect

- **WorkBuddy:** Boom writes the file WorkBuddy actually reads (`.workbuddy-ai\mcp.json`). If you connected it on r42, press connect once more.
- **Claude Desktop from the Microsoft Store:** Boom finds it now, and writes in the app's own folder.
- **Your apps' MCP:** another app's "boom" entry is no longer offered for import, because Boom would call itself in a loop; Boom refuses it if anyone tries.

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
