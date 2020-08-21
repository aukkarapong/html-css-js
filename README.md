# HTML5 + CSS + JS

## HTML

### สรุป Tag HTML ที่ใช้บ่อย

```html
<!-- -->

<!DOCTYPE html>

<html></html>

<head></head>

<body></body>

<div></div>

<section></section>

<header></header>

<footer></footer>

<ul>
  <li></li>
  <li></li>
</ul>

<ol>
  <li></li>
  <li></li>
</ol>

<h1></h1>

<h2></h2>

<h3></h3>

<h4></h4>

<a></a>

<p></p>

<strong></strong>

<span></span>
<label></label>

<table>
  <tr>
    <th></th>
    <th></th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>
</table>

<img />

<form name="" id="" action="" method="POST">
  <input type="hidden" />
  <input type="text" />
  <input type="file" />
  <input type="checkbox" />
  <input type="date" />
  <input type="email" />
  <input type="number" />
  <input type="password" />
  <input type="radio" />
  <textarea></textarea>
</form>

<button type="button"></button>
<button type="reset"></button>
<button type="submit"></button>
```

### สรุป Attrinute ที่ใช้บ่อย

```text
id=""
class=""

**สำหรับ tag input & button**
name=""
value=""

**สำหรับ tag form**
method="POST"
method="GET"
```

### สรุป Tag HTML ที่ไม่ต้องปิดท้าย หรือปิดท้ายด้วย />

```html
<br />
<img />
<input type="hidden" />
<input type="text" />
<input type="file" />
<input type="checkbox" />
<input type="date" />
<input type="email" />
<input type="number" />
<input type="password" />
<input type="radio" />
```

---

## CSS

### CSS selector

#### 1. Simple selectors (select elements based on name, id, class)

```css
/* select จากชื่อ Tag */
p {
  color: red;
}

/* select ขาด id */
#my-header {
  background-color: red;
}

/* select จากชื่อ class */
.my-sub-header {
  font-size: 14px;
}
```

ส่วน property ต่าง ๆ ของ css สามารถศึกษาเพิ่มเติมได้ใน `https://www.w3schools.com/css/`

---

## Javascript

### วิธีการเขียน Javascript

#### **1. การเขียน Javascript ไว้ในส่วน head ของ html**

```html
<!DOCTYPE html>
<html>
  <head>
    <script>
      function myFunction() {
        document.getElementById("demo").innerHTML = "Paragraph changed.";
      }
    </script>
  </head>
  <body>
    <h1>A Web Page</h1>
    <p id="demo">A Paragraph</p>
    <button type="button" onclick="myFunction()">Try it</button>
  </body>
</html>
```

#### **2. การเขียน Javascript ไว้ในส่วน body ของ html**

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>A Web Page</h1>
    <p id="demo">A Paragraph</p>
    <button type="button" onclick="myFunction()">Try it</button>

    <script>
      function myFunction() {
        document.getElementById("demo").innerHTML = "Paragraph changed.";
      }
    </script>
  </body>
</html>
```

#### **3. การเขียน Javascript แยกออกมาเป็นไฟล์ .js**(สมมติตั้งชื่อว่า myScript.js)

\*\*\* แนะนำให้ใช้วิธีนี้ \*\*\*

```js
function myFunction() {
  document.getElementById("demo").innerHTML = "Paragraph changed.";
}
```

และจะต้องทำการเรียกใช้ในหน้า html ตามตัวอย่าง

```html
<script src="myScript.js"></script>
```

#### **Function**

```js
function myFunction(param1, param2) {
  var concatParam = param1 + param2;
  alert(concatParam);
}
```

```html
<!-- การเรียกใช้งานในหน้า html -->
<button type="button" onclick="myFunction('param1-value', 'param2-value')">
  Click Me
</button>
```

#### **JavaScript HTML DOM EventListener**

```js
// my-script.js
document.getElementById("myBtn").addEventListener("click", displayDate);

function displayDate() {
  document.getElementById("demo").innerHTML = Date();
}
```

```html
<!-- my-html.html -->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>My-HTML</title>
  </head>

  <body>
    <h2>JavaScript addEventListener()</h2>

    <p>
      This example uses the addEventListener() method to attach a click event to
      a button.
    </p>

    <button id="myBtn">Try it</button>

    <p id="demo"></p>

    <script src="my-script.js"></script>
  </body>
</html>
```

จะเห็นว่า `<script src="my-script.js"></script>` จะ import ไฟล์ ไว้ด้านล่างสุด เนื่องจากต้องทำการสร้าง HTML element `<button id="myBtn">Try it</button>` และ `<p id="demo"></p>` ก่อน ถ้าเรา import ไว้ข้างบน ตัวจับ event listener ของ javascript จะหา tag `button id="myBtn"` และ `p id="demo"` ไม่เจอ หน้าเว็บเราจะ click ไม่ได้ตามที่ต้องการ
