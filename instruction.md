# POS System Requirement Document - Small Food Shop

## 1. Business Requirements (ව්‍යාපාරික අවශ්‍යතා)

මෙම පද්ධතියේ ප්‍රධාන අරමුණ වන්නේ කෑම කඩයේ දෛනික විකුණුම් කළමනාකරණය කිරීම සහ බිල්පත් නිකුත් කිරීමයි.

### 1.1 මූලික කාර්යයන් (Core Functions)
* **Menu Management:** කෑම වර්ග, මිල ගණන් සහ කාණ්ඩ (Categories - e.g., Rice, Kottu, Drinks) ඇතුළත් කිරීම සහ වෙනස් කිරීම.
* **Billing / Checkout:** පාරිභෝගිකයා ඇණවුම් කරන දේවල් list එකකට එකතු කර, මුළු මුදල (Total) ගණනය කර බිල්පතක් සෑදීම.
* **Inventory Tracking:** කඩේ තියෙන බඩු ප්‍රමාණය (Stock) අඩු වන ආකාරය බැලීම.
* **Sales History:** දිනපතා සිදු වූ විකුණුම් වාර්තා (Daily Reports) බැලීම.
* **Print Receipt:** බිල්පතක් thermal printer එකකින් print කිරීමට හෝ PDF එකක් ලෙස ලබා ගැනීමට හැකි වීම.

### 1.2 පරිශීලක අවශ්‍යතා (User Needs)
* ඉතා සරල සහ වේගවත් UI එකක් තිබීම (කෑම කඩවල තියෙන කාර්යබහුල බව නිසා).
* Mouse එක පාවිච්චි නොකර Keyboard shortcuts වලින් වැඩ කළ හැකි වීම.
* Internet නැති අවස්ථාවලදී පවා සිස්ටම් එක වැඩ කිරීම (Offline Capability).

---

## 2. Technical Requirements (තාක්ෂණික අවශ්‍යතා)

මෙම පද්ධතිය ගොඩනැගීමට භාවිතා කරන තාක්ෂණයන් සහ ඒවායේ කාර්යභාරය මෙසේය.

### 2.1 Technology Stack
* **Frontend:** HTML5 (ව්‍යුහය සඳහා), Tailwind CSS (සැලසුම/Design සඳහා).
* **Logic:** Vanilla JavaScript (ES6+).
* **Database:** Dexie.js (Browser එකේ IndexedDB භාවිතා කරමින් දත්ත ගබඩා කිරීමට).
* **Icons:** Lucide Icons හෝ FontAwesome.

### 2.2 Functional Modules
1.  **Dashboard:** දවසේ මුළු ආදායම සහ විකුණුම් ප්‍රමාණය පෙන්වන සාරාංශය.
2.  **POS Screen:**
    * Search Bar (කෑම වර්ග සෙවීමට).
    * Category Filters.
    * Cart (එකතු කරගත් කෑම ලැයිස්තුව).
    * Payment Modal (මුදල් ගෙවන ආකාරය සහ ඉතිරි මුදල ගණනය කිරීම).
3.  **Product Management:** කෑම වර්ග add/edit/delete කළ හැකි form එකක්.
4.  **Order History:** පරණ බිල්පත් නැවත බැලීමේ හැකියාව.

### 2.3 Data Schema (දත්ත ගබඩා වන ආකාරය - Dexie.js)
පද්ධතියේ ප්‍රධාන වශයෙන් table 3ක් අවශ්‍ය වේ:
* `products`: `id, name, price, category, stock`
* `orders`: `id, datetime, total_amount, payment_method`
* `order_items`: `id, order_id, product_id, quantity, unit_price`

---

## 3. Implementation Roadmap (ක්‍රියාත්මක කිරීමේ පියවර)

1.  **Setup:** මූලික HTML ෆයිල් එක හදාගෙන Tailwind CSS සහ Dexie.js library links එකතු කිරීම.
2.  **Database Initialization:** Dexie.js මගින් `pos_db` නමින් database එකක් සහ tables create කිරීම.
3.  **UI Design:** Tailwind CSS පාවිච්චි කරලා POS screen එකේ layout එක (Sidebar, Product Grid, Cart) හදාගැනීම.
4.  **Logic Development:**
    * කෑමක් click කළ විට cart එකට add වීම.
    * Quantity වෙනස් කරන විට total එක update වීම.
    * 'Checkout' button එක එබූ විට දත්ත database එකට save වීම.
5.  **Reporting:** Database එකේ තියෙන orders අරගෙන daily report එකක් පෙන්වීම.
6.  **Printing:** CSS `@media print` පාවිච්චි කරලා බිල්පත පමණක් print වීමට සැලැස්වීඋස් 