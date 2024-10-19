# Apache Service
**Explanation**:  


أباتشي هو **Web Server** شهير جداً، بيساعد في تقديم محتوى الويب على الإنترنت. السيرفر ده بيستقبل **requests** من المتصفحات وبيقدم الصفحات. أباتشي مجاني ومفتوح المصدر، يعني أي حد ممكن يستخدمه ويعدله. بيشتغل على أنظمة تشغيل مختلفة زي **Linux** و**Windows**. وبيقدر يدعم محتوى ديناميكي من خلال استخدام **modules** زي **PHP** و**Perl**. بفضل مرونته وكفاءته، بيستخدمه ملايين المواقع حول العالم.

**Example**:  


تخيل أن فيه مكتبة صغيرة عايزة تعمل **website** لعرض الكتب والعروض. بيستخدموا أباتشي لاستضافة الموقع بتاعهم، عشان العملاء يقدروا يشوفوا الكتالوج والعروض الموجودة عندهم في أي وقت.

---

# Port 80
**Explanation**:  


البورت 80 هو البورت الافتراضي لترافيك **HTTP**. لما تدخل عنوان ويب في المتصفح من غير ما تحدد بورت، المتصفح بيستخدم البورت 80 بشكل تلقائي. البورت ده أساسي لتقديم الصفحات العادية على الويب. أي موقع يعتمد على **HTTP** غالباً هتلاقيه بيستخدم البورت 80. لو كنت عايز تشوف موقع مش مؤمن، هتلاقيه شغال على البورت ده.

**Example**:  


لما واحد يدخل على `http://www.library.com`، المتصفح بتاعه بيبعت طلب للسيرفر على البورت 80 عشان يحمل الصفحة الرئيسية للمكتبة، وبالتالي يقدر يصفح الكتب والعروض.

---

# Management Ports
**Explanation**:  


المانجمنت بورتس هي بورتات معينة بتستخدم للإدارة والتحكم في السيرفرات والأجهزة الشبكية. بتسمح للمديرين بالوصول عن بُعد للتكوين والمراقبة. من أشهر البورتات دي:
- **Port 22**:

لتسجيل الدخول عن بعد باستخدام **SSH**، وهو بروتوكول آمن لتوصيل الجلسات.
- **Port 8080**:

غالباً بيستخدم كواجهة إدارة على أجهزة مختلفة، وخاصة في تطبيقات الويب.

**Example**:  


في شركة، المدير الفني محتاج يغير إعدادات **router**. بيستخدم متصفح الويب ويدخل على **IP** الراوتر مع البورت 8080 عشان يعدل الإعدادات عن بُعد، مما يسهل عليه العملية دون الحاجة للذهاب إلى المكان.

---

# iptables
**Explanation**:  


**iptables**

هي أداة في **Linux** لتكوين الجدار الناري. بتسمح للمديرين بتحديد قواعد لتنظيم مرور البيانات. ممكن نحدد قواعد للسماح أو الحظر أو تعديل **packets** على حسب عناوين **IP** أو بورتات أو بروتوكولات معينة. هي أداة قوية لحماية الأنظمة وتحديد ما يمكن أن يدخل ويخرج من الشبكة.

**Example**:  


شركة بتستخدم iptables عشان تمنع كل الاتصالات اللي جايه من بره، وتسمح بس بالاتصالات على البورتين 80 و443. ده بيساعدهم يحافظوا على أمان الشبكة بتاعتهم ويقللوا من المخاطر المحتملة.

---

# Bootnet
**Explanation**:


**Bootnet**

يعني شبكة من الأجهزة اللي ممكن تتشغل عن بُعد، عادة باستخدام بروتوكول زي **PXE** (Preboot Execution Environment). النظام ده بيساعد في تثبيت أنظمة تشغيل على أجهزة كتير في وقت واحد. التكنولوجيا دي مفيدة بشكل خاص في الشركات الكبيرة أو المؤسسات التعليمية.

**Example**:  


جامعة عايزة تنصب **Operating System** على 30 كمبيوتر في معمل. بدل ما يثبتوه على كل جهاز لوحده، بيستخدموا Bootnet عشان يشغلوا الأنظمة عن بُعد، ويوفروا وقت ومجهود، وكمان يضمنوا إن كل الأجهزة متطابقة.

---

# nmap
**Explanation**: 


**nmap** 

(Network Mapper) أداة مفتوحة المصدر بتستخدم لاستكشاف الشبكات وفحص الأمان. بتساعد في اكتشاف الأجهزة والخدمات على الشبكة من خلال فحص المنافذ. نجم nmap في تحديد الأجهزة المفتوحة والخدمات اللي شغالة عليها، وبتقدر كمان تجمع معلومات تفصيلية عن نظام التشغيل والتطبيقات المستخدمة.

**Example**: 


