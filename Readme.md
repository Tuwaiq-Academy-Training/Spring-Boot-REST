
## مفهوم REST

يعتبر REST، أو REpresentational State Transfer،  أسلوبًا معماريًا لتوفير معايير بين أنظمة الكمبيوتر على الويب، مما يسهل على الأنظمة التواصل مع بعضها البعض. تتميز الأنظمة المتوافقة مع REST، والتي غالبًا ما تسمى أنظمة RESTful، بكيفية كونها عديمة الحالة وتفصل اهتمامات العميل (Client) والخادم (Server). سوف ندرس ما تعنيه هذه المصطلحات ولماذا تعتبر خصائص مفيدة للخدمات على الويب.
فصل العميل (Client) والخادم (Server)
في النمط المعماري REST، يمكن تنفيذ العميل (Client) وتنفيذ الخادم (Server) بشكل مستقل دون معرفة كل منهما بالآخر. هذا يعني أنه يمكن تغيير الكود الموجود على جانب العميل (Client) في أي وقت دون التأثير على تشغيل الخادم (Server)، ويمكن تغيير الكود الموجود على جانب الخادم (Server) دون التأثير على عمل العميل (Client).
طالما أن كل جانب يعرف تنسيق الرسائل التي سيتم إرسالها إلى الآخر، فيمكن الاحتفاظ بها معيارية ومنفصلة. بفصل مخاوف واجهة المستخدم عن مخاوف تخزين البيانات (Data)، نقوم بتحسين مرونة الواجهة عبر الأنظمة الأساسية وتحسين قابلية التوسع من خلال تبسيط مكونات الخادم (Server). بالإضافة إلى ذلك، يتيح الفصل لكل مكون القدرة على التطور بشكل مستقل.
باستخدام واجهة REST، يصل العملاء المختلفون إلى نفس نقاط نهاية REST، ويقومون بنفس الإجراءات، ويتلقون نفس الاستجابات.
الأنظمة التي تتبع نموذج REST هي أنظمة عديمة الحالة (Stateless)، مما يعني أن الخادم (Server) لا يحتاج إلى معرفة أي شيء عن حالة العميل (Client) والعكس صحيح. بهذه الطريقة، يمكن لكل من الخادم (Server) والعميل (Client) فهم أي رسالة مستلمة، حتى بدون رؤية الرسائل السابقة. يتم فرض هذا القيد على انعدام الجنسية من خلال استخدام الموارد.
نظرًا لأن أنظمة REST تتفاعل من خلال العمليات القياسية على الموارد، فإنها لا تعتمد على تنفيذ الواجهات.
تساعد هذه القيود تطبيقات RESTful في تحقيق الموثوقية والأداء السريع وقابلية التوسع، كمكونات يمكن إدارتها وتحديثها وإعادة استخدامها دون التأثير على النظام ككل، حتى أثناء تشغيل النظام.
الآن، سوف نستكشف كيف يحدث الاتصال بين العميل (Client) والخادم (Server) عندما نقوم بتنفيذ واجهة RESTful.

التواصل بين العميل (Client) والخادم (Server)
في بنية REST، يرسل العملاء طلبات لاسترداد أو تعديل الموارد، وترسل الخوادم استجابات لهذه الطلبات. دعنا نلقي نظرة على الطرق القياسية لتقديم الطلبات وإرسال الردود.
تقديم الطلبات Making Requests
يتطلب REST أن يقوم العميل (Client) بتقديم طلب إلى الخادم (Server) لاسترداد أو تعديل البيانات (Data) الموجودة على الخادم (Server). يتكون الطلب بشكل عام من:

- فعل HTTP، الذي يحدد نوع العملية المطلوب إجراؤها
- رأس، والذي يسمح للعميل (Client) بتمرير معلومات حول الطلب
- طريق إلى مورد
- نص رسالة اختياري يحتوي على بيانات

HTTP Verbs
هناك 4 أفعال HTTP أساسية نستخدمها في طلبات التفاعل مع الموارد في نظام REST:

