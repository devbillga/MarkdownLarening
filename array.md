---
title: ว่าด้วยเรื่อง Array ใน Javascript
description: 'ลองสร้างไฟล์ Markdown ด้วย @nuxt/content และทำเป็น blog เพื่อไปแสดงหน้า blog'
createdAt: '2020-08-16T01:58:51+07:00'
---
# Array.from
### พารามิเตอร์
    Array.from(arrayLike [, mapFn [, thisArg]])

#### arrayLike : อาร์เรย์หรือ string ที่ทำซ้ำเพื่อแปลงเป็นอาร์เรย์
#### mapFn *ไม่จำเป็น* : ฟังก์ชั่นเพื่อเรียกทุกองค์ประกอบของอาร์เรย์
#### thisArg *ไม่จำเป็น* : ใช้งานในขณะที่เมื่อมีการดำเนิน this.mapFn
### ส่งคืนค่า : อาร์เรย์ใหม่
````javascript
console.log(Array.from('foo'));
// ผลลัพธ์: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], x => x + x));
// ผลลัพธ์: Array [2, 4, 6]
````
# Array.isArray
### พารามิเตอร์
    Array.isArray(value)
#### value : ค่าที่จะตรวจสอบ
### ส่งคืนค่า : true ถ้าค่าเป็น Array,false ถ้าค่าไม่เป็น Array
````javascript
Array.isArray([1, 2, 3]);  // true
Array.isArray({foo: 123}); // false
Array.isArray('foobar');   // false
Array.isArray(undefined);  // false
````
# Array.of
## การสร้าง Array ใหม่ จากจำนวนตัวแปร
### พารามิเตอร์
    Array.of(element0[, element1[, ...[, elementN]]])
#### element : ค่าใช้ในการสร้างอาร์เรย์
### ส่งคืนค่า : อาร์เรย์ใหม่
````javascript
Array.of(7);       // [7] 
Array.of(1, 2, 3); // [1, 2, 3]

Array(7);          // อาร์เรย์ที่ค่าว่าง 7 ช่อง
Array(1, 2, 3);    // [1, 2, 3]
````
# Array.concat
## การรวม Array และ สร้าง Array ใหม่
### พารามิเตอร์
    const new_array = old_array.concat([value1, value2, ..., valueN])
#### value : ค่าหรือ Array ที่จะเชื่อมต่อเข้ากับอาร์เรย์ใหม่ หากไม่ใส่พารามิเตอร์ทั้งหมดจะส่งคืน Array สำเนา
### ส่งคืนค่า : อาร์เรย์ใหม่
````javascript
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);

console.log(array3);
// expected output: Array ["a", "b", "c", "d", "e", "f"]
````
# Array.copyWithin
## การคัดลอก ค่าภายในอาเรย์ มาแทนในตำแหน่งที่ต้องการ
### พารามิเตอร์
    arr.copyWithin(target, start, end])
#### target : ตำแหน่งที่ต้องการเปลี่ยน ถ้าติดลบ target จะนับจากท้าย
#### start *ไม่จำเป็น* : ตำแหน่งที่ต้องคัดลอกค่า
#### target : ตำแหน่งยุติการคัดลอกจาก start หากละเว้นจะคัดลอกจนถึง ตำแหน่งสุดท้าย
### ส่งคืนค่า : อาร์เรย์ที่แก้ไข
````javascript
const array1 = ['a', 'b', 'c', 'd', 'e'];

// คัดลอกตำแหน่ง 3 มาแทนในตำแหน่ง 0
console.log(array1.copyWithin(0, 3, 4));
// expected output: Array ["d", "b", "c", "d", "e"]

// copy to index 1 all elements from index 3 to the end
console.log(array1.copyWithin(1, 3));
// expected output: Array ["a", "d", "e", "d", "e"]
````
# Array.entries
## เพิ่ม key ให้กับ Array
### พารามิเตอร์
    array.entries()

### ส่งคืนค่า : ออบเจ็ค (object) 
````javascript
var a = ['a', 'b', 'c'];
var iterator = a.entries();

for (let e of iterator) {
  console.log(e);
}
// [0, 'a']
// [1, 'b']
// [2, 'c'] 
````
#  Array.every
## ส่งค่าไปตรวจสอบในฟังก์ชั่น ถ้ามีเพียงค่าเดียวไม่ผ่านก็จะคืนค่าเป็น false
### พารามิเตอร์
    arr.every(callback())
#### callback : ฟังก์ชันที่จะทดสอบสำหรับแต่ละองค์ประกอบ

### ส่งคืนค่า : true หรือ false
````javascript
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];
const array2 = [1, 41, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// expected output: true
console.log(array2.every(isBelowThreshold));
// expected output: false
````