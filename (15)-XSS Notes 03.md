
# أنواع ثغرات XSS مع أمثلة

## 1. XSS غير المنعزلة (Reflected XSS)
**الوصف**: يحدث عندما يتم إدخال كود في طلب HTTP ويتم إرجاعه مباشرة في استجابة الصفحة.

**مثال**:
```plaintext
https://example.com/search?q=<script>alert('XSS')</script>
```

---

## 2. XSS المخزنة (Stored XSS)
**الوصف**: يحدث عندما يتم تخزين كود JavaScript في قاعدة بيانات ويُعرض لاحقًا على المستخدمين.

**مثال**:
إذا قمت بإدخال الكود التالي في نموذج تعليقات:
```html
<script>alert('Stored XSS')</script>
```

---

## 3. XSS باستخدام data URIs
**الوصف**: استغلال ثغرات XSS من خلال تحميل كود JavaScript باستخدام data URIs.

**أمثلة**:
- **Alert**:
    ```plaintext
    https://example.com#data:text/javascript,alert('Hello from Data URI!')
    ```

- **تغيير عنوان الصفحة**:
    ```plaintext
    https://example.com#data:text/javascript,document.title='Hacked Title'
    ```

- **إدخال نص في صفحة**:
    ```plaintext
    https://example.com#data:text/javascript,document.body.innerHTML='<h1>You have been hacked!</h1>'
    ```

- **تنفيذ دالة بعد فترة**:
    ```plaintext
    https://example.com#data:text/javascript,setTimeout(() => alert('Executed after 2 seconds!'), 2000)
    ```

- **إضافة رسالة إلى وحدة التحكم**:
    ```plaintext
    https://example.com#data:text/javascript,console.log('This is a log from Data URI!')
    ```

- **استدعاء دالة موجودة**:
    ```plaintext
    https://example.com#data:text/javascript,existingFunction()
    ```

---

## 4. DOM-based XSS
**الوصف**: يحدث عندما يتم تعديل DOM من خلال كود JavaScript على الصفحة، مما يسمح بتنفيذ أكواد ضارة.

**مثال**:
إذا كان هناك كود JavaScript في الصفحة يقوم بتنفيذ كود بناءً على معلمات URL:
```javascript
var userInput = location.hash.substr(1); // يتم أخذ البيانات من الـ hash
eval(userInput); // يؤدي إلى تنفيذ الكود
```
يمكنك استخدام:
```plaintext
https://example.com#alert('DOM XSS')
```

---

## 5. XSS عبر الـ JSONP
**الوصف**: يحدث عندما تسمح التطبيقات باسترجاع بيانات عبر JSONP، مما يُمكن المهاجم من إدخال كود JavaScript.

**مثال**:
```plaintext
https://example.com/api?callback=<script>alert('JSONP XSS')</script>
```

---
