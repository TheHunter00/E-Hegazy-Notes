## 1. API (Application Programming Interface) - واجهة برمجة التطبيقات
الـ **API** هي مجموعة من التعريفات والإجراءات التي تسمح لتطبيقات أو مواقع الإنترنت بالتواصل مع بعضها وتبادل البيانات. كل **API** يمكن أن يوفر وظائف معينة مثل استرجاع البيانات أو إرسال معلومات لتحديث قاعدة بيانات.

**مثال عملي:**
لو كنت تستخدم تطبيق للطقس، التطبيق يرسل طلب إلى **API** للحصول على بيانات الطقس:
```bash
GET https://api.weather.com/v1/forecast?city=cairo
```
هنا، التطبيق يطلب البيانات الخاصة بالطقس في **القاهرة** من السيرفر باستخدام الـ **API**.

---

## 2. SOP (Same-Origin Policy) - سياسة نفس المصدر
الـ **SOP** هي قاعدة أمان في المتصفحات تمنع التطبيقات من إجراء طلبات إلى مصدر آخر (موقع أو سيرفر) يختلف في الـ **origin** (بروتوكول HTTP/HTTPS، النطاق، أو المنفذ).

**مثال عملي:**
إذا كان لديك موقع **siteA.com**، وأنت عايز تمنع موقع آخر **siteB.com** من الوصول لبيانات **siteA.com** عبر **AJAX**، هتمنع هذا باستخدام **SOP**.

---