مدير الشبكة بيستخدم nmap عشان يفحص الشبكة بتاعته ويشوف إيه الأجهزة اللي شغالة وإيه الخدمات المفتوحة على كل جهاز. إذا اكتشف أن فيه خدمة مش مستخدمة، ممكن يقفلها لتحسين الأمان.

---

# nmap www.website.com
**Explanation**:  


الأمر ده بيطلب من nmap إنه يفحص الدومين `www.website.com`. الأداة هتحاول تكتشف الأجهزة الحية وتعرف إيه المنافذ المفتوحة. يمكن استخدام هذا الأمر كخطوة أولى لتحديد المخاطر الأمنية المحتملة.

**Example**:  


استشاري أمان بيستخدم الأمر ده عشان يتأكد إن الموقع بتاع العميل شغال بشكل صحيح، وبيكتشف إن المنافذ 80 و443 مفتوحة، مما يعني إن الموقع متاح للزوار.

---

# nmap -hh
**Explanation**: 


الأمر ده بيظهر قائمة المساعدة لـ nmap، اللي بتوضح كل الخيارات المتاحة والأوامر. ده مفيد للناس اللي لسه مبتدئين في استخدام الأداة، وبيساعدهم في فهم كيفية استخدام الأداة بشكل صحيح.

**Example**:  


واحد مبتدئ في استخدام nmap بيستخدم الأمر ده عشان يتعلم عن الخيارات المختلفة المتاحة له ويستعد للفحص الأول بتاعه. بيقرأ المعلومات ليتأكد إنه مش هيخطئ في استخدام الأوامر.

---

# Bing Scan
**Explanation**:  


**Bing scan**

يعني استخدام محرك البحث Bing للبحث عن معلومات عن مواقع معينة أو ثغرات. من خلال صياغة استفسارات معينة، الباحثين في الأمان ممكن يكتشفوا ملفات مكشوفة أو إعدادات غير صحيحة. Bing يعتبر أداة مفيدة للتعرف على المخاطر المحتملة في المواقع.

**Example**: 


باحث في الأمان بيستخدم Bing للبحث عن `site:example.com filetype:pdf` عشان يلاقي مستندات **PDF** متاحة بشكل عام على موقع العميل. بيكتشف مستند حساس كان المفروض مش يبقى متاح للجمهور، وده ممكن يساعده في تحديد نقاط الضعف.

---

# nmap Arguments and Switches
**Explanation**:  


nmap بيقدم مجموعة من الأوامر اللي بتغير طريقة الفحص. من الأوامر المشهورة:
- **`-sS`**:

 بيعمل فحص **Stealth** (مخفي) للمنافذ، يعني يحاول يتجنب اكتشاف الفحص.
- **`-sU`**:

 بيعمل فحص للمنافذ باستخدام **UDP**، اللي مابيشغلش اتصالات كاملة.
- **`-p`**:

 يحدد المنافذ اللي هيتفحص (مثلاً `-p 80,443` للمنافذ الخاصة بـ HTTP وHTTPS).
- **`-A`**:
  
 يفعل الفحص العدواني لجمع معلومات تفصيلية عن الخدمات، بما في ذلك نظام التشغيل والخدمات المشغلة.

**Example**:  
محلل أمان بيستخدم الأمر `nmap -sS -p 80,443 www.example.com` عشان يفحص المواقع بشكل خفي وبدون ما يتكشف. بعد الفحص، بيكتشف إن فيه خدمة مش متأمنة.

---

# 53 DNS
**Explanation**:  


البورت 53 هو البورت المخصص لخدمات **DNS** (نظام أسماء النطاقات). DNS مهم جداً لأنه بيترجم أسماء النطاقات اللي بنعرفها (زي `www.example.com`) إلى عناوين **IP** اللي تستخدمها الأجهزة للتواصل. بدون DNS، هتكون صعوبة في تذكر عناوين IP.

**Example**:  


لما تدخل على `www.example.com`، جهازك بيستخدم DNS على البورت 53 عشان يلاقي عنوان IP الخاص بالسيرفر ويقدر يتواصل معاه. لو حصل أي خطأ في DNS، ممكن الموقع مش يفتح.

---

# SNMP 161
**Explanation**:  


**SNMP** 

(بروتوكول إدارة الشبكة البسيط) بيشتغل على البورت 161 وبيستخدم لمراقبة وإدارة الأجهزة في الشبكة. بيسمح للمديرين بجمع معلومات عن أداء الأجهزة وصحتها. يعتبر SNMP أداة مهمة في إدارة الشبكات الكبيرة.

**Example**:  


فريق **IT** بيستخدم SNMP لمراقبة الشبكات. بيحددوا تنبيهات في حالة أي جهاز يفصل أو يكون فيه مشاكل في الأداء. مثلاً، لو جهاز راوتر فشل، يتلقوا إشعاراً فورياً.

---

# nmap -sT
**Explanation**:  


