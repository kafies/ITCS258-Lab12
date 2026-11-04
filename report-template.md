# Lab 12 report — One local Compose experiment

# รายงาน Lab 12 — ทดลอง Compose ในเครื่องด้วยแอปเดียว

Student ID / รหัสนักศึกษา:

Name / ชื่อ:

OS and Docker context / ระบบปฏิบัติการและ Docker context:

Repository URL / URL repository:

Dr. Pisit Praiwattana, your mentor in 2026

Complete required sections **01–04** using the gacha workshop. Use real commands/results and readable screenshots from **your own screen**. Export **`student_ID_lab12.PDF`** and submit one file to MyCourse by its posted deadline.

ทำส่วนบังคับ **01–04** ด้วย gacha workshop ใช้คำสั่ง/ผลจริงกับภาพอ่านได้จาก **หน้าจอตนเอง** ส่งออก **`student_ID_lab12.PDF`** แล้วส่งไฟล์เดียวใน MyCourse ตามกำหนด

## 01 · Folder, environment and readiness / โฟลเดอร์ environment และความพร้อม

- Docker Client/Server and Compose versions.
- Explain the folder roles: app source, Dockerfile, Compose files, `.env.example`, actual `.env`, SQL initialization.
- Show `config --quiet` and `config --services` results.
- Explain CLI interpolation versus container environment; show only sanitized configuration.

ตรวจเวอร์ชัน Engine/Compose อธิบายหน้าที่ไฟล์ แสดงผลตรวจ config และแยก interpolation ของ CLI ออกจาก environment ใน container ไม่แสดงข้อมูลลับจริง

Evidence and explanation / หลักฐานและคำอธิบาย:


## 02 · Compose keys and startup / Key และการเริ่มระบบ

- Explain the real `services`, `build`, `image`, `ports`, `environment`, `depends_on`, `healthcheck` and `volumes` settings.
- Show image build, stack startup, `ps` and useful logs.
- Show healthy app/database and actual `/health` output.
- Draw laptop → app and app → DB with hostnames and ports.

อธิบาย key จริง ผล build/start/ps/log และ health วาดการเชื่อมต่อเครื่อง→app กับ app→DB พร้อมชื่อและพอร์ต

Evidence and explanation / หลักฐานและคำอธิบาย:


## 03 · API and basic SQL / API และ SQL พื้นฐาน

- Use your own student ID in `/test` or equivalent API client.
- Show recharge1000 coins → exchange1000 coins →10gems → one draw → history.
- Record actual draw ID, result_name, rarity and created_at. COMMON is a valid result; SSR is not required.
- Show SQL connection, table list, SELECT matching the history and COUNT.
- Show the separate `-sql` wallet INSERT/SELECT practice.
- Explain 2% legendary probability and why a small experiment does not guarantee a fixed result count.

ใช้รหัสตนเองใน /test แสดงเติม/แลก/สุ่ม/อ่าน history เก็บแถวจริง ผล COMMON ใช้ได้ ไม่บังคับ SSR ตรวจ SQL, SELECT/COUNT ที่ตรงกัน และฝึก INSERT ด้วย wallet -sql แยก อธิบายความน่าจะเป็น 2%

Original draw ID / ID draw เดิม:

Original result + rarity / ผลและ rarity เดิม:

Original creation time / เวลาสร้างเดิม:

Evidence and explanation / หลักฐานและคำอธิบาย:


## 04 · Persistence and bind mounts / ข้อมูลถาวรและ bind mount

| Stage / ช่วง | DB container ID | Named volume | Original draw ID | Result + rarity + created_at |
| --- | --- | --- | --- | --- |
| Initial / เริ่มต้น | | | | |
| Restart / หลัง restart | | | | |
| Down/up / หลังสร้างใหม่ | | | | |

- Show actual restart/down/up commands and the API history/SQL read after each.
- After down/up show a **new DB container ID**, **same volume**, and **unchanged original draw**, without drawing/reinserting it again.
- Explain named volume versus the read-only `db/init.sql` bind mount.
- Verify source path/type; explain one real or predicted bind-mount pitfall and fix.
- Distinguish the PostgreSQL entrypoint (empty data directory only) from app bootstrap (`server.js` executes its copied SQL at every app startup). Explain why current `CREATE TABLE IF NOT EXISTS` does not change existing columns, why schema changes need migrations, and what rebuilding copied SQL can affect.
- แยก entrypoint ของ PostgreSQL ที่รันเมื่อ data directory ว่าง ออกจาก bootstrap ของแอปที่ `server.js` รัน SQL ที่คัดลอกทุกครั้งที่เริ่ม อธิบายว่า `CREATE TABLE IF NOT EXISTS` ไม่แก้ column เดิม และการแก้ SQL ใน image ต้อง rebuild พร้อมวาง migration อย่างตั้งใจ
- Explain `down` versus `down -v`, and why volume persistence is not backup.

แสดงคำสั่งกับผลอ่านหลังแต่ละขั้น หลัง down/up ต้องเห็น ID container ใหม่ volume เดิม และ draw เดิมโดยไม่สุ่มซ้ำ อธิบาย named volume เทียบ bind mount แบบ read-only ตรวจ path/ชนิดไฟล์ อธิบายข้อผิดพลาดกับวิธีแก้ รวมถึง init/migration, down/down -v และ persistence/backup

Evidence and explanation / หลักฐานและคำอธิบาย:


## In-room LA check / ตรวจ LA ในห้อง

Show your working experiment to the LA before leaving the room. Record a short summary of what you demonstrated and any correction you made.

แสดงการทดลองที่ทำงานได้ต่อ LA ก่อนออกจากห้อง บันทึกสั้น ๆ ว่าแสดงอะไรและแก้ไขสิ่งใด

Demonstration summary / สรุปสิ่งที่แสดง:


## Optional practice / ฝึกเพิ่มเติมทางเลือก

If you chose another backend/framework, briefly show how the same pattern applies. This is optional and does not replace the single required gacha experiment.

หากเลือกฝึกแบ็กเอนด์/framework อื่น ให้สรุปการใช้รูปแบบเดียวกัน ส่วนนี้เป็นทางเลือกและไม่แทนการทดลอง gacha ที่บังคับ


## Final check / ตรวจสอบก่อนส่ง

- All required parts 01–04 are present / ครบส่วนบังคับ 01–04
- Evidence comes from my own screen / ภาพจากหน้าจอตนเอง
- Original draw remains unchanged; no replacement was created / แถวเดิมไม่เปลี่ยนและไม่ได้สร้างแทน
- Repository URL and sanitized configuration included / มี URL repository และค่าตั้งไม่มีข้อมูลลับ
- Filename uses my actual ID: `student_ID_lab12.PDF` / ใช้รหัสจริงในชื่อไฟล์
- One PDF uploaded and checked for readability / ส่ง PDF เดียวและเปิดตรวจความชัดเจนแล้ว
