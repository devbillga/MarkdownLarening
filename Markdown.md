---
title: วิธีเขียน Markdown
description: 'ลองสร้างไฟล์ Markdown ด้วย @nuxt/content และทำเป็น blog เพื่อไปแสดงหน้า blog'
createdAt: '2020-08-16T01:58:51+07:00'
---

ใน VS Code ดูวิว Markdown กด F1 พิมพ์ Markdown หรือกด Ctrl+K+V  
สวัสดีครับ
บล้อกนี้เขียนด้วย `@nuxt/content` โดยใช้ Markdown

# หัวข้อ ใช้ h1-h6
## h2
<h4>h4</h4>

###### h6 

    ใช้ # หน้าข้อความ(ใส่ # จำนวนตามขนาด) หรือ Tag <h1></h1>
#
## จัดการข้อความตัวเอียงและหนา
*This is text will* __be tialic__  
_This is **text will** be tialic_
    
    ใช้ * หรือ _ (ตัวเอียง) | และ ** หรือ __ (ตัวหนา)
        *This is text will* __be tialic__  
        _This is **text will** be tialic_
#
## การขึ้นบรรทัดใหม่
    1.ใช้ Spacebar(เคาะ) 2 ครั้ง หลังข้อความที่จะขึ้นบรรทัดใหม่
    2.ใช้ # หรือ ## ค้นบรรทัด
#
## การใส่โค้ด
การใช้ โค้ดแบบที่ 1  

    1.ใช้ Tab
    2.ใช้ ` โค้ด `
    3.ใช้ 
        ```(ภาษา) 
        โค้ด 
        ```
การใช้ `โค้ดแบบที่ 2`  
การใช้ โค้ดแบบที่ 3
```javascript
export const mutations = {
  set_drawer(state, newVle) {
    state.drawer = newVle
}
```
#
## ใส่ Link ในเอกสาร
[ไปที่ Test Link](#Test-Link)

    [ไปที่ TestLink](#Test-Link)
##
## ใส่ Link นอกเอกสาร     
[Devahoy](https://devahoy.com)

    [Devahoy](https://devahoy.com)
#
## ทำสัญลักษณ์รายการ (Bullet) 
* name
    - some
    * tee
- lastname
##

    ใช้ * หรือ - หน้าข้อความ  
#
## แสดงข้อมูลรายการแบบมีหมายเลขกำกับ(Number Lists)
1. sunday
1332. monday
2. tuesday  
##
    ใช้ ตัวเลขอะไรก็ได้ตามด้วย . (จุด) หน้าข้อความ 
        1.sunday
#
## ทำตัวเลือกหรือติ๊กถูก
- [ ] Apple
- [ ] Tree
- [ ] Lemon
- [x] Cup
#
# Test Link
## ใส่รูปภาพ ในโปรเจ็ค
![vuetify](../../static/v.png)

    ![vuetify](../../static/v.png)
## ใส่รูปภาพ ข้างนอก
![gitlab](https://nuxtjs.org/img/companies/original/gitlab.svg)

    ![gitlab](https://nuxtjs.org/img/companies/original/gitlab.svg)

#
## สร้างตาราง
Col1  | Col2  |  Col3 | Col4
----- | ----- | ----- | ----- |
Test1 | Test1 | Test1 | Test1 |
Test2 | Test2 | Test2 | Test2 |
Test3 | Test3 | Test3 | Test3 |

    Col1  | Col2  |  Col3 | Col4
    ----- | ----- | ----- | ----- |
    Test1 | Test1 | Test1 | Test1 |
    Test2 | Test2 | Test2 | Test2 |
    Test3 | Test3 | Test3 | Test3 |

