
## 1. `sudo`
- بيسمح لك تنفذ الأوامر بصلاحيات المستخدم الجذر. بتستخدمه لما تحتاج تعمل تغييرات على النظام تتطلب أذونات أعلى.
- **المثال**:
  

  ```bash
    sudo apt update
  ```

## 2. `su`
- بتستخدمه عشان تغير المستخدم للجذر أو لمستخدم تاني. محتاج كلمة مرور المستخدم الجديد.
- **المثال**:

  ```bash
  su -
  ```

## 3. `apt`
- أداة لإدارة الحزم في أنظمة Debian. بتستخدمها لتثبيت، تحديث، وإزالة الحزم.
- **المثال**:
  
  ```bash
  apt install package-name
  ```

## 4. `apt-get update`
- بتقوم بتحديث قائمة الحزم المتاحة. مهم عشان تتأكد إنك هتثبت أحدث الإصدارات.
- **المثال**:
  
  ```bash
  sudo apt-get update
  ```

## 5. `apt-get upgrade`
- بتستخدم لتحديث الحزم المثبتة على النظام لأحدث الإصدارات.
- **المثال**:
  
  ```bash
  sudo apt-get upgrade
  ```

## 6. `man`
- بتعرض صفحات المساعدة للأوامر. مفيد عشان نفهم كيفية استخدام الأمر.
- **المثال**:
  
  
  ```bash
  man ls
  ```

## 7. `tcpdump`
- أداة لالتقاط وتحليل حزم البيانات في الشبكة. بتستخدم لاستكشاف الأخطاء.
- **المثال**:
  
  
  ```bash
  sudo tcpdump -i eth0
  ```

## 8. `clear`
- بيعمل مسح للشاشة في الطرفية، مما يساعد في تنظيم العرض.
- **المثال**:
  
  ```bash
  clear
  ```

## 9. `apt-cache search`
- بيساعدك تبحث عن الحزم المتاحة. مفيد لما تحاول تلاقي حزمة معينة.
- **المثال**:
  
  ```bash
  apt-cache search vim
  ```

## 10. `apt-get autoremove`
- بيستخدم لإزالة الحزم غير المستخدمة. بيساعد في تنظيف النظام.
- **المثال**:
  
  ```bash
  sudo apt-get autoremove
  ```

## 11. `locate filename`
- بيستخدم للبحث عن الملفات بسرعة. معتمد على قاعدة بيانات بتتحدث بشكل دوري.
- **المثال**:
  
  ```bash
  locate myfile.txt
  ```

## 12. `find directory filename`
- بيستخدم للبحث عن الملفات داخل دليل معين. ممكن تبحث وفق شروط متعددة.
- **المثال**:
  
  ```bash
  find /home/user -name "*.txt"
  ```

## 13. `curl`
- أداة لنقل البيانات باستخدام بروتوكولات متعددة. بتستخدم لجلب المحتوى من الإنترنت.
- **المثال**:
  
  ```bash
  curl http://example.com
  ```

## 14. `wget`
- أداة لتحميل الملفات من الإنترنت. مثالية لتنزيل الملفات الكبيرة.
- **المثال**:
  
  ```bash
  wget http://example.com/file.zip
  ```

## 15. `touch`
- بيستخدم لإنشاء ملف جديد أو تحديث توقيت آخر تعديل للملف.
- **المثال**:
  
  ```bash
  touch newfile.txt
  ```

## 16. `cat`
- بيستخدم لعرض محتويات ملف. ممكن كمان تدمج الملفات.
- **المثال**:
  
  ```bash
  cat myfile.txt
  ```

## 17. `mkdir`
- بيستخدم لإنشاء مجلد جديد. بتحدد اسم المجلد اللي تريده.
- **المثال**:
  
  ```bash
  mkdir newfolder
  ```

## 18. `rm`
- بيستخدم لحذف الملفات أو المجلدات. لازم تكون حذر لأن الحذف مش ممكن يتراجع عنه.
- **المثال**:
  
  ```bash
  rm myfile.txt
  ```

## 19. `mv`
- بيستخدم لنقل أو إعادة تسمية الملفات. ممكن تستخدمه لنقل ملف لدليل تاني.
- **المثال**:
  
  ```bash
  mv oldname.txt newname.txt
  ```

## 20. `nano`
- محرر نصوص في الطرفية. سهل الاستخدام لتعديل الملفات النصية.
- **المثال**:
  
  ```bash
  nano myfile.txt
  ```

## 21. `>` و `>>`
- بيستخدم لإعادة توجيه المخرجات لملف:
  - `>`: يحل محل محتويات الملف.
  - `>>`: يضيف لمحتويات الملف.
- **المثال**:
  
  - `>`: 
    ```bash
    echo Hello > newfile.txt
    ```
  - `>>`: 
    ```bash
    echo Hello >> newfile.txt
    ```

## 22. `ping`
- بيستخدم لاختبار الاتصال مع عنوان IP أو نطاق. ممكن يساعد في تحديد إذا كانت الشبكة شغالة.
- **المثال**:
  
  ```bash
  ping google.com
  ```

## 23. `ifconfig`
- بيستخدم لعرض معلومات الشبكة. بيعرض تفاصيل زي عنوان IP.
- **المثال**:
  
  ```bash
  ifconfig
  ```

## 24. `ifconfig | grep -i "inet"`
- بيعمل تصفية لمخرجات `ifconfig` عشان يعرض عنوان IP بس. مفيد للحصول على معلومات IP بسرعة.
- **المثال**:
  
  ```bash
  ifconfig | grep -i "inet"
  ```

