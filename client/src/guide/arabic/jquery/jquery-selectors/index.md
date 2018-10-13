---
title: jQuery Selectors
localeTitle: مختارات jQuery
---
## مختارات jQuery

يستخدم jQuery محددات نمط CSS لتحديد أجزاء ، أو عناصر ، لصفحة HTML. ثم يتيح لك القيام بشيء ما مع العناصر باستخدام أساليب jQuery أو وظائف.

لاستخدام أحد هذه المحددات ، اكتب علامة الدولار والأقواس بعدها: `$()` . هذا هو اختصار للدالة `jQuery()` . داخل الأقواس ، أضف العنصر الذي تريد تحديده. يمكنك استخدام إما أحادي أو مزدوج. بعد ذلك ، أضف نقطة بعد الأقواس والأسلوب الذي تريد استخدامه.

في jQuery ، تكون أدوات اختبار فئة ومعرفات مثل تلك الموجودة في CSS.

في ما يلي مثال لأسلوب jQuery يحدد جميع عناصر الفقرة ، ويضيف فئة "محددة" إليهم:

 `<p>This is a paragraph selected by a jQuery method.</p> 
 <p>This is also a paragraph selected by a jQuery method.</p> 
 
 $("p").addClass("selected"); 
` 

في jQuery ، تكون محددات الفئة ومعرّف الهوية هي نفسها الموجودة في CSS. إذا كنت تريد تحديد عناصر بفئة معينة ، فاستخدم نقطة ( `.` ) واسم الفئة. إذا كنت تريد تحديد عناصر بمعرف معين ، فاستخدم رمز التجزئة ( `#` ) واسم المعرف. تجدر الإشارة إلى أن HTML ليس حساسًا لحالة الأحرف ، لذلك من الأفضل أن تظل علامات HTML ومتغيرات CSS صغيرة جدًا.

الاختيار حسب الصف:

 `<p class="p-with-class">Paragraph with a class.</p> 
 
 $(".p-with-class").css("color", "blue"); // colors the text blue 
` 

التحديد حسب المعرّف:

 `<li id="li-with-id">List item with an ID.</li> 
 
 $("#li-with-id").replaceWith("<p>Socks</p>"); 
` 

يمكنك أيضًا تحديد عناصر معينة مع فئاتها ومعرفاتها:

### اختيار حسب الفئة

إذا كنت تريد تحديد عناصر بفئة معينة ، فاستخدم نقطة (.) واسم الفئة.

 `
<p class="pWithClass">Paragraph with a class.</p> 
` 

 `$(".pWithClass").css("color", "blue"); // colors the text blue 
` 

يمكنك أيضًا استخدام محدد الفئة مع اسم العلامة لتكون أكثر تحديدًا.

 ``
<ul class="wishList">My Wish List</ul>`<br> 
`` 

 `$("ul.wishList").append("<li>New blender</li>"); 
` 

### اختيار حسب الهوية

إذا كنت تريد تحديد عناصر بقيمة معرف معينة ، فاستخدم رمز التجزئة (#) واسم المعرف.

 `
<li id="liWithID">List item with an ID.</li> 
` 

 `$("#liWithID").replaceWith("<p>Socks</p>"); 
` 

كما هو الحال مع محدد الصف ، يمكن استخدام هذا أيضًا مع اسم العلامة.

 `
<h1 id="headline">News Headline</h1> 
` 

 `$("h1#headline").css("font-size", "2em"); 
` 

### محددات تعمل كمرشحات

هناك أيضًا محددات تعمل كمرشحات - وعادةً ما تبدأ بالنقطتين. على سبيل المثال ، يحدد الخيار `:first` العنصر الذي يكون الطفل الأول من أصله. فيما يلي مثال لقائمة غير مرتبة ببعض عناصر القائمة. يحدد محدد jQuery أسفل القائمة أول عنصر `<li>` في القائمة - عنصر القائمة "One" - ثم يستخدم طريقة `.css` لتحويل النص إلى اللون الأخضر.

 `
   <ul> 
      <li>One</li> 
      <li>Two</li> 
      <li>Three</li> 
   </ul> 
` 

 `$("li:first").css("color", "green"); 
` 

**ملاحظة:** لا تنس أن تطبيق css في JavaScript ليس ممارسة جيدة. يجب عليك دائمًا تقديم أنماطك في ملفات css.

محدد التصفية الآخر ، `:contains(text)` ، يحدد العناصر التي تحتوي على نص معين. ضع النص الذي تريد مطابقته بين الأقواس. هنا مثال مع فقرتين. يأخذ محدد jQuery الكلمة "Moto" ويغير لونه إلى اللون الأصفر.

 `
    <p>Hello</p> 
    <p>World</p> 
` 

 `$("p:contains('World')").css("color", "yellow"); 
` 

وبالمثل ، يحدد `:last` selector `:last` العنصر الأخير للطفل التابع له. يحدد محدد JQuery أدناه العنصر `<li>` الأخير في القائمة - عنصر القائمة "Three" - ثم يستخدم طريقة `.css` لتحويل النص إلى اللون الأصفر.

`$("li:last").css("color", "yellow");`

**ملاحظة:** في jQuery selector ، يكون `World` في علامات تنصيص مفردة لأنه موجود بالفعل داخل زوج من علامات الاقتباس المزدوجة. استخدم دائمًا علامات الاقتباس الأحادية داخل علامات اقتباس مزدوجة لتجنب إنهاء سلسلة بدون قصد.

**اختيار متعددة** في jQuery ، يمكنك استخدام العديد من المحددات لتطبيق نفس التغييرات على أكثر من عنصر واحد ، باستخدام سطر واحد من التعليمات البرمجية. يمكنك القيام بذلك عن طريق فصل معرفات مختلفة بفاصلة. على سبيل المثال ، إذا كنت ترغب في تعيين لون الخلفية لثلاثة عناصر باستخدام ids cat و dog و rat على التوالي إلى اللون الأحمر ، فقم بذلك ببساطة:

 `$("#cat,#dog,#rat").css("background-color","red"); 
` 

هذه ليست سوى عدد قليل من المحددات المتاحة للاستخدام في jQuery. راجع قسم "مزيد من المعلومات" للحصول على ارتباط إلى القائمة الكاملة على موقع jQuery على الويب.

#### معلومات اكثر:

*   [قائمة كاملة من محددات jQuery](http://api.jquery.com/category/selectors/)