- GET - استرداد مورد معين (بواسطة المعرف) أو مجموعة من الموارد
- POST — إنشاء مورد جديد
- PUT - تحديث مورد معين (بواسطة المعرف)
- DELETE — إزالة مورد معين بواسطة المعرف





----------


# مفهوم CRUD

الإنشاء والقراءة والتحديث والحذف (CRUD) هي الوظائف الأساسية الأربع التي يجب أن تكون النماذج قادرة على القيام بها، على الأكثر.
عندما نبني واجهات برمجة التطبيقات، نريد أن توفر نماذجنا أربعة أنواع أساسية من الوظائف. يجب أن يكون النموذج قادرًا على إنشاء الموارد وقراءتها وتحديثها وحذفها. غالبًا ما يشير علماء الكمبيوتر إلى هذه الوظائف بالاختصار CRUD. يجب أن يتمتع النموذج بالقدرة على أداء هذه الوظائف الأربع على الأكثر حتى يكتمل. إذا كان لا يمكن وصف إجراء من خلال إحدى هذه العمليات الأربع، فمن المحتمل أن يكون نموذجًا خاصًا به.
يعد نموذج CRUD شائعًا في إنشاء تطبيقات الويب، لأنه يوفر إطارًا لا يُنسى لتذكير المطورين بكيفية إنشاء نماذج كاملة قابلة للاستخدام. على سبيل المثال، لنتخيل نظامًا لتتبع كتب المكتبة. في قاعدة بيانات المكتبة الافتراضية هذه، يمكننا أن نتخيل أنه سيكون هناك مورد كتب، والذي سيخزن أشياء من الكتب. لنفترض أن كائن الكتاب يشبه هذا:

     “book”: {
         "id": <Integer>,
         “title”: <String>,
         “author”: <String>,
         “isbn”: <Integer>
      }

لجعل نظام المكتبة هذا قابلاً للاستخدام، نود التأكد من وجود آليات واضحة لإكمال عمليات CRUD:
**عملية الإنشاء** **Create**
سيتكون هذا من وظيفة نسميها عند إضافة كتاب مكتبة جديد إلى الفهرس. البرنامج الذي يستدعي الوظيفة سيوفر قيم “title” و “author” و "isbn". بعد استدعاء هذه الوظيفة، يجب أن يكون هناك إدخال جديد في مورد الكتب المقابل لهذا الكتاب الجديد. بالإضافة إلى ذلك، يتم تعيين معرّف فريد للإدخال الجديد، والذي يمكن استخدامه للوصول إلى هذا المورد لاحقًا.
**عملية القراءة** **Read**
سيتكون هذا من وظيفة سيتم استدعاؤها لرؤية جميع الكتب الموجودة حاليًا في الفهرس. لن يؤدي استدعاء الوظيفة هذا إلى تغيير الكتب الموجودة في الكتالوج - بل سيؤدي ببساطة إلى استرداد المورد وعرض النتائج. سيكون لدينا أيضًا وظيفة لاسترداد كتاب واحد، يمكننا توفير العنوان أو المؤلف أو رقم ISBN له. مرة أخرى، لن يتم تعديل هذا الكتاب، بل سيتم استرجاعه فقط.
**عملية التعديل أو التحديث** **Update**
يجب أن تكون هناك وظيفة لاستدعاء عندما يجب تغيير المعلومات حول الكتاب. سيقوم البرنامج الذي يستدعي الوظيفة بتزويد القيم الجديدة لكل من “title” و “author” و "isbn". بعد استدعاء الوظيفة، سيحتوي الإدخال المقابل في مورد الكتب على الحقول الجديدة المتوفرة.
**عملية الحذف** **Delete**
يجب أن تكون هناك وظيفة لاستدعاء لإزالة كتاب مكتبة من الفهرس. سيوفر البرنامج الذي يستدعي الوظيفة قيمة واحدة أو أكثر (“title” و / أو “author” و / أو "isbn") لتحديد الكتاب، ثم تتم إزالة هذا الكتاب من مصدر الكتب. بعد استدعاء هذه الوظيفة، يجب أن يحتوي مورد الكتب على جميع الكتب التي كان لديه من قبل، باستثناء الكتاب الذي تم حذفه للتو.



