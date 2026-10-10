# punpun Agent — ตัวติดตั้งสำหรับ Windows

โปรแกรม Agent ของ punpun ทำงานบน PC ของคุณเอง ใช้ตัดคลิปและส่งคลิปไปโพสต์บนโทรศัพท์ Android ผ่าน USB

repo นี้มีแค่ไฟล์ติดตั้ง ซอร์สโค้ดของ punpun ไม่ได้อยู่ที่นี่

## ดาวน์โหลดและติดตั้ง

1. ไปที่ [Releases](../../releases/latest) แล้วดาวน์โหลด `punpun-agent-setup-<เวอร์ชัน>.exe`
2. (แนะนำ) ตรวจไฟล์ใน PowerShell แล้วเทียบค่ากับไฟล์ `.sha256` ในหน้า Release และกับค่าที่หน้า **Agents** บนเว็บ punpun แสดง:
   ```powershell
   Get-FileHash .\punpun-agent-setup-<เวอร์ชัน>.exe -Algorithm SHA256
   ```
3. ดับเบิลคลิกเพื่อติดตั้ง ถ้า Windows ขึ้น "Windows protected your PC" ให้กด **More info → Run anyway** เพราะไฟล์ยังไม่ได้ลงนามดิจิทัล
4. หน้าต่างตั้งค่าจะเปิดขึ้นมา ให้ใส่ **รหัสเชื่อมต่อ** จากหน้า Agents บนเว็บ

ใช้งานต้องมีบัญชี punpun

## ซอฟต์แวร์ของบุคคลที่สามที่แนบมา

ตัวติดตั้งมีโปรแกรมเหล่านี้แนบมาโดยไม่ได้แก้ไข ไฟล์ licence และ README ของแต่ละตัวอยู่ในโฟลเดอร์ที่ติดตั้ง (`adb\`, `scrcpy\`) และดูได้ด้วยคำสั่ง `punpun-agent licenses`

| ซอฟต์แวร์ | Licence | ซอร์สโค้ด |
|---|---|---|
| Android SDK Platform-Tools (`adb`) | Apache License 2.0 (`LICENSE-THIRD-PARTY-Apache-2.0.txt`) | https://android.googlesource.com/platform/packages/modules/adb/ |
| scrcpy 4.1 | Apache License 2.0 | https://github.com/Genymobile/scrcpy/tree/v4.1 |
| FFmpeg (DLL ที่มากับ scrcpy) | LGPL 2.1 หรือใหม่กว่า | https://ffmpeg.org/download.html ใช้เวอร์ชันตามที่ scrcpy v4.1 ระบุ |
| SDL3 (DLL ที่มากับ scrcpy) | zlib | https://github.com/libsdl-org/SDL |
| libusb (DLL ที่มากับ scrcpy) | LGPL 2.1 หรือใหม่กว่า | https://github.com/libusb/libusb |

DLL ที่เป็น LGPL ถูกแนบเป็นไฟล์แยก ไม่ได้ลิงก์รวมเข้ากับโปรแกรมของเรา คุณเปลี่ยนเป็นเวอร์ชันที่ build เองได้โดยวางทับในโฟลเดอร์ `scrcpy\`

ส่วนอื่นๆ ของ punpun Agent © punpun สงวนลิขสิทธิ์
