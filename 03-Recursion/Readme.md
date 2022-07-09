
<div dir="rtl">

# بازگشت

## در این فصل

- شما در مورد "بازگشت" یاد می گیرید. "بازگشت" یک تکنیک کدگذاری است که در بسیاری از الگوریتم ها استفاده می شود. این یک بلوک ساختمانی برای درک فصل های بعدی این کتاب است.
- یاد می گیرید که چگونه یک مسئله را به یک حالت پایه و یک مورد بازگشتی تقسیم کنید. استراتژی تقسیم کن (فصل 4) از این مفهوم ساده برای حل مسائل سخت استفاده می کند.

من در مورد این فصل هیجان زده هستم زیرا بازگشت را پوشش می دهد، روشی زیبا برای حل مشکلات. بازگشت یکی از موضوعات مورد علاقه من است، اما تفرقه انگیز است. مردم یا آن را دوست دارند یا از آن متنفرند، یا از آن متنفرند تا اینکه چند سال بعد یاد بگیرند که آن را دوست داشته باشند. من شخصاً در آن اردوگاه سوم بودم. برای اینکه کار را برای شما راحت تر کنم، توصیه هایی دارم:

- این فصل دارای نمونه های کد زیادی است. کد را برای خودتان اجرا کنید تا ببینید چگونه کار می کند.
- در مورد توابع بازگشتی صحبت خواهم کرد. حداقل یک بار، از یک تابع بازگشتی با قلم و کاغذ عبور کنید: چیزی مانند، «ببینیم، من 5 را به فاکتوریل منتقل می کنم، و سپس 5 بار با عبور از 4 به فاکتوریل، که ... است، برمی گردم، و غیره. قدم زدن در یک تابع مانند این به شما یاد می دهد که یک تابع بازگشتی چگونه کار می کند.

این فصل همچنین شامل بسیاری از شبه کدها است. کد کاذب یک توضیح سطح بالا از مشکلی است که در تلاش برای حل آن در کد هستید. مانند کد نوشته شده است، اما قرار است به گفتار انسان نزدیکتر باشد.

## بازگشت

فرض کنید در اتاق زیر شیروانی مادربزرگتان حفاری می کنید و با یک چمدان قفل شده مرموز روبرو می شوید.

![chapter_03_00](../images/03/chapter_03_00.jpg)

مادربزرگ به شما می گوید که احتمالاً کلید چمدان در این جعبه دیگر است.

![chapter_03_01](../images/03/chapter_03_01.jpg)


این جعبه حاوی جعبه های بیشتری است، با جعبه های بیشتری در داخل آن جعبه ها. کلید در جعبه ای در جایی است. الگوریتم شما برای جستجوی کلید چیست؟ قبل از ادامه مطلب به الگوریتمی فکر کنید.
در اینجا یک رویکرد وجود دارد.

![chapter_03_02](../images/03/chapter_03_02.jpg)


1. انبوهی از جعبه ها را بسازید تا از بین آنها نگاه کنید.
2. یک جعبه را بردارید و از طریق آن نگاه کنید.
3. اگر جعبه ای پیدا کردید، آن را به انبوه اضافه کنید تا بعداً آن را بررسی کنید.
4. اگر کلیدی پیدا کردید، کارتان تمام است!
5. تکرار کنید.

در اینجا یک رویکرد جایگزین وجود دارد.

![chapter_03_03](../images/03/chapter_03_03.jpg)

1. از طریق جعبه نگاه کنید.
2. اگر جعبه ای پیدا کردید، به مرحله 1 بروید.
3. اگر کلیدی پیدا کردید، کارتان تمام است!

کدام رویکرد برای شما راحت تر به نظر می رسد؟ روش اول از یک حلقه while استفاده می کند. در حالی که توده خالی نیست، جعبه ای را بردارید و از میان آن نگاه کنید:

```python
def
    look_for_key(main_box):
    pile = main_box.make_a_pile_to_look_through()
    while pile is not empty:
        box = pile.grab_a_box()    
        for item in box:      
            if item.is_a_box():
                pile.append(item)
      
            elif item.is_a_key():
                print "found the key!"

```

راه دوم از بازگشت استفاده می کند. بازگشت جایی است که یک تابع خود را فراخوانی می کند. در اینجا راه دوم در شبه کد است:

![chapter_03_04](../images/03/chapter_03_04.jpg)

هر دو رویکرد یک چیز را انجام می دهند، اما رویکرد دوم برای من واضح تر است. بازگشت زمانی استفاده می شود که راه حل را واضح تر می کند. هیچ مزیت عملکردی برای استفاده از بازگشت وجود ندارد. در واقع، حلقه ها گاهی اوقات برای عملکرد بهتر هستند. من این نقل قول توسط لی کالدول در Stack Overflow را دوست دارم: [«حلقه ها ممکن است به افزایش عملکرد برای برنامه شما دست یابند. بازگشت ممکن است به افزایش عملکرد برای برنامه نویس شما منجر شود. انتخاب کنید کدام یک در موقعیت شما مهمتر است!»](http://stackoverflow.com/a/72694/139117.)

بسیاری از الگوریتم های مهم از بازگشت استفاده می کنند، بنابراین درک مفهوم مهم است.

</div>