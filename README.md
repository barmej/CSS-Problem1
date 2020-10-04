<body dir="rtl">
<h1 dir="rtl">تمرين CSS</h1>
<h2 dir="rtl">ما سنقوم بعمله: </h2>

![exercise screenshot](/images/css-exercise.png)

<h2 dir="rtl">الخطوات: </h2>
<h3 dir="rtl">1- افتح ملف index.html ، لاحظ أن العناصر اللازمة لتطبيق التصميم موجودة </h3>
<p dir="rtl">
ستساعدك التعليقات الموجودة في الملف
</p>

<h3 dir="rtl">2- سنقوم بإضافة containers(حاويات) لتساعدنا في تطبيق التصميم بالشكل المطلوب</h3>
<p dir="rtl">
يجب التمعن في التصميم وتحليله لمعرفة الطريقة الأمثل لتقسيمه، مثلًا سنخرج بالتحليل التالي لمثل هذا التصميم،
</p>

![first analysis screenshot](/images/css-first-analysis.png)

<p dir="rtl">لربما تتساءل لماذا أقوم بإضافة حاويات للعناصر؟</p>
<p dir="rtl">سيساعدنا ذلك عند البدء بإضافة الخصائص للعناصر وترتيب الlayout </p>
<p dir="rtl">مثلًا، لاحظ أن الصورة مع جزئية النص مع أيقونة الواتساب تظهر على استقامة واحدة أي في row واحد، فينبغي أن أجمعها في كونتينر أو حاوية لإعطائها هذه الخاصية،
</p>

<p dir="rtl">
لاحظ أيضًا أن الاسم والمسمى الوظيفي ليست على استقامة واحدة وإنما تظهر كعمود فالعنصر الثاني يظهر فوق العنصر 
</p>
<p dir="rtl">
الأول، فلذلك ينبغي أن أجمع هذه العناصر سوية في كونتينر لوحدها داخل الكونتينر الأب الذي سيأخذ خاصية flex-direction: row;
</p>

![deep analysis screenshot](/images/css-deep-analysis.png)

<p dir="rtl">
لجعل الحاوي يظهر كصف، سنستخدم الخاصية التالية في CSS
<br>

<code>
display: flex;
</code>

<br>
العناصر تظهر كعمود بشكل تلقائي، لكن يمكننا عمل ذلك أيضًا باستخدام خصائص flex

<br>
<code>
display: flex;

flex-direction: column;
</code>

</p>

<p dir="rtl"><b>لاحظ أن التنسيقات التي تلزمنا موجودة مسبقًا في ملف CSS، حاول أخذ نظرة تمعن فيه</b></p>

<br>
<h3 dir="rtl">3- الآن سنحاول تنسيق الجزئية ذات ال3 عناصر، الصورة والنص وأيقونة الواتساب</h3>
<p dir="rtl">
لجعل العناصر متباعدة أفقيَا، أول ما يخطر في بالنا هو استخدام margins،
لكن سنواجه مشاكل عديدة عند اختلاف عرض الشاشة عندها، لذلك يوجد حل أفضل وفعّال أكثر باستخدام خصائص flex أيضًا،
وهي خصائص justify-content, align-items،
<br>
<code>
display: flex;

justify-contetn: space-between;

align-items: center;
</code>
<br>

<p dir="rtl">
أيضًا، لاحظ أن هذه الحاوية تأخذ ثلثي العرض، يمكننا فعل ذلك عن طريق إعطاء خاصية
</p>

<code>
.flex {

flex-grow: 2

}

</code>

<p dir="rtl">
للتعرف أكثر على هذه العناصر اقرأ المقال التالي:
<a href="https://blog.barmej.com/2020/07/24/flex-box/">Flex Box</a>
</p>

<p dir="rtl">
لاحظ أن النص(الاسم والمسمى الوظيفي) يصبح في الوسط ونحن لا نريد ذلك، وإنما نريد أن يبقى بجانب الصورة،
لذلك نقوم بجمع كونتينر النص مع الصورة في كونتينر وإعطاؤه خاصية
</p>

display: flex;

<p dir="rtl">
ولتنصيف العناصر أفقيًا سيلزمنا الخاصية
</p>

align-items: center;

قبل:

![before align items](/images/before-align-items.PNG)

بعد:

![before align items](/images/after-align-items.PNG)

</p>
<h3 dir="rtl">4- جعل التصميم مناسب للشاشات ذات الأحجام الصغيرة</h3>
<p dir="rtl">
ممتاز! أحسنت، يبدو التصميم مثاليًا على الشاشات الكبيرة الآن،
</p>
<p dir="rtl">
لكن ماذا عن الشاشات الصغيرة؟
</p>
<p dir="rtl">
يمكننا أيضًا استخدام خصائص flex box لتحسين ذلك،
مثلًا يمكننا استخدام خاصية
</p>
<code>
flex-wrap: wrap;
</code>
<p dir="rtl">
لجعل العناصر تنتقل للسطر التالي عندما يتعدى المحتوى عرض الشاشة،
وتجنب أن تصبح مضغوطة أو يصبح لدينا scroll لليمين واليسار
</p>
<p dir="rtl">
لكن يتبقى مشكلة وهو أن العناصر تكون ملاصقة لبعضها
عند عرض
600بيكسيل
يحدث ذلك،
</p>
<p dir="rtl">
إذًا ماذا نفعل لحل ذلك؟
</p>
<p dir="rtl">
الحل السحري لدينا هو استخدام
media query
</p>

<p dir="rtl">
سنضيف اسم كلاس جديد لكونتينر الأزرار، وسنقوم بالتالي:
</p>

<code>

@media only screen and (max-width: 600px) {

.buttons-container {

      margin-top: 20px;

      width: 100%;

}

}

</code>

<p dir="rtl">
لاحظ أن هذه الخصائص لا تتطبق إطلاقًا عند شاشة عرضها أكبر من 600 بيكسيل!
</p>

<p dir="rtl">
قبل:
</p>

![before media query](/images/before-media-query.PNG)

<p dir="rtl">
بعد:
</p>

![after media query](/images/after-media-query.PNG)

<p dir="rtl">
لاحظ أن لدينا margin-right غير مرغوب به على الشاشات الصغيرة للجزء الأعلى،
هل يمكنك تحسين ذلك؟
</p>

<p dir="rtl">
للتعرف أكثر على media query
</p>

<p dir="rtl">
اقرأ في هذا الرابط
<a href="https://www.w3schools.com/css/css_rwd_mediaqueries.asp">Media Query and Responsive Design</a>
</p>

<p dir="rtl">
مبارك! :tada:
</p>

<p dir="rtl">
لقد قمت بتطبيق تصميم responsive كامل!
هذه الخطوات ستتكرر بشكل كبير في أية تصميمات أخرى ستقوم بتنفيذها للويب!
</p>

<p dir="rtl">
أتمنى أنك استمتعت بهذا التصميم واستفدت منه!
</p>

<p dir="rtl">
ملاحظة: 
container = كونتينر = حاوية = حاوي = عنصر يجمع مجموعة من العناصر
</p>
</body>
