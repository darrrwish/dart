
<div class="markdown-card1">
<div class="markdown-header1">
<h1><!-- 🔤 العنوان -->Loops in Dart</h1>
<p><!-- 🧾 الوصف -->الحلقات التكرارية</p>
</div>

<div class="markdown-content1">

<!-- 👨‍💻 الكود -->
```dart
void main() {
for (int i = 0; i < 5; i++) {
print("Hello #$i");
}
```

</div> </div> 



# الحلقات التكرارية (Loops) في دارت  

## اللوبز دي إيه؟ 🤔
اللوبز (الحلقات التكرارية) ببساطة هي طريقة علشان تكرر سطر أو مجموعة أسطر من الكود أكتر من مرة من غير ما تكررها بنفسك.

زيه زي لما تقول لصاحبك:
- "هاتلي الشاي 5 مرات" بدل ما تقوله:
  - "هاتلي شاي"
  - "هاتلي شاي"
  - "هاتلي شاي"
  - "هاتلي شاي"
  - "هاتلي شاي"

## أنواع اللوبز في دارت:
1. **فور لوب `for`** - لما تعرف عدد المرات اللي عايز تكرر فيها الكود
2. **فور إيتش لوب `forEach`** - علشان تمر على كل عنصر في ليست أو ماب
3. **وايل لوب `while`** - لما تكرر الكود طالما الشرط بيتحقق
4. **دو وايل لوب `do while`** - نفس الوايل بس بتشغل الكود قبل ما تفحص الشرط

## مثال من غير لوب 😩
```dart
void main() {
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
    print("أحمد");
}
```
دي طريقة المبتدئين.. لو عايز تكتب اسمك 100 مرة هتتعب!

## مثال بلوب (أسهل بكتير!) 😎
```dart
void main() {
  for (int i = 0; i < 10; i++) {
    print("أحمد");
  }
}
```
باللوب هتعمل نفس الحاجة بس بسطرين بس!

## ليه نستخدم لوبز؟ 🤷♂️
1. **توفير وقتك** - مش هتكتب الكود مليون مرة
2. **تقليل الأخطاء** - لو غلطت هتعدل في مكان واحد بس
3. **الكود هيبقى أنضف** - أسهل للقراءة والفهم

## أمثلة عملية تانية:
### 1. طباعة أرقام من 1 لـ 10
```dart
for (int i = 1; i <= 10; i++) {
  print(i);
}
```

### 2. جمع أرقام في ليست
```dart
List<int> numbers = [10, 20, 30, 40];
int sum = 0;

for (int num in numbers) {
  sum += num;
}

print("المجموع هو: $sum"); // هيطبع 100
```

### 3. طباعة جدول الضرب
```dart
int number = 5;
for (int i = 1; i <= 10; i++) {
  print("$number × $i = ${number * i}");
}
```

#  أمثلة عملية 🚀

## 1️⃣ For Loop (عندما تعرف عدد التكرارات)

```dart
void main() {
  // طباعة أرقام من 1 إلى 5
  for (int i = 1; i <= 5; i++) {
    print('الرقم: $i');
  }
  
  // طباعة الأرقام الزوجية من 0 إلى 10
  for (int j = 0; j <= 10; j += 2) {
    print('الزوجي: $j');
  }
}
```

## 2️⃣ ForEach Loop (للتنقل بين عناصر القوائم)

```dart
void main() {
  List<String> fruits = ['تفاح', 'موز', 'برتقال'];
  
  // الطريقة التقليدية
  fruits.forEach((fruit) {
    print('الفاكهة: $fruit');
  });
  
  // طريقة مختصرة بسهم واحد
  fruits.forEach((fruit) => print('فاكهة: $fruit'));
}
```

## 3️⃣ While Loop (عندما لا تعرف عدد التكرارات)

```dart
void main() {
  int counter = 0;
  
  // طباعة الأرقام أقل من 5
  while (counter < 5) {
    print('العداد: $counter');
    counter++;
  }
  
  // مثال عملي: الانتظار حتى إدخال القيمة الصحيحة
  bool isValid = false;
  while (!isValid) {
    String input = stdin.readLineSync()!;
    isValid = input == 'نعم';
    print('هل أنت متأكد؟ (اكتب "نعم")');
  }
}
```

## 4️⃣ Do-While Loop (تنفيذ الكود مرة واحدة على الأقل)

```dart
void main() {
  int x = 10;
  
  // سيتم التنفيذ مرة واحدة رغم أن الشرط غير محقق
  do {
    print('القيمة: $x');
    x++;
  } while (x < 5);
  
  // مثال عملي: قائمة طعام
  String order;
  do {
    print('الرجاء اختيار طبق (بيتزا/برجر)');
    order = stdin.readLineSync()!;
  } while (order != 'بيتزا' && order != 'برجر');
  print('تم اختيار: $order');
}
```

## 🎯 أمثلة إضافية متقدمة

### 1. Loop مع Maps:
```dart
void main() {
  Map<String, int> ages = {'أحمد': 25, 'محمد': 30, 'خالد': 20};
  
  ages.forEach((name, age) {
    print('$name عمره $age سنة');
  });
}
```

### 2. Loop مع break و continue:
```dart
void main() {
  // break لإيقاف اللوب عند شرط معين
  for (int i = 0; i < 10; i++) {
    if (i == 5) break;
    print(i);
  }
  
  // continue لتخطي تكرار معين
  for (int j = 0; j < 5; j++) {
    if (j == 2) continue;
    print('الرقم $j');
  }
}
```

### 3. Loop مع القوائم المصفوفة:
```dart
void main() {
  List<List<int>> matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
  ];
  
  for (var row in matrix) {
    for (var number in row) {
      print(number);
    }
  }
}
```
---
> في مليون حاجة تستهلك وقتك طولة بالك غير انك تكرر الكود ياهندسة! 😆  
> بعد ما فهمت اللوبز، هتقدر تكتب أكواد أذكى وأقصر! جربها دلوقتي وشوف الفرق.

