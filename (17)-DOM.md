### DOM (Document Object Model)

الـ **DOM** هو طريقة تمثيل محتوى صفحة الويب كأنها شجرة. كل عنصر في الصفحة (زي العناوين، الفقرات، الصور) بيكون جزء من الشجرة دي.

#### أهم النقاط عن DOM:

1. **الشجرة**: تخيل الصفحة كأنها شجرة، كل عنصر هو ورقة أو فرع.
2. **الوصول للعناصر**: تقدر تستخدم JavaScript علشان توصل لأي عنصر في الشجرة. زي:
   - `document.getElementById("id")`: بتجيب عنصر باستخدام الـ ID بتاعه.
3. **تعديل المحتوى**: تقدر تغيّر النص أو الشكل بتاع العناصر بسهولة.
4. **الأحداث**: تقدر تخلي الصفحة تتفاعل مع المستخدم، زي الضغط على زر.

### الربط بين DOM و XSS

**الـ DOM** هو تمثيل الصفحة في المتصفح. لما تتفاعل مع الصفحة، زي ما تضيف نص أو تغير محتوى، أنت بتتعامل مع الـ DOM.

#### إزاي XSS بتستخدم الـ DOM:

1. **إدخال المستخدم**:
   - لو فيه حقل في الصفحة (زي نموذج) يتيح للمستخدم كتابة نص، ممكن يكتب نص عادي أو سكربت ضار.
   - لو الموقع مش بيتحقق من النص أو ينظفه، المهاجم ممكن يكتب حاجة زي:
     ```html
     <script>alert('XSS!');</script>
     ```

2. **تعديل الـ DOM**:
   - لو استخدمت `innerHTML` لتحديث المحتوى في الصفحة، السكربت الضار اللي كتبه المهاجم هيتنفذ.
   - مثال:
     ```javascript
     const userInput = "<script>alert('XSS!');</script>";
     document.getElementById("output").innerHTML = userInput; // خطر
     ```

3. **نتيجة XSS**:
   - لما السكربت يتنفذ، المهاجم يقدر يعمل حاجات ضارة، زي:
     - سرقة معلومات حساسة (زي الكوكيز).
     - تنفيذ عمليات غير مرغوب فيها على حساب المستخدم.

#### كيفية الوقاية من XSS:

1. **تجنب استخدام `innerHTML`**:
   - استخدم `textContent` أو `createElement` بدلاً من `innerHTML` علشان تحمي نفسك من XSS.

   **مثال**:
   ```javascript
   const userInput = "<script>alert('XSS!');</script>";
   document.getElementById("output").textContent = userInput; // آمن
   ```

2. **تنظيف المدخلات**:
   - استخدم مكتبات مثل DOMPurify لتنظيف أي مدخلات غير موثوقة.

   **مثال باستخدام DOMPurify**:
   ```javascript
   const userInput = "<script>alert('XSS!');</script>";
   const cleanInput = DOMPurify.sanitize(userInput);
   document.getElementById("output").innerHTML = cleanInput; // آمن
   ```

3. **التحقق من المدخلات**:
   - تأكد من المدخلات باستخدام تعبيرات منتظمة (Regex).

   **مثال**:
   ```javascript
   function isValidInput(input) {
       return /^[a-zA-Z0-9\s]*$/.test(input); // يسمح بحروف وأرقام ومسافات بس
   }
   ```

4. **استخدام Headers أمان**:
   - استخدم `Content Security Policy (CSP)` لتحديد المصادر المسموح بها لتشغيل السكربتات.

### BOM (Browser Object Model)

الـ **BOM** هو نموذج يُستخدم للتفاعل مع المتصفح، وبيوفر لك وسيلة للوصول إلى ميزات المتصفح ووظائفه.

#### أهم النقاط عن BOM:

1. **كائن النافذة**: 
   - كائن `window` هو الكائن العام الذي يمثل نافذة المتصفح. يتضمن جميع خصائص المتصفح ويمثل السياق العام للصفحة.
   
2. **كائن المتصفح**: 
   - كائن `navigator` يوفر معلومات عن المتصفح نفسه، زي اسم المتصفح وإصدار نظام التشغيل.
   
3. **كائن الموقع**: 
   - كائن `location` يمكّنك من الحصول على عنوان URL الحالي أو تغييره. يمكنك من توجيه المستخدم إلى صفحات أخرى.
   
4. **كائن التاريخ**: 
   - كائن `history` يوفر طرقًا للتنقل عبر تاريخ جلسة المتصفح، زي `history.back()` و`history.forward()`.

### POM (Page Object Model)

الـ **POM** هو نمط تصميم بيستخدم بشكل أساسي في أتمتة الاختبارات. بيساعدك تدير تعقيدات العناصر والإجراءات في الاختبارات الآلية.

#### أهم النقاط عن POM:

1. **فصل الصفحات**: 
   - كل صفحة ويب أو مكون يتم تمثيله كفئة. ده بيخلي الوظائف والخصائص المتعلقة بالصفحة في مكان واحد.
   
2. **إعادة استخدام الكود**: 
   - بما إن عناصر الصفحة والإجراءات معروفة في الفئات، تقدر تعيد استخدام الفئات دي في اختبارات مختلفة.
   
3. **سهولة الصيانة**: 
   - لو واجهة المستخدم اتغيرت، هتحتاج تحدث بس الفئة المعنية بالصفحة.

### الخلاصة

- الـ DOM هو وسيلة للتفاعل مع محتوى الصفحة، والمهاجمين يستغلوا الـ DOM لتنفيذ XSS.
- تأكد دائمًا من حماية مدخلات المستخدم لتفادي الثغرات الأمنية، واستخدم طرق آمنة للتعامل مع المحتوى.
- الـ BOM يساعدك في التفاعل مع المتصفح نفسه وإدارة التنقل وتاريخ الجلسات.
- الـ POM يساعدك تنظم اختباراتك وتجعلها أسهل في الصيانة.

![ipN8SI1](https://github.com/user-attachments/assets/b58a6641-3725-40aa-ac7f-4a0f120c0c05)