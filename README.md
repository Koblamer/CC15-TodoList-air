# 0

Setup Project with CreateReactApp (CRA)

Script สำหรับติดตั้ง create-react-app ลงใน global (เครื่อง)
sudo npm i -g create-react-app (1 time ต่อเครื่อง)

Script สร้างโปรเจคก์โดย CRA
npx create-react-app <project-name> ( 1 ครั้ง / Project)

SYNTAX : npm run <script_name> === npx <actual_script>
npm run start === npx react-scripts start

// npm run == ดู package.json ที่ key scripts
// npm run start === ดู package.json ที่ key scripts และคีย์ย่อย start => react-scripts start
// เอา react-scripts start มารัน npx ให้

# 1 Setup Project

- `npx create-react-app <project-name>`
- `cd <project-name>`
- `npm start` or `npm run start` or `npx react-scripts start`
- auto open browser localhost:3000

# 2 About Project

- Other Code / Dependencies อยู่ใน node_mudules
- ลบทิ้งได้
- ติดตั้งใหม่ด้วย `npm install` จะทำการติดตั้ง dependencies ที่อยู่ใน package.json ให้อัตโนมัติ
- Code เราเองอยู่ใน src/

#3 : CSS setup

#### 3.1 : ติดตั้ง scss

ติดตั้ง sass เพื่อช่วยให้การเขียน CSS แบบ BEM สะดวกมากขึ้น
รันคำสั่ง npm install sass ลงใน terminal (อย่าลืม check path ว่าอยู่ที่ root project แล้ว : ตำแหน่งที่มี file package.json)
ตรวจสอบ dependencies ในไฟล์ package.json ว่ามี sass แล้ว

#### 3.2 : setup index.scss

ไฟล์ index.css : ให้แปลงนามสกุลไฟล์ เป็น index.scss
ไฟล์ index.js : เปลี่ยนการ import จาก index.css เป็น index.scss

#### 3.3 : CSS Global Reset

ไฟล์ index.scss : เขียน css rule เพื่อลบ default padding,margin ต่างๆ รวมถึงวิธีการวัดขนาดของ Box-model

_,
_::after,
\*::before {
margin: 0;
padding: 0;
box-sizing: inherit;
}

html {
font-size: 62.5%; /_equal font-size : 10px_/
}

body {
box-sizing: border-box;
}

#### 3.4 : Typography

ไฟล์ index.scss : ให้ทำการ import google font

@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@200;300;400;500;600;700;800;900&family=Source+Sans+Pro:wght@400;600;700&display=swap');

ไฟล์ index.scss : ทำการเพิ่ม font หลักของ application (Nunito) ลงใน tag body

body {
font-family: 'Nunito', -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu',
'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
}

#### 3.5 : Color

knowledge : scss มีความสามารถในการสร้างตัวแปรไว้ใช้ได้
ไฟล์ index.scss : สร้างตัวแปรสำหรับเก็บสีหลักๆของ web-application

$primary: #db4c3f;
$grey-light: #eaeaea;
$grey-dark: #808080
$white: #fff;