----------


# بناء Rest Api
## المتطلبات   
- برنامج Postman لاختبار الروابط.
## مقدمة 

في هذا الفصل سنقوم ببناء مشروع يحتوي على الأربع عناصر الأساسية في أي مشروع Api وهي:

- ا get وهو النوع الخاص باستقبال البيانات.
- ا post وهو النوع الخاص بإضافة بيانات جديدة.
- ا put وهو النوع الخاص بتعديل البيانات.
- ا delete وهو النوع الخاص بحذف البيانات.



## بناء مشروع Spirng Boot عن طريق Spring Boot Initializr

من أجل القيام بأول مشروع Spring Boot سوف نتجه إلى موقع [Spring Boot Initializr](https://start.spring.io) والذي سوف يمكننا من إنشاء مشروع Spring Boot بشكل بسيط وسريع.
سنقوم ببناء مشروع متجر قهوة بحيث يمكننا عرض وإضافة وتعديل وحذف منتجات القهوة التي لدينا.

## 
![](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1637589747087_image.png)



## إنشاء المجلد الخاص بالقهوة

في البداية سنقوم بإنشاء المجلد الخاص بالقهوة والذي يحتوي على جميع الملفات الخاصة بالقهوة، ولكن قبل البدء بكتابته سنتعرف على أفضل الممارسات في تنظيم المشروع.

    com
     +- example
         +- myapplication
             +- MyApplication.java
             |
             +- class-name
             |   +- ClassName.java
             |   +- ClassNameController.java
             |

 الآن سنقوم بإنشاء مجلد جديد باسم coffee وسيكون بداخله كل الملفات المتعلقة بالقهوة.
 

## إنشاء ملف  `offee.java` الخاص بصفات القهوة 

بداخل هذا المجلد سنقوم بإنشاء ملف `java` جديد وسيكون باسم `Coffee.java` وبداخله الصفات المتعلقة بالقهوة مثل الاسم و السعر... إلى آخره.  


    package com.coffeeshop.coffee;
    public class Coffee {
        private final long id;
        private String name;
        private double price;
        public Coffee(long id, String name, double price) {
            this.id = id;
            this.name = name;
            this.price = price;
        }
        public long getId() {
            return id;
        }
        public String getName() {
            return name;
        }
        public void setName(String name) {
            this.name = name;
        }
        public double getPrice() {
            return price;
        }
        public void setPrice(double price) {
            this.price = price;
        }
        @Override
        public String toString() {
            return "Coffee [id=" + id + ", name=" + name + ", price=" + price + "]";
        }
    }

  
 يحتوي `coffee.java` على ثلاث صفات:

-  صفة id: وهي ترمز إلى رقم خاص بكل قهوة ونوعها long.
- صفة name: وهي صفة خاصة باسم القهوة ونوعها String.
- صفة price: وهي صفة خاصة بسعر القهوة ونوعها double.

وتم إضافة setter و getter للصفات وكذلك تم إضافة toString.



## إنشاء ملف `CoffeeController.java` 

ملف `CoffeeController.java` هو الملف المسؤول عن إدارة طلبات Rest Api Class الخاصة، وسوف يحتوي على الأربع `requests` الأساسية:

- ا get وهو النوع الخاص باستقبال البيانات.
- ا post وهو النوع الخاص بإضافة بيانات جديدة.
- ا put وهو النوع الخاص بتعديل البيانات.
- ا delete وهو النوع الخاص بحذف البيانات.

في البداية سوف ننشئ `CoffeeController.java`، ومن المهم استخدام `@RestController` عند بدايته وذلك لتحديد أنه `C``lass` خاص بمعالجة `Rest Requests`.


    package com.coffeeshop.coffee;
    
    import org.springframework.web.bind.annotation.RestController;
    @RestController
    public class CoffeeController {
    
    }

الآن نضيف بيانات `coffee` وسوف تكون من نوع `List<Coffee>` وباسم `coffees` وسوف نسند له قيمة `new ArrayList<>()`. كما سنقوم بإضافة `constructor` ونضيف بداخله بيانات `coffees`.


        List<Coffee> coffees = new ArrayList<>();
        CoffeeController() {
            coffees.addAll(
                    List.of(
                        new Coffee(1, "Black Coffee", 12),
                        new Coffee(2, "Latte", 21),
                        new Coffee(3, "Cappuccino", 7)
                    ));
        }


##  طلبات Get

 سنقوم الآن بإنشاء أول Api لنا وسيكون من نوع get، وسيكون خاص باستعراض كل أنواع القهوة التي نملكها.


    @GetMapping
    List<Coffee> getCoffees() {
        return coffees;
    }

عند الدخول إلى هذا الرابط http://localhost:8080 نلاحظ أن النتيجة التي أمامنا هي المدخلات التي وضعناها بداخل `Constructor` الخاص بـ `CoffeeController()`.


    [
        {
            "id": 1,
            "name": "Black Coffee",
            "price": 12.0
        },
        {
            "id": 2,
            "name": "Latte",
            "price": 21.0
        },
        {
            "id": 3,
            "name": "Cappuccino",
            "price": 7.0
        }
    ]

 
 والآن سنقوم بتعديل مسار الرابط ونجعله يكون بعد `http://localhost:8080/coffee` وذلك لتمييز أن هذا هو المسار الخاص بجلب المعلومات الخاصة بالقهوة. ويمكننا ذلك عن طريق إضافة `@RequestMapping("/coffee")` فوق `C``lass` الخاص بـ `CoffeeController`.

    
    @RestController()
    @RequestMapping("/coffee")
    public class CoffeeController {
        List<Coffee> coffees;
        CoffeeController() {
            coffees = List.of(
            new Coffee(1, "Black Coffee", 12), 
            new Coffee(2, "Latte", 21),
            new Coffee(3, "Cappuccino", 7));
        }
        @GetMapping
        List<Coffee> getCoffees() {
            return coffees;
        }
    }

الآن عند الدخول إلى هذا الرابط  `http://localhost:8080/coffee` سوف نحصل على نفس النتيجة السابقة.


    [
        {
            "id": 1,
            "name": "Black Coffee",
            "price": 12.0
        },
        {
            "id": 2,
            "name": "Latte",
            "price": 21.0
        },
        {
            "id": 3,
            "name": "Cappuccino",
            "price": 7.0
        }
    ]

 
 الآن سنقوم بإضافة getApi آخر وسيكون وظيفته إحضار البيانات الخاصة بالقهوة عند البحث عن `id` الخاص فيها.
 
 في البداية سنقوم بكتابة `F``unction` الخاصة بهذه الوظيفة:


        @GetMapping("/{id}")
        Optional<Coffee> getCoffeeById(@PathVariable Long id) {
            for (Coffee coffee : coffees) {
                if (id.equals(coffee.getId())) {
                    return Optional.of(coffee);
                }
            }
            return Optional.empty();
        }


- استخدمنا `@GetMapping("/{id}")` من أجل تحديد المسار أو الرابط الخاص بهذه الوظيفة وقمنا بإضافة `/{id}`  وذلك لإرسال هذه القيمة إلى `P``arameter` الخاص بهذه الدالة، على سبيل المثال: `http://localhost:8080/coffee/1` ويمثل رقم ١ `id` الخاص بالقهوة.
- قمنا باستخدام `@PathVariable` وذلك لجعل `id` يأخذ قيمته من الرابط.
- قمنا بوضع نوع الدالة Oprional وذلك لجعل هذه الدالة تعمل عند البحث عن `id` غير موجود. 
- بداخل هذه الدالة نقوم بالبحث عن العنصر الذي يحتوي على `id` الموجود في الرابط باستخدام `for loop` ثم نقوم بإرجاع هذا العنصر، وإذا كان لا يوجد عنصر نعيد له عبارة فارغة.
    مثال: 
    عند كتابة هذا الرابط `http://localhost:8080/coffee/1` سنحصل على نتيجة القهوة التي تحتوي على `id` قيمته ١.
    {
        "id": 1,
        "name": "Black Coffee",
        "price": 12.0
    }

عند كتابة هذا الرابط `http://localhost:8080/coffee/9` سوف نحصل على نتيجة القهوة التي تحتوي على `id` قيمته ٩، ولكن بما أننا لا نملك قهوة تحتوي على رقم `id` ٩ سنحصل على النتيجة التالية؛ وذلك بسبب استخدامنا قيمة من نوع `Optional<Coffee>`:

    null

ولتحسين Api سنقوم باستخدام `ResponseEntity` وذلك لكي نعيد إشارة Httpststus. يمكنك التعرف عليها بشكل أكبر من [هنا](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).
سيصبح الكود بهذا الشكل:

        @GetMapping("/{id}")
        ResponseEntity<Optional<Coffee>> getCoffeeById(@PathVariable Long id) {
            for (Coffee coffee : coffees) {
                if (id.equals(coffee.getId())) {
                    return new ResponseEntity<>(Optional.of(coffee), HttpStatus.OK);
                }
            }
            return new ResponseEntity<>(Optional.empty(), HttpStatus.NOT_FOUND);
        }

 الآن عند القيام بنفس العملية يمكننا معرفة نوع الرد بحيث أنه إذا لم يكن هناك `id` موجود سوف نحصل على `HttpStatus` بقيمة `404 Not Found`، ويمكننا معرفة ذلك عن طريق استخدام برنامح `postman`.
 

![عند البحث عن قيمة غير موجودة في postman](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1637679308963_image.png)


  الآن عند القيام بنفس العملية ولكن بالبحث عن قيمة موجودة فسوف نلاحظ أن `HttpStatus` قيمته `OK 200`.

![عند البحث عن قيمة  موجودة في postman](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1637679707027_image.png)

## طلبات Post

تختلف طلبات Post عن Get بسبب أن Post تحتوي على Body ويمكننا من وضع بيانات فيها وتقوم Post بإضافة وإرسال البيانات.
الآن سنقوم بإضافة postApi آخر وسيكون وظيفته إضافة قهوة إلى مجموعة القهوة التي نملكها.
 في البداية سوف نقوم بكتابة `F``unction` الخاصة بهذه الوظيفة:
 

    @PostMapping()
    public ResponseEntity<Coffee> postNewCoffee(@RequestBody Coffee c) {
        coffees.add(c);
        return new ResponseEntity<>(c, HttpStatus.CREATED);
    }

استخدمنا `@PostMapping()` من أجل تحديد أن هذا الطلب هو Post أو الرابط الخاص بهذه الوظيفة، كما قمنا بإضافة واستخدام  `@RequestBody` وذلك لإضافة بيانات القهوة الجديدة.
وبداخل هذه الدالة قمنا بإضافة القهوة `c` الموجودة بداخل `@RequestBody`.
مثال:

![](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1638266158487_image.png)



## طلبات Post

تختلف طلبات Post عن Get بسبب أن Post تحتوي على Body ويمكّننا من وضع بيانات فيها وتقوم Post بإضافة وإرسال البيانات.
الآن سنقوم بإضافة postApi آخر وسيكون وظيفته إضافة قهوة إلى مجموعة القهوة التي نملكها.
 في البداية سنقوم بكتابة `F``unction` الخاصة بهذه الوظيفة:

        @PostMapping()
        public ResponseEntity<Coffee> postNewCoffee(@RequestBody Coffee c) {
            coffees.add(c);
            return new ResponseEntity<>(c, HttpStatus.CREATED);
        }
## 
- استخدمنا `@PostMapping()` من أجل تحديد أن هذا الطلب هو Post أو الرابط الخاص بهذه الوظيفة، كما قمنا بإضافة واستخدام  `@RequestBody`  وذلك لإضافة بيانات القهوة الجديدة.
- بداخل هذه الدالة قمنا بإضافة القهوة `c` الموجودة بداخل `@RequestBody`.
    مثال: 
![](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1638266158487_image.png)

## 
## طلبات Put

تقوم طلبات Put بتعديل البيانات الموجودة. 
سنقوم الآن بإضافة putApi وسيكون وظيفته التعديل على بيانات القهوة الموجودة. 
 في البداية سنقوم بكتابة `F``unction` الخاصة بهذه الوظيفة:

        @PutMapping("/{id}")
        ResponseEntity<Optional<Coffee>> putCoffee(
        @PathVariable Long id,
        @RequestBody Coffee c) {
            for (Coffee coffee : coffees) {
                if (id.equals(coffee.getId())) {
                    int coffeeIndex = coffees.indexOf(coffee);
                    coffees.set(coffeeIndex, c);
                    return new ResponseEntity<>(Optional.of(c), HttpStatus.OK);
                }
            }
            return new ResponseEntity<>(Optional.empty(), HttpStatus.NOT_FOUND);
        }
##  
- استخدمنا `@PutMapping("/{id}")` من أجل تحديد المسار أو الرابط الخاص بهذه الوظيفة وقمنا بإضافة `/{id}`  وذلك لإرسال هذه القيمة إلى `P``arameter` الخاص بهذه الدالة، مثال: `http://localhost:8080/coffee/1` ويمثل رقم ١ `id` الخاص بالقهوة .
- قمنا باستخدام `@PathVariable` وذلك لجعل `id` يأخذ قيمته من الرابط.
- قمنا باستخدام  `@RequestBody`  وذلك لإضافة بيانات القهوة الجديدة.
- قمنا بوضع نوع الدالة Optional وذلك لجعل هذه الدالة تعمل عند البحث عن `id` غير موجود. 
- بداخل هذه الدالة نقوم بالبحث عن العنصر الذي يحتوي على `id` نفس الموجود في الرابط باستخدام `for loop`، ثم نقوم بتعديل العنصر الذي يحتوي على هذا العنصر، وإذا كان لا يوجد عنصر نعيد له عبارة فارغة.
    مثال: 
![](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1638268139315_Screen+Shot+2021-11-30+at+1.28.03+PM.png)

## طلبات  Delete

تقوم طلبات Put بحذف البيانات.
سنقوم الآن بإضافة deleteApi وسيكون وظيفته حذف قهوة موجودة بين القهوة التي لدينا.
 في البداية سنقوم بكتابة `F``unction` الخاصة بهذه الوظيفة:


        @DeleteMapping("/{id}")
        ResponseEntity<Optional<String>> deleteCoffeeById(@PathVariable Long id) {
            for (Coffee coffee : coffees) {
                if (id.equals(coffee.getId())) {
                    int coffeeIndex = coffees.indexOf(coffee);
                    coffees.remove(coffeeIndex);
                    return new ResponseEntity<>(Optional.of("Deleted"), HttpStatus.ACCEPTED);
                }
            }
            return new ResponseEntity<>(Optional.of("Not Found"), HttpStatus.NOT_FOUND);
        }


- استخدمنا `@DeleteMapping("/{id}")` من أجل تحديد المسار أو الرابط الخاص بهذه الوظيفة وقمنا بإضافة  `/{id}` وذلك لإرسال هذه القيمة إلى `P``arameter` الخاص بهذه الدالة مثال: `http://localhost:8080/coffee/1` ويمثل رقم ١ `id` الخاص بالقهوة .
- قمنا باستخدام `@PathVariable` وذلك لجعل `id` يأخذ قيمته من الرابط.
- بداخل هذه الدالة نقوم بالبحث عن العنصر الذي يحتوي على `id` نفس الموجود في الرابط باستخدام `for loop`، ثم نقوم بحذف هذا العنصر ونعيد عبارة Deleted، وإذا كان لا يوجد عنصر نعيد له عبارة Not Found.

مثال:

![](https://paper-attachments.dropbox.com/s_4E5081556D8D7995404A88F735C9A07394B3AAF32E4850A4FE39753C3240EBAD_1638268880953_Screen+Shot+2021-11-30+at+1.40.47+PM.png)


-----------


# ماهو Lombok :

مشروع Lombok هي أداة مكتبة جافا تُستخدم لتقليل / إزالة الشفرة المعيارية وحفظ الوقت  للمطورين أثناء التطوير عن طريق استخدام بعض التعليقات التوضيحية فقط. بالإضافة إلى ذلك ، فإنه يزيد أيضًا من قابلية قراءة الكود المصدري ويوفر مساحة.

تعليقات Lombok التوضيحية: توفر Lombok مجموعة من التعليقات التوضيحية لجعل حياتنا البرمجية أسهل. دعونا نلقي نظرة على التعليقات التوضيحية القليلة الأكثر استخدامًا في Lombok

**@Getter and @Setter:**
توفر هذه التعليقات التوضيحية طريقتي getter و setter للحقل. يمكن استخدام هذه التعليقات التوضيحية على كل من المستويات والحقل والفصل. ينشئ التعليق التوضيحي Getter طريقة getter بنوع وصول كعام والذي يقوم ببساطة بإرجاع الحقل وباسم ()getName  إذا كان اسم الحقل هو "Name". ينشئ التعليق التوضيحي Setter طريقة تعيين بنوع الوصول كعموم والذي يعيد الفراغ ويأخذ معلمة واحدة لتعيين القيمة للحقل. سيكون للمُعيِّن الافتراضي اسم ()setName  إذا كان اسم الحقل هو "Name".


**@NoArgsConstructor:** 
يتم استخدام هذا التعليق التوضيحي لإنشاء مُنشئ بدون وسيطات. له جسم فارغ ولا يفعل شيئًا. يتم استخدامه بشكل عام مع بعض المُنشئ ذي المعلمات الأخرى قيد الاستخدام. يكون مطلوبًا عندما تريد إنشاء كائن للفئة من خلال عدم تمرير أي وسائط في المنشئ.

**@AllArgsConstructor:** 
يتم استخدام هذا التعليق التوضيحي لإنشاء مُنشئ ذي معلمات يقبل معلمة واحدة لكل حقل ويقوم بتهيئتها باستخدامه. إنه مطلوب عندما تريد إنشاء كائن للفئة عن طريق تمرير القيم الأولية للحقول في المنشئ.

**@ToString:** 
يتم استخدام هذا التعليق التوضيحي لتجاوز طريقة ()toString وإنشاء تطبيق افتراضي لها. يطبع التطبيق الافتراضي اسم الفئة والحقول بالترتيب ، مفصولة بفاصلات. يمكنك أيضًا تخطي بعض الحقول التي لا تريد طباعتها عن طريق التعليق عليها باستخدام  ToString.Exclude@

 **@EqualsAndHashCode:** 
 يتم استخدام هذا التعليق التوضيحي لتجاوز طريقتي ()equals  و ()hashCode ويوفر تطبيقًا افتراضيًا لـ thu. يستخدم التطبيق الافتراضي جميع الحقول غير الثابتة ، ويمكننا تعديله واستبعاد بعض الحقول باستخدام التعليق التوضيحي EqualsAndHashCode.Exclude@
 
 **@Data:** 
 هذا التعليق التوضيحي عبارة عن تعليق توضيحي مختصر ومجموعات التعليقات التوضيحية ToString وGetter وSetter وEqualsAndHashCode وRequiredArgsConstructor في تعليق توضيحي واحد. يوفر هذا التعليق التوضيحي جميع الكود المعياري المستخدم عادةً في فئات نموذج جافا مثل المحصل لجميع الحقول ، واضبط جميع الحقول غير النهائية ، وتنفيذ افتراضي لـ ()toString() ، equals و ()hashCode باستخدام جميع الحقول من الفصل والمنشئ الذي يهيئ جميع مجالات الفصل