الأمر ده بيعمل فحص **TCP Connect**، يعني بيعمل اتصال كامل مع المنافذ عشان يتأكد إذا كانت مفتوحة. الطريقة دي ممكن تتكشف بسهولة، لكن بتعطي معلومات دقيقة عن حالة المنافذ.

**Example**: 


مدير الشبكة بيستخدم `nmap -sT 192.168.1.100` عشان يشوف الخدمات اللي شغالة على السيرفر المحلي. الفحص بيظهر إن البورت 22 (**SSH**) و80 (**HTTP**) مفتوحين، وبالتالي يقدر يتواصل مع السيرفر بشكل مباشر.

---

# nmap -sU
**Explanation**:  


الأمر ده بيعمل فحص لمنافذ **UDP**. بما إن UDP مابيستخدمش الاتصال الكامل، الفحص ده مهم عشان يكتشف الخدمات اللي بتعتمد على UDP، زي خدمات **DNS** و**DHCP**.

**Example**:  


خبير أمان بيستخدم `nmap -sU 192.168.1.100` عشان يكتشف المنافذ المفتوحة على السيرفر. الفحص بيظهر إن البورت 53 (**DNS**) مفتوح، يعني السيرفر جاهز للاستجابة لاستفسارات DNS.

---

# nmap --top-ports 2000
**Explanation**:  


الأمر ده بيفحص أهم 2000 بورت مشهورة على الجهاز المستهدف. ده بيوفر الوقت بدل ما تفحص كل البورتات. استخدام هذه الميزة مفيد في تحديد المنافذ الأكثر استخدامًا بشكل سريع.

**Example**:  


مُختبر اختراق بيستخدم الأمر `nmap --top-ports 2000 192.168.1.50` عشان يحدد الخدمات المهمة اللي ممكن تكون معرضة للخطر بسرعة. النتائج تساعده في تحديد أولويات الفحص.

---

# nmap -sT -sU -p 1-65535 www.website.com
**Explanation**:  


الأمر ده بيفحص كل من **TCP** و**UDP** على جميع المنافذ (من 1 لـ 65535) على الموقع المحدد. الفحص ده شامل بس بياخد وقت طويل جداً، لكنه يعطي معلومات دقيقة عن كل المنافذ.

**Example**:  


فريق أمان في شركة بيستخدم الأمر ده عشان يتأكدوا إن مافيش بورتات غير ضرورية مفتوحة على السيرفر بتاعهم، وبالتالي يحسنوا الأمان ويقللوا المخاطر.

---

# nmap -sT -sU -p 80,443,22 www.website.com
**Explanation**: 


الأمر ده بيفحص بس المنافذ المحددة (80 و443 و22). الطريقة دي أسرع وبتساعد على فحص الخدمات الأساسية بدون الحاجة لفحص كل المنافذ.

**Example**:  


مدير نظام بيستخدم الأمر ده عشان يتأكد إن خدمات الويب وSSH شغالة بشكل صحيح. الفحص يساعده على التعرف على أي مشاكل في الخدمات.

---

# nmap -sT -sU -p 80,443,22 -A www.website.com
**Explanation**:


الأمر ده بيفحص نفس المنافذ بس كمان بيجمع معلومات تفصيلية عن الخدمات، مثل النسخ المستخدمة والإعدادات.

**Example**: 


محلل أمان بيستخدم الأمر ده عشان يعرف أكثر عن الخدمات على سيرفر الويب بتاع الشركة ويكتشف أي ثغرات محتملة. المعلومات اللي يحصل عليها بتساعده في تحسين الأمان.

---

# TCP RAD
**Explanation**:


TCP RAD يمكن يقصد به تقنيات اختبار المنافذ بشكل عشوائي. الطرق دي ممكن تساعد في اكتشاف الثغرات بشكل أقل توقع. الهدف منها هو تجاوز الحماية التي قد تكون موجودة.

**Example**:  


باحث أمان يستخدم الطرق العشوائية لفحص المنافذ بدلاً من الفحص التقليدي، وبالتالي يتجنب الكشف من نظم الحماية ويزيد فرص اكتشاف الثغرات.

---

# Cowboy HTTPD
**Explanation**: 


**Cowboy**

هو **HTTP Server** خفيف مكتوب بلغة **Erlang**. معروف بأداؤه العالي وقدرته على التعامل مع عدد كبير من الاتصالات. بيدعم المعايير الحديثة وبيقدر يقدم محتوى ثابت وديناميكي بكفاءة، مما يجعله مثالي للتطبيقات التي تحتاج استجابة سريعة.

**Example**:  


مطور بيبني تطبيق دردشة في الوقت الحقيقي بلغة **Erlang** واختار Cowboy عشان يدير طلبات **HTTP** بسبب كفاءته وقدرته على التعامل مع عدد كبير من الاتصالات في نفس الوقت.