## 25. `grep`
- بيستخدم للبحث عن نص داخل الملفات. ممكن تستخدمه مع تعبيرات منتظمة لبحث متقدم.
- **المثال**:
  
  ```bash
  grep "search_term" file.txt
  ```

## 26. `cut`
- بيستخدم لقص أجزاء من النصوص. ممكن تستخدمه لفصل النصوص بناءً على محددات.
- **المثال**:
  
  ```bash
  echo "one,two,three" | cut -d "," -f 2
  ```

## 27. `pwd`
- بيستخدم لعرض المسار الحالي للدليل. بيظهر لك فين في هيكل النظام.
- **المثال**:
   
  ```bash
  pwd
  ```

## 28. `&&`
- بيستخدم لتنفيذ الأوامر بالتتابع بس إذا كانت الأوامر السابقة ناجحة.
- **المثال**:
  
  ```bash
  mkdir new_folder && cd new_folder
  ```

## 29. `;`
- بيستخدم لتنفيذ الأوامر بالتتابع بغض النظر عن نتيجة الأوامر السابقة.
- **المثال**:
   
  ```bash
  mkdir new_folder; cd new_folder; touch file.txt
  ```

## 30. `|`
- بيستخدم لتوجيه مخرجات أمر كمدخل لأمر تاني. بيساعد في معالجة البيانات بشكل فعال.
- **المثال**:
  
  ```bash
  ls -l | grep "filename"
  ```

## 31. `head`
- بيستخدم لعرض أول 10 أسطر من ملف. مفيد لرؤية البداية بدون فتح الملف بالكامل.
- **المثال**:
  
  ```bash
  head file.txt
  ```

## 32. `tail`
- بيستخدم لعرض آخر 10 أسطر من ملف. بيستخدم لمراقبة السجلات.
- **المثال**:
  
  ```bash
  tail file.txt
  ```

## 33. `chmod`
- بيستخدم لتغيير أذونات الملفات. ممكن تحدد من يقدر يقرا، يكتب، أو ينفذ.
- **المثال**:
   
  ```bash
  chmod 755 file.txt
  ```

## 34. `stdin`, `stdout`, `stderr`
- تشير لتدفقات البيانات في النظام:
  - **stdin**: المدخلات القياسية.
  - **stdout**: المخرجات القياسية.
  - **stderr**: مخرجات الأخطاء.
- **المثال**:
  
  ```bash
  command_not_found 2> error.log
  ```

## 35. `tail -f /var/log/apache2/access.log`
- بيستخدم لعرض السجلات في الوقت الحقيقي. مفيد لمراقبة الأنشطة الجارية.
- **المثال**:
  
  
  ```bash
  tail -f /var/log/apache2/access.log
  ```

## 36. `tail -f /var/log/apache2/error.log`
- بيستخدم لعرض أخطاء السجلات في الوقت الحقيقي. بيساعد في استكشاف الأخطاء.
- **المثال**:

  ```bash
  tail -f /var/log/apache2/error.log
  ```

## 37. `Regular Expressions`
- نمط للبحث عن نصوص معقدة. بيستخدم في أوامر زي `grep`.
- **المثال**:
   
  ```bash
  grep -E "pattern" file.txt
  ```

## 38. `ls -lah`
- بيعرض محتويات الدليل بتفصيل مع الحجم المقروء. بيساعد في فهم حجم الملفات والمجلدات.
- **المثال**:
   
  ```bash


  ls -lah
  ```

## 39. `sort`
- بيستخدم لترتيب الأسطر في ملف أو مخرجات أمر. ممكن ترتب تصاعدي أو تنازلي.
- **المثال**:
  
  ```bash
  sort file.txt
  ```

## 40. `ps`
- بيستخدم لعرض العمليات الجارية على النظام. مفيد لمراقبة التطبيقات.
- **المثال**:
  
  ```bash
  ps aux
  ```

## 41. `kill`
- بيستخدم لإنهاء عملية معينة. محتاج معرف العملية (PID).
- **المثال**:
   
  ```bash
  kill 1234
  ```

## 42. `kill -9`
- بيستخدم لإنهاء عملية بشكل قاسي. لازم تستخدمه بحذر.
- **المثال**:
  
  ```bash
  kill -9 1234
  ```

## 43. `df -h`
- بيعرض معلومات عن استخدام القرص بشكل سهل القراءة. مفيد عشان تعرف مساحة القرص المتاحة.
- **المثال**:
  
  ```bash
  df -h
  ```

## 44. `top`
- بيعرض قائمة بالعمليات الجارية في الوقت الحقيقي. مفيد لمراقبة الأداء.
- **المثال**:
   
  ```bash
  top
  ```

## 45. `file permissions`
- بتحدد من يقدر يقرا، يكتب، أو ينفذ الملفات. ممكن تحدد الأذونات باستخدام `chmod`.
- **المثال**:
   
  ```bash
  chmod u+x script.sh
  ```

## 46. `d` و `-`
- `d`: folder.
- `-`: file.
  
## 47. `r`, `w`, `x`
- `r`: إذن القراءة.
- `w`: إذن الكتابة.
- `x`: إذن التنفيذ.

## 48. `root`, `users`, `normal users`
- `root`: المستخدم الجذر، عنده كل الأذونات.
- `users`: المستخدمين العاديين، عندهم أذونات محدودة.
  
---

