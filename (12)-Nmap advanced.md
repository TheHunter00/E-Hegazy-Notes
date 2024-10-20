# Subnet Calculator
**Explanation**:


**Subnet Calculator**

هو أداة تُستخدم لتقسيم الشبكات إلى أجزاء أصغر تُسمى **subnets**. يساعد في حساب معلومات مثل **Network Address** و**Broadcast Address** و**Subnet Mask** و**Host Range**. يُستخدم لتحديد عدد الأجهزة التي يمكن أن تتواجد في كل subnet، مما يسهل إدارة الشبكات الكبيرة.

**Types**:


1. **CIDR Notation**:
   
مثل `/24`، يُستخدم لتحديد عدد البتات المستخدمة لعنوان الشبكة.

2. **Classful Subnetting**: 

تقسيم الشبكة بناءً على الفئات (A, B, C).

3. **VLSM (Variable Length Subnet Mask)**: 

يسمح بتقسيم الشبكة إلى أحجام مختلفة حسب الحاجة.

**Example**:  


إذا كنت تريد تقسيم الشبكة `192.168.1.0/24`، يمكن استخدام subnet calculator لتحديد subnet mask وhost range لتوزيعها على أقسام مختلفة.

---

# Scan List of IP Ranges
**Explanation**:  


يعني "Scan List of IP Ranges" استخدام أدوات مثل nmap لفحص مجموعة من عناوين IP. يمكن أن تشمل الفحوصات اكتشاف الأجهزة والخدمات النشطة وتحديد الثغرات الأمنية.

**Example**:  


يمكن فحص نطاق من العناوين مثل `192.168.1.0/24` أو عدة نطاقات باستخدام nmap.

---

#### nmap -il 119.160.254.0/24 vs nmap -il 119.160.254.0/24 -sn vs nmap -il 119.160.254.0/24 --top-ports 100
- **nmap -il 119.160.254.0/24**:

 يقوم بفحص جميع المنافذ على جميع الأجهزة في النطاق المحدد.
  
- **nmap -il 119.160.254.0/24 -sn**:

 يقوم بفحص الـ hosts فقط (ping scan) دون فحص المنافذ. يساعد في معرفة الأجهزة المتصلة فقط.

- **nmap -il 119.160.254.0/24 --top-ports 100**:

يقوم بفحص أهم 100 بورت فقط لكل جهاز في النطاق، مما يسرع عملية الفحص ويقلل من حجم البيانات.

**Example**:  


إذا كنت تريد معرفة الأجهزة النشطة في الشبكة، يمكنك استخدام الأمر الثاني (`-sn`). لكن إذا كنت تبحث عن خدمات محددة، قد تستخدم الأمر الثالث.

---

# exploit-db.com
**Explanation**:  


**Exploit Database** 

هو أرشيف يحتوي على معلومات حول الثغرات الأمنية في البرمجيات، ويقدم مجموعة من **exploits**، **proof of concepts**، و**payloads**. يُستخدمه الباحثون في الأمن لتحديد الثغرات واختبار الأنظمة.

**Example**:  


يمكنك البحث عن ثغرة معينة في برنامج معين باستخدام exploit-db.com للعثور على طرق استغلالها.

---

# Metasploit and Its Commands and Usage
**Explanation**:  


**Metasploit** 

هو إطار عمل مفتوح المصدر يُستخدم لاختبار الاختراق واستغلال الثغرات الأمنية. يوفر مجموعة من الأدوات والمكتبات لجعل عملية اختبار الأمان أكثر سهولة.

**Commands**:


- **msfconsole**:

لفتح واجهة Metasploit.
- **use [module]**:

لتحديد الـ module المستخدم للاستغلال.
- **set [parameter] [value]**:

لتعيين القيم للمعلمات.
- **exploit**:

لتشغيل الاستغلال.

**Example**:  
يمكنك استخدام `msfconsole` للبحث عن exploit ثم استخدامه ضد هدف محدد.

---

# Hydra and Medusa
**Explanation**:  
**Hydra** و**Medusa** 

هما أدوات تُستخدم لتنفيذ هجمات **brute force** لكلمات المرور. تساعدان في اختبار قوة كلمات المرور للخدمات المختلفة مثل SSH وHTTP وFTP.

**Example**:  


إذا كان لديك قائمة كلمات مرور، يمكنك استخدام Hydra لاختبار كلمة مرور لحساب SSH محدد.

---

# Rockyou Password List
**Explanation**:  
**Rockyou Password List** 

هي مجموعة شهيرة من كلمات المرور التي تم تسريبها من اختراق موقع Rockyou. تُستخدم كمرجع في هجمات **brute force** لتجربة كلمات المرور الشائعة.

**Example**:  


تستخدم أدوات مثل Hydra أو Medusa هذه القائمة لاختراق حسابات ضعيفة.

---

# nmap Email List Exploit Disclosure
**Explanation**:  


تشير هذه العبارة إلى استخدام nmap لفحص القوائم البريدية بحثًا عن ثغرات أو معلومات خاصة. قد تتضمن العملية استخدام nmap لاكتشاف الأجهزة أو الخدمات المرتبطة بعناوين البريد الإلكتروني المحددة.

**Example**:  


يمكن لمختبر اختراق استخدام nmap لاكتشاف المعلومات عن السيرفرات التي تدير البريد الإلكتروني لعناوين معينة.

---

# Save nmap Files
**Explanation**:  


يمكن حفظ نتائج nmap في ملفات لاستخدامها لاحقًا أو لتحليلها. توفر nmap خيارات لتصدير النتائج بتنسيقات مختلفة مثل **XML** و**grepable**.

**Example**:  


يمكن استخدام الأمر `nmap -oN results.txt 192.168.1.0/24` لحفظ النتائج في ملف نصي.

---
