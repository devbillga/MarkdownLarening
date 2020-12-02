# แก้ไขไฟล์ image โดยใช้ *Jimp*
## ติดตั้ง Package jimp
[อ่านเพิ่มเติม](https://www.npmjs.com/package/jimp)

    npm install --save jimp
นำ Package เข้ามาทำงานใน โปรเจ็ค  

    const Jimp = require("jimp");
## นำไฟล์รูปมาใช้งาน
    const image = Jimp.read("ที่อยู่และชื่อไฟล์รูปภาพ"); 
## การสร้างภาพใหม่
    new Jimp  ( 256 , 256 , ( err , image ) => {     
        ภาพนี้มีขนาด 256 x 256 ทุกพิกเซลตั้งค่าเป็น 0x00000000
    } ) ;
## บันทึกภาพ
    image.write("ที่อยู่และชื่อไฟล์รูปภาพ") 
    หรือ 
    image.writeAsync("ที่อยู่และชื่อไฟล์รูปภาพ")
## เพิ่มข้อความในรูป
    const font = Jimp.loadFont(Jimp.FONT_SANS_16_WHITE)
    image.print(font, 0, 0, 'Hello world!')
## ปรับขนาดภาพ
    image.resize(250, 250)
## ปรับขนาดความกว้าง หรือสูงเป็น 250 และปรับขนาดให้เหมาะสม
    image.resize(Jimp.AUTO, 250)
    image.resize(250, Jimp.AUTO)
## เพิ่มการล้างซีเปีย(สีน้ำตาลดำ)ลงในภาพ
    image.sepia()
## ปรับแต่งแต่ละพิกเซล
    image.pixelate(100)
    หรือ
    image.pixelate(5, 50, 50, 190, 200) //pixe,x, y, w, h
## Clone รูปภาพ
    const image2 = image.clone()
## เบลอภาพ
    image.gaussian(1)
    หรือ
    image.blur(1)
## แปลงภาพ
    image.invert()
## ตั้งค่าความสว่าง -1 to +1
    image.brightness( 0.5 )
## กำหนดคุณภาพ 0-100
    image.quality(100)
## เปลี่ยนเป็นโทนสีเทา
    image.greyscale()
## เอฟเฟกต์โกสต์ (ภาพซ้อน)
    const image2 = image.clone()
    image.composite(image2, 5, 0, {
        mode: Jimp.BLEND_MULTIPLY,
        opacitySource: 0.5,
        opacityDest: 0.9
    })
## เอฟเฟกต์ลายนูน (เงา)
    image.convolute([[-2, -1, 0], [-1, 1, 1], [0, 1, 2]])
#
## การจัดการสี
    image.color([
        { apply: 'hue', params: [-90] },
        { apply: 'lighten', params: [50] },
        { apply: 'xor', params: ['#06D'] }
    ])
ตัวปรับแต่ง

Modifier | Description
--------------------- | ---------------------
lighten {amount}	| ทำให้สีจางลงตามจำนวนที่กำหนดจาก 0 ถึง 100 การให้ 100 จะทำให้สีขาวเสมอ (ทำงานผ่าน [TinyColor](github.com/bgrins/TinyColor))
brighten {amount}	| ปรับสีให้สว่างขึ้นตามจำนวนที่กำหนดตั้งแต่ 0 ถึง 100 
darken {amount}	 | ทำให้สีเข้มขึ้นตามจำนวนที่กำหนดจาก 0 ถึง 100 การให้ 100 จะทำให้สีดำเสมอ
desaturate {amount} |ลดความอิ่มตัวของสีตามจำนวนที่กำหนดจาก 0 ถึง 100 การให้ 100 จะเหมือนกับการเรียก greyscale
saturate {amount} |	ทำให้สีอิ่มตัวตามจำนวนที่กำหนดตั้งแต่ 0 ถึง 100 
greyscale {amount} |เปลี่ยนสีเป็นสีเทา
spin {degree} |	หมุนสีตามจำนวนที่กำหนดตั้งแต่ -360 ถึง 360 การโทรด้วย 0, 360 หรือ -360 จะไม่ทำอะไรเลย - เนื่องจากจะกำหนดเฉดสีให้กลับไปเป็นแบบเดิม
hue {องศา} |	การหมุน
mix {color, amount} |ผสมสีตามค่า RGB, amount คือความทึบของสีที่ซ้อนทับ
tint {amount} |	ผสมกับสีขาว
shade {amount} |ผสมกับสีดำ
xor {color} |สองสีเป็นบิตฟิลด์และใช้การดำเนินการ XOR กับคอมโพเนนต์สีแดงสีเขียวและสีน้ำเงิน
red {amount} |	แก้ไขส่วนสีแดงตามที่กำหนด
green {amount} |	แก้ไขส่วนสีเขียวตามที่กำหนด
blue {amount} |	แก้ไขส่วนสีน้ำเงินตามที่กำหนด