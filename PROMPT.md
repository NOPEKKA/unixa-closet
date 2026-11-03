# Prompt: reposition navigation and main actions (UNIXA)

Reference prototype (match its layout): https://nopekka.github.io/unixa-closet/
Prototype source: `index.html` in this repo (single file, front-end only, sample data).

```
Reposition the navigation and main actions of the existing UNIXA app (Next.js, next-intl, TH/EN). Do NOT rebuild it. Keep all backend APIs, auth, orders, chat and QR logic. Change only layout, positions and labels.

GOAL: a first-time user can use it with no explanation, and nothing looks cluttered.

1) REMOVE THE SIDEBAR
Delete the always-open left sidebar. No hamburger drawer on desktop or tablet.

2) DESKTOP + TABLET (>=768px): TWO-ROW TOP BAR
Row 1 (left to right):
- Logo -> Home
- Search box (grows to fill the width)
- Primary button "ลงขายเสื้อผ้า / Sell clothes" (+ icon)
- Chat icon (badge = unread)
- Bell icon (badge = unread)
- Avatar menu
Row 2 (every link has an icon AND a word, no more than 6):
- หน้าแรก Home
- เลือกดูเสื้อผ้า Browse clothes
- บันทึกไว้ Saved
- คำสั่งซื้อ Orders (badge = orders needing action)
- ตู้ของฉัน My closet (sellers only; badge = new orders)
- ช่วยเหลือ Help (pushed to the far right)
Do not put a heart/saved icon or a cart in row 1.

3) AVATAR MENU (dropdown from the avatar)
Header: name + "ดูโปรไฟล์". Then:
- Buy: คำสั่งซื้อ, รายการที่บันทึกไว้
- Sell: ตู้เสื้อผ้าของฉัน, ออเดอร์ที่ขาย, ลงขายเสื้อผ้า (non-sellers see "เริ่มขายเสื้อผ้า" instead)
- ตั้งค่า, ช่วยเหลือ
- Language TH/EN toggle, Theme system/light/dark toggle
- ออกจากระบบ
Remove "Account / Profile / Settings" from any sidebar. Profile and Settings live only here.

4) HOME PAGE ORDER
Hero (search + "ดูเสื้อผ้าทั้งหมด" + "ลงขายเสื้อผ้า") -> heading "เลือกตามหมวด" with the 9 category pills (เสื้อ, กางเกง, กระโปรง, เดรส, เสื้อคลุม, ชุดนักศึกษา, ชุดกีฬา, รองเท้า, อื่น ๆ) -> ลงใหม่ -> เสื้อผ้าแนะนำ -> เสื้อผ้าทั้งหมด.
Categories appear ONLY here, not in the top bar. Remove "Today's Schedule" from Home.

5) PHONE (<768px)
- Top bar: logo, search, chat icon, bell icon. No sell button, no row 2, no avatar.
- Fixed bottom bar, 5 items, icon + word:
  Buyer: หน้าแรก | เลือกดู | คำสั่งซื้อ | บันทึก | เมนู
  Seller: หน้าแรก | เลือกดู | คำสั่งซื้อ | ตู้ของฉัน | เมนู
  (My closet shows the new-order badge and is highlighted on all closet pages and the sell page.)
- "เมนู" opens a bottom sheet: profile row, Buy / Sell / Account groups, ช่วยเหลือ, language, theme, sign out.
- Browse: 2-column cards, floating "เรียงตาม | ตัวกรอง" pill above the bottom bar.
- Listing page: sticky bar above the bottom bar with price + heart + "จองนัดรับ".
- My closet: header buttons "ดูหน้าตู้" and "ลงขายเสื้อผ้า" side by side at full width; the 5 tabs (ภาพรวม, รายการ, ออเดอร์, ดัน, ยอดขาย) shown as an icon + short label grid, no horizontal scrolling.
- Settings: the section list becomes a horizontal chip row pinned under the top bar.

6) ACTIONS THAT MOVE
- Cart, checkout and receipt pages are removed. The listing page has ONE button "จองนัดรับ" (pick day, time and place first, then confirm in a dialog).
- Seller listing rows: one "จัดการ" button opening a menu: แก้ไขราคา/สภาพ, ลดราคา, ดันขึ้นหน้าแรก, ขายแล้ว (ขายนอกแอป), พักรายการ, ลบรายการ, ยกเลิกการจอง. No row of separate edit/discount/promote buttons.
- Chat is a fixed icon (header on phone, bottom-right on desktop), not draggable.
- Remove the notification ON/OFF switch from the navbar; keep it in Settings -> Notifications.
- Remove the global bottom announcement bar.

7) RULES
- Every nav item = icon + label. Max 6 in row 2, max 5 in the phone bottom bar.
- No horizontal scrolling for primary navigation at any width >=360px.
- Touch targets >=44px on phone.
- Keep the existing color tokens and the light/dark theme.
- Make sure <meta name="viewport" content="width=device-width, initial-scale=1"> is present.
- Use next-intl for all labels; do not hard-code Thai or English.

Acceptance checks:
- No sidebar anywhere.
- Phone seller sees "ตู้ของฉัน" in the bottom bar without opening any menu.
- Categories appear once (Home), not in the top bar.
- No cart icon or page exists.
```
