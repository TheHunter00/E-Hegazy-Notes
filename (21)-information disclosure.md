
### **Information Disclosure in Web Pentesting**

**Information Disclosure** 

هو عملية كشف معلومات حساسة أو خاصة عن غير قصد من خلال **web applications** أو **servers**. ده ممكن يحصل بسبب أخطاء في **configuration**, وجود **vulnerabilities**, أو رسائل **error** غير آمنة بتكشف تفاصيل عن التطبيق أو السيرفر. لما يحصل **information disclosure**, ممكن المهاجمين يستغلوا المعلومات دي في **attacks** زي **SQL injection**, **XSS**, أو **brute force attacks**.

### **Other Names for Information Disclosure**:
- **Data Leakage**:
  
تسريب بيانات عن طريق **misconfigurations** أو أخطاء غير متعمدة.
- **Information Exposure**:
  
تعرض معلومات حساسة.
- **Debugging Mode Exposure**:

ظهور تفاصيل حساسة من خلال وضع **debugging** في بيئة **production**.

### **Examples of Information Disclosure**:

1. **Error Messages**:


لو النظام بيديك رسائل خطأ بتحتوي على **file paths** أو **stack traces**.  
 
   - مثال:
     - `"Error: Database connection failed. Path: /var/www/html/db_connection.php"`
     في الحالة دي **path** لملف **database connection** مكشوف، وده بيخلي الهجومين يعرفوا مكان الملف ويستغلوا أي ثغرة في النظام.

2. **Logs**: **log files**


ممكن تحتوي على معلومات حساسة زي **passwords** أو **API keys**.  
  
   - مثال:
     - `"User attempted to login with password: 123456"`
     لو الهجومين حصلوا على **log file** ده، ممكن يستخدموا الكلمة دي في هجوم **brute force**.

3. **Headers**:


ممكن تظهر معلومات حساسة في **HTTP headers** زي **server version** أو **technology stack**.  

   - مثال:
     - **X-Powered-By: PHP/7.2.1**
     بيكشف عن نوع **PHP version**، ولو الإصدار ده فيه **vulnerabilities** معروفة، المهاجمين ممكن يستغلوا الثغرة.

4. **Source Code Exposure**:


لو **source code** متاح للجميع من خلال **misconfigurations** أو أخطاء في إعدادات السيرفر.  
  
   - مثال:
     - `"Fatal error: Uncaught Exception: SQL Error: Table 'users' not found in /var/www/html/db_query.php on line 23"`
     الرسالة دي بتكشف عن **file path** وأيضًا مكان الخطأ في الكود اللي ممكن يستخدمه الهجومين في استغلال الثغرات.

5. **Sensitive Data in URLs**:


لو في معلومات حساسة موجودة في **URLs** زي **session IDs**, **tokens**, أو **API keys**.
  
   - مثال:
     - URL زي `http://example.com/dashboard?session=abc123456`
     لو الهجومين شافوا **session ID** دي، ممكن يستخدموها للوصول لحسابات المستخدمين أو استغلال **session hijacking**.

---

### **Impact of Information Disclosure**:
- **Exploitation of Vulnerabilities**:

لما المهاجم يعرف معلومات زي نوع **server** أو **PHP version**, ممكن يستغل **known vulnerabilities**.

   
   - مثال: لو الموقع بيستخدم **PHP/7.2.1** والسيرفر ده فيه ثغرة معروفة في الإصدار ده، الهجومين ممكن يستغلوا الثغرة دي علشان يهاجموا الموقع.

- **Data Breach**:

كشف معلومات زي **passwords**, **API keys**, أو **personal information** ممكن يؤدي إلى تسريب البيانات الحساسة.

   
   - مثال: لو تسربت **API key** في **logs** أو **URLs**, ممكن الهاكرز يستخدموها للوصول إلى أنظمة أو **cloud services**.

- **Targeted Attacks**:

المهاجمين ممكن يوجهوا هجمات دقيقة موجهة لما يعرفوا تفاصيل عن **server** أو **technology stack**.
 
   - مثال: لو المهاجم عرف **server type** و **version**, ممكن يحاول يستغل **RCE (Remote Code Execution)** أو **SQL injection**.

---

### **Mitigation of Information Disclosure**:

1. **Disable Debugging Mode in Production**:

تأكد من تعطيل **debugging mode** في بيئة **production** لأن ده ممكن يفضح تفاصيل زي **file paths** أو **stack traces**.  
   - **Example**:

في بيئة **production**, تأكد إنك مش بتعرض رسائل خطأ مفصلة زي:
     - `"Error: Database connection failed. Path: /var/www/html/db_connection.php"`
     وخلي الرسالة عامة زي: `"Unable to connect to the database. Please try again later."`

2. **Generic Error Handling**:

استخدم **error handling** بشكل يحمي تفاصيل السيرفر أو التطبيق. بدل ما تظهر **internal details** زي **file paths** أو **database information**, خلي رسائل الأخطاء أكثر عمومية.
   - **Example**:
   - بدل ما تقول : `"Error: SQL Query Failed at /var/www/html/db_query.php"`,
   -  خليها : `"Error: Unable to process the request. Please try again later."`

3. **Secure Permissions**:

تأكد من أن **permissions** على الملفات الحساسة مثل **logs**, **config files**, أو **source code** تكون **restricted** فقط للأشخاص المصرح لهم بالوصول إليها.
   - **Example**:

استخدم **file permissions** زي **chmod** على السيرفر لتحكم في مين يقدر يقرأ أو يكتب في **log files**.

4. **Encryption**:

لازم تستخدم **encryption** لكل البيانات الحساسة سواء في النقل أو التخزين.
   - **Example**:

لو بتخزن **passwords**, استخدم **hashing** مع **salt** زي **bcrypt** بدل ما تخزنهم في **plain text**. كمان لازم **API keys** تكون مشفرة ومحمية.

5. **Limit Information in URLs**:

تجنب إرسال معلومات حساسة زي **session IDs** أو **tokens** في **URLs**. لو لازم، خليها مشفرة أو استخدم **secure HTTP**.

6. **Server Configuration and Security Headers**:

تأكد إن **server** مش بيكشف أي معلومات غير ضرورية في **HTTP headers**. استخدم **security headers** زي **X-Content-Type-Options**, **X-XSS-Protection**, و **Strict-Transport-Security (HSTS)** لتقوية أمان الموقع.

---
