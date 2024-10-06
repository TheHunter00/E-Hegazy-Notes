## Comparison Table: TCP vs UDP

| Feature                   | TCP (Transmission Control Protocol)             | UDP (User Datagram Protocol)           |
|---------------------------|-------------------------------------------------|----------------------------------------|
| **Connection**            | Connection-oriented                              | Connectionless                         |
| **Reliability**           | Reliable, ensures delivery                       | Unreliable, no guarantee               |
| **Order**                 | Maintains order of packets                       | No order guaranteed                    |
| **Error Checking**        | Yes, provides error recovery                     | Yes, but no recovery                   |
| **Flow Control**          | Yes, manages data transmission rate             | No                                     |
| **Function**              | Ensures reliable data transfer                   | Fast data transfer without reliability  |
| **Usage**                 | Web pages, file transfers, email                | Streaming, gaming, VoIP                |
| **Used By Other Protocols**| HTTP, FTP, SMTP, Telnet                        | DNS, DHCP, SNMP                       |
| **Orientation of Data Packets**| Stream-oriented, maintains data sequence  | Datagram-oriented, no sequence          |
| **Speed of Transfer**     | Slower due to connection establishment           | Faster due to lack of connection setup  |
| **Header Size**           | Larger (20 bytes minimum)                        | Smaller (8 bytes)                      |
| **Applications**          | Suitable for applications needing reliable data  | Suitable for applications needing speed |
| **Three-Way Handshake**   | Yes, used to establish a reliable connection    | No, sends packets directly without handshake |
| **Ordering of Packets**   | Yes, ensures packets arrive in order             | No, packets may arrive out of order    |
| **MTU**                   | Typically supports larger MTU (up to 1500 bytes) | Smaller MTU, often the same but less consistent |

### How TCP Ranges Packets
- **كيفية ترتيب حزم TCP**:
  - عند إرسال البيانات، يقوم بروتوكول TCP بتقسيم البيانات إلى حزم صغيرة (segments). 
  - كل حزمة تحتوي على رقم تسلسل (sequence number) خاص بها. 
  - هذا الرقم يمكن TCP من إعادة ترتيب الحزم عند الاستلام، مما يضمن أن البيانات تصل إلى التطبيق في الترتيب الصحيح.

### How UDP Operates Without Handshaking
- **كيفية عمل UDP**: 
  - عند استخدام UDP، يرسل التطبيق البيانات مباشرة على الشبكة في شكل حزم دون إنشاء اتصال أو استخدام أي نوع من التأكيدات. 
  - يتم إرسال الحزم إلى الوجهة، ولكن لا يتم انتظار استجابة، مما يجعله سريعًا ولكن أقل موثوقية.

## TCP Three-Way Handshake

1. **SYN** (Synchronize):
   - يتم إرسال حزمة SYN من الجهاز العميل إلى الخادم لبدء الاتصال.

2. **SYN-ACK** (Synchronize-Acknowledge):
   - يستجيب الخادم بإرسال حزمة SYN-ACK لتأكيد استلام طلب الاتصال.

3. **ACK** (Acknowledge):
   - يقوم العميل بإرسال حزمة ACK للخادم لتأكيد الاتصال.


## Attack Types

### SYN Flood Attack
- **الوصف**: 
  - هجوم يتسبب في إغراق الخادم بحزم SYN، مما يمنعه من معالجة الطلبات الشرعية. 

- **كيفية العمل**: 
  - المهاجم يرسل العديد من طلبات SYN دون أن يكمل عملية الاتصال، مما يملأ قائمة الانتظار على الخادم.

### SYN Cookies
- **الوصف**: 
  - تقنية تستخدم لحماية الخوادم من هجمات SYN Flood.

- **كيفية العمل**: 
  - بدلاً من تخصيص موارد الاتصال عند تلقي حزمة SYN، يستخدم الخادم قيمة فريدة (cookie) لتأكيد الطلب، مما يقلل من الموارد المستخدمة.

### Example Attack
- **مثال**: 
  - مهاجم يستخدم أدوات مثل LOIC (Low Orbit Ion Cannon) لإرسال حزم SYN بكثرة إلى خادم مستهدف، مما يؤدي إلى إغراقه.

### DNS Amplification Attack
- **الوصف**: 
  - نوع من هجمات DDoS يستخدم خوادم DNS للزيادة من حجم الهجوم.

- **كيفية العمل**: 
  - المهاجم يرسل طلبات DNS مزيفة إلى خوادم DNS باستخدام عنوان IP الضحية. تستجيب خوادم DNS ببيانات كبيرة، مما يؤدي إلى تحميل الضحية.

### Summary of Attacks
- **SYN Flood Attack**: 
  - يهدف إلى إغراق الخادم ومنعه من معالجة الطلبات.

- **SYN Cookies**: 
  - تقنية لحماية الخوادم من هجمات SYN Flood.

- **DNS Amplification Attack**: 
  - يستغل خوادم DNS لزيادة حجم الهجوم على الضحية.

## Summary
- **TCP**: 
  - موثوق، يتطلب اتصال، يحتفظ بالترتيب، مناسب للتطبيقات التي تحتاج إلى دقة في تسليم البيانات.

- **UDP**: 
  - سريع، بدون اتصال، لا يضمن التسليم أو الترتيب، مناسب للتطبيقات حيث تكون السرعة أكثر أهمية من الموثوقية.