![image](https://github.com/user-attachments/assets/5d7d2c6d-315e-475f-b9b0-4906a2161508)

![image](https://github.com/user-attachments/assets/79a17ba5-0405-4925-8213-4699cecf87f8)

## 3. CORS (Cross-Origin Resource Sharing) - مشاركة الموارد عبر الأصل
**CORS**

هو آلية بتسمح لمواقع معينة بالوصول إلى بيانات **API** من مواقع أخرى، في حالة التوافق بين **origin** الموقع المرسل و **origin** السيرفر.

**مثال عملي:**
لنفترض أن لديك **API** على **siteA.com** وتريد السماح لموقع **siteB.com** بالوصول للبيانات من خلال **CORS**:
```bash
Access-Control-Allow-Origin: siteB.com
```
هذا يتيح فقط لموقع **siteB.com** الوصول للبيانات الخاصة بـ **siteA.com**.

---
![image](https://github.com/user-attachments/assets/f751a650-1f3e-42ed-97d4-7c738e95a8a7)


## 4. CSP (Content Security Policy) - سياسة أمان المحتوى
**CSP** 

هي سياسة أمان لتحديد المصادر المسموح بتحميل المحتوى منها (مثل السكريبتات والصور)، بهدف الحماية من الهجمات مثل **XSS (Cross-Site Scripting)**.

**مثال عملي:**
لو عندك موقع وتريد تحميل السكريبتات فقط من موقع موثوق:
```bash
Content-Security-Policy: script-src 'self' trusted-source.com;
```
ده يعني السماح بتحميل السكريبتات من الموقع الخاص بك فقط أو من **trusted-source.com**.

---


![image](https://github.com/user-attachments/assets/735f485b-8267-4ddc-90c2-467eb5aee90a)


![image](https://github.com/user-attachments/assets/9368a128-e5d4-45dc-83be-01f7f0e0653b)


## 5. Access-Control-Allow-Origin - تحديد المصدر المسموح بالوصول
**Access-Control-Allow-Origin** 

هو **header** يحدد أي **origin** (موقع) مسموح له بالوصول للبيانات عبر **CORS**.

**مثال عملي:**
إذا كنت تريد السماح فقط لموقع **siteB.com** بالوصول للـ **API**:
```bash
Access-Control-Allow-Origin: siteB.com
```

---

## 6. Access-Control-Allow-Credentials - السماح بإرسال الكوكيز
**Access-Control-Allow-Credentials**

هو **header** يحدد ما إذا كان سيتم السماح بإرسال **cookies** أو **tokens** عبر **CORS**.

**مثال عملي:**
إذا كنت تحتاج إلى إرسال **cookies** مع الطلبات عبر **CORS**:
```bash
Access-Control-Allow-Credentials: true
```

---

## 7. Origin - المصدر
**Origin** هو مزيج من الـ **protocol** 
(مثل `http` أو `https`)، **domain** (مثل `example.com`)، و **port** (مثل `8080`). كل طلب HTTP يحتوي على **origin** ليُحدد إذا كان الطلب من نفس المصدر أم لا.

**مثال عملي:**
**origin** الخاص بـ **https://example.com:8080** هو:
- **protocol**: `https`
- **domain**: `example.com`
- **port**: `8080`

---

## 8. True - قيمة صحيحة
عند استخدام **Access-Control-Allow-Credentials: true**، المتصفح يسمح بإرسال **cookies** أو **tokens** مع الطلبات عبر **CORS** من مواقع مختلفة.

**مثال عملي:**
```bash
Access-Control-Allow-Credentials: true
```
ده يسمح للمتصفح بإرسال **cookies** مع الطلبات.

---

## 9. Exploiting Misconfigured CORS - استغلال تكوين CORS غير الآمن
إذا كانت **CORS** مش متكون بشكل آمن (مثل السماح لـ `*` في **Access-Control-Allow-Origin**)، يمكن للمهاجمين استغلال الثغرة دي ويقوموا بتنفيذ هجمات عبر **CORS** مثل **CSRF (Cross-Site Request Forgery)** أو سرقة بيانات المستخدم.

**مثال عملي على الثغرة:**
لو عندك **API** على **siteA.com**، والسيرفر بيسمح لأي **origin** بالوصول:
```bash
Access-Control-Allow-Origin: *
```
ده يفتح الباب للمهاجمين على مواقع تانية للاستفادة من البيانات بدون إذن.

---

## 10. Content Security Policy (CSP) - سياسة أمان المحتوى
**CSP**

هي أداة وقائية لمنع **XSS** وهجمات التحميل غير الآمن عبر تحديد المصادر المسموح بتحميل المحتوى منها، مثل **images**، **scripts**، **stylesheets**.

**مثال عملي:**
```bash
Content-Security-Policy: default-src 'self'; img-src 'self' trusted-source.com;
```
هنا، يتم تحميل الصور فقط من الموقع نفسه أو من **trusted-source.com**.

---

## 11. Access-Control-Allow-Methods - تحديد الطرق المسموح بها
**Access-Control-Allow-Methods** 

هو **header** يحدد الطرق المسموح بها مثل **GET** و **POST** في الطلبات عبر **CORS**.

**مثال عملي:**
```bash
Access-Control-Allow-Methods: GET, POST
```
هكذا يسمح فقط بطلبات **GET** و **POST** ويمنع باقي الطرق مثل **PUT** و **DELETE**.

---

## 12. Access-Control-Allow-Headers - تحديد الرؤوس المسموح بها
**Access-Control-Allow-Headers**

هو **header** يحدد أي رؤوس HTTP مسموح بها في الطلبات عبر **CORS**.

**مثال عملي:**
```bash
Access-Control-Allow-Headers: Content-Type, Authorization
```
هنا يتم السماح فقط بـ **Content-Type** و **Authorization** في الطلبات عبر **CORS**.

---

## 13. خطورة ثغرة CORS وكيفية إصلاحها

### خطورة ثغرة CORS:
ثغرة **CORS** بتحدث لما يكون الـ **CORS** مش متكون بشكل صحيح. لو كان السيرفر بيسمح لأي **origin** بالوصول للبيانات، أو السماح باستخدام **methods** غير آمنة، أو السماح بإرسال **cookies** و **tokens** بدون تدقيق، ده ممكن يفتح المجال للهجمات.

### أسباب حدوث ثغرة CORS:
- السماح لـ **Access-Control-Allow-Origin: *`** (أي موقع يقدر يدخل).
- السماح بـ **Access-Control-Allow-Methods: *`** (أي طريقة طلب).
- السماح بـ **Access-Control-Allow-Headers: *`** (أي رأس طلب).
- السماح بإرسال **cookies** أو **authentication tokens** بشكل غير محكم.

### الخطورة من ثغرة CORS:
- **التعرض للهجمات عبر المواقع**: يمكن للمهاجمين من مواقع أخرى إرسال طلبات للموقع بدون إذن.
- **سرقة بيانات حساسة**: إذا كان الموقع يسمح لجميع **origins** بالوصول، المهاجمين ممكن يستغلوا البيانات.
- **هجمات CSRF**: إذا كانت **CORS** غير مؤمنة، الهجوم يمكن أن يتسبب في تغيير بيانات الحسابات باستخدام **cookies** أو **tokens**.

### إصلاح ثغرة CORS:
1. **تحديد الـ Origins المسموح بها**: لا تستخدم `*` بل حدد المواقع الموثوقة.
2. **تحديد الـ Methods المسموح بها**: استخدم فقط **GET** و **POST** إذا كان هذا كل ما تحتاجه.
3. **تحديد الـ Headers المسموح بها**: لا تسمح باستخدام **headers** غير ضرورية.
4. **التأكد من الـ Access-Control-Allow-Credentials**: إذا كنت لا تحتاج إرسال **cookies**، تأكد من أن **Access-Control-Allow-Credentials: false**.
5. **اختبار CORS بشكل دوري**: يجب أن تتأكد من التكوين السليم وتحديث السياسات بانتظام.

---
[**SOP vs CORS vs CSP** - Medium](https://medium.com/@sundaeGAN/sop-vs-cors-vs-csp-524e9f758fad)

## الخاتمة:
ثغرة **CORS** هي واحدة من الثغرات الأمنية الشائعة إذا لم تتم إدارة **CORS** بشكل جيد. باتباع أفضل الممارسات مثل تحديد **origins** بشكل دقيق، وتحديد **methods** و **headers** بشكل آمن، مع مراجعة سياسات **CSP**، يمكن تقليل المخاطر بشكل كبير والحفاظ على أمان تطبيقاتك.
