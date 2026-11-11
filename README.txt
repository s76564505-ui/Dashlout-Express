دشلوط إكسبريس - نسخة الموقع الأولى

الملفات:
- index.html / style.css / app.js: واجهة العميل والإدارة.
- firestore.rules: قواعد حماية قاعدة البيانات.
- manifest.webmanifest / sw.js / icon.svg: تجهيزات PWA الأساسية.

مهم قبل التشغيل:
1) في Firebase Console > Firestore Database > Rules، استبدل القواعد الحالية بمحتوى firestore.rules ثم اضغط Publish.
2) في Authentication > Users، أنشئ حساب بريد إلكتروني لصاحب الخدمة (يمكن تسجيله من واجهة الموقع أولاً).
3) انسخ UID الخاص بحساب صاحب الخدمة من Authentication > Users.
4) في Firestore > Data، أنشئ collection باسم admins، ثم document ID يساوي UID بالضبط، وأضف field:
   active (boolean) = true
5) انشر ملفات المجلد على استضافة HTTPS تدعم ملفات static. صفحة الإدارة هي نفس عنوان الموقع مع /admin في النهاية.

تنبيه: لا تنشر الموقع للعملاء قبل اختبار حساب عميل وحساب إدارة منفصلين، والتأكد من أن العميل لا يستطيع قراءة طلبات غيره. لا تضف أي بيانات شخصية حقيقية للاختبار.

الموقع يستخدم Firebase Authentication وFirestore، وقد تنطبق حدود الاستخدام المجاني لخطة Spark. Google Fonts اختيارية ويمكن حذف سطر @import لو أردت تقليل الاتصالات الخارجية.
