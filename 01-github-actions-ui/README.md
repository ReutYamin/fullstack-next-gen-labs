# GitHub Actions Lab 01: Core Infrastructure & Pipeline UI

במעבדה זו נכיר לראשונה את **GitHub Actions** ונבנה את ה־Workflow הראשון שלנו. במהלך העבודה נלמד כיצד Pipeline מופעל, כיצד לקרוא את ה־Logs, כיצד לאתר תקלות, ומדוע כל ריצה מתבצעת על שרת זמני (Runner).

---

## מטרות המעבדה

בסיום המעבדה תדעו:

* ליצור Workflow ראשון ב־GitHub Actions.
* להפעיל Pipeline באמצעות `git push`.
* לנווט בממשק GitHub Actions.
* לקרוא ולהבין את ה־Logs של ה־Workflow.
* להבין כיצד עובד GitHub Runner.
* להשתמש בכלי AI ליצירת Workflow בסיסי.

---

## רקע

מערכת GitHub Actions היא מערכת CI/CD המובנית בתוך GitHub ומאפשרת להריץ תהליכים באופן אוטומטי בעקבות אירועים שונים, כגון `Push`, `Pull Request` או יצירת `Release`.

כל Workflow רץ על **GitHub Runner** – שרת זמני שנוצר מחדש עבור כל הרצה. המשמעות היא שבכל פעם שה־Workflow מתחיל, סביבת העבודה ריקה לחלוטין, ולכן יש להוריד את קוד הפרויקט מחדש לפני שמבצעים פעולות עליו.

---

## משימה 1 – יצירת Workflow ראשון

### שלב 1: כניסה ל־Repository

היכנסו ל־Repository שלכם ב־GitHub.

### שלב 2: פתיחת לשונית Actions

פתחו את לשונית **Actions**.

### שלב 3: בחירת תבנית

בחרו אחת מהתבניות המוצעות, לדוגמה: **Simple Workflow** או **Node.js**.

### שלב 4: עריכת ה־Workflow

מחקו את פקודות ברירת המחדל שבחלק `steps`.

### שלב 5: הוספת פקודות

הוסיפו שתי פקודות `run`:

* פקודת `echo` שמדפיסה הודעה לבחירתכם.
* פקודה המציגה את גרסת שפת הפיתוח של הפרויקט, לדוגמה: `node --version` או `python --version`.

### שלב 6: ביצוע Commit

בצעו Commit ישירות לענף `main`.

### שלב 7: צפייה בריצה

חזרו ללשונית **Actions** ועקבו אחר הריצה עד לסיומה.

### שלב 8: בדיקת Logs

פתחו את ה־Logs ובדקו שכל השלבים הושלמו בהצלחה.

---

## משימה 2 – יצירת תקלה וניתוח ה־Logs

### שלב 1: יצירת תקלה מכוונת

צרו שגיאת Runtime מכוונת בפרויקט, לדוגמה פקודה שאינה קיימת או שגיאת Syntax.

### שלב 2: ביצוע Commit ו־Push

בצעו את הפקודות הבאות:

```bash
git add .
git commit -m "Add intentional runtime error"
git push
```

### שלב 3: מעבר ל־Actions

עברו ללשונית **Actions**.

### שלב 4: איתור הריצה שנכשלה

אתרו את ה־Workflow שנכשל.

### שלב 5: ניתוח התקלה

פתחו את הריצה ובדקו:

* איזה Job נכשל.
* איזה Step נכשל.
* מהי הודעת השגיאה.

### שלב 6: תיקון התקלה

תקנו את הבעיה בקוד או בקובץ ה־Workflow.

### שלב 7: בדיקה חוזרת

בצעו Push נוסף וודאו שה־Pipeline מסתיים בהצלחה.

---

## משימה 3 – יצירת Workflow באמצעות AI

במשימה זו תשתמשו בכלי AI כדי ליצור Workflow שמריץ את תהליך ה־Lint של הפרויקט.

### שלב 1: פתיחת כלי AI

פתחו את ChatGPT, Gemini או Claude.

### שלב 2: העתקת הפרומפט

העתיקו את הפרומפט הבא.

### שלב 3: התאמת המידע לפרויקט

החליפו את המידע שבסוגריים במידע מהפרויקט שלכם.

### שלב 4: יצירת Workflow

בקשו מהמודל ליצור את קובץ ה־Workflow.

### שלב 5: בדיקה והבנה

עברו על הקובץ והבינו כל חלק לפני שאתם משתמשים בו.

### שלב 6: הוספה ל־Repository

הוסיפו את הקובץ ל־Repository ובדקו שהוא פועל.

```text
[ROLE]: Expert DevOps Engineer enforcing enterprise-level CI/CD compliance standards.

[CONTEXT]:
Here is my configuration file:
[Insert package.json / requirements.txt]

[OBJECTIVE]:
Construct a valid GitHub Actions YAML file triggered on push to main to run the project's Lint script.

Output only YAML.

[CONSTRAINTS]:
Run atop ubuntu-latest.
Must explicitly declare actions/checkout@v4 as step 01 because the runner starts empty.
```

---

## שאלות לבדיקה עצמית

* מהו Workflow?
* מהו Event ב־GitHub Actions?
* מה ההבדל בין Workflow, Job ו־Step?
* מהו GitHub Runner?
* מדוע יש להשתמש ב־`actions/checkout`?
* היכן ניתן למצוא את הודעת השגיאה המלאה כאשר Workflow נכשל?
* מה ההבדל בין שגיאת YAML לבין שגיאת Runtime?
* מדוע חשוב להבין את הקוד שנוצר על ידי AI לפני שמשתמשים בו?

---

## טעויות נפוצות

* שכחתם לבצע `git push`.
* קובץ ה־Workflow אינו נמצא בתיקייה `.github/workflows`.
* שגיאות הזחה (Indentation) בקובץ YAML.
* שימוש בפקודה שאינה קיימת בפרויקט.
* שכחתם להוסיף `actions/checkout`.
* ניסיון לתקן את הבעיה לפני קריאת הודעת השגיאה בלוגים.
* העתקת קוד שנוצר על ידי AI מבלי להבין את מטרתו.

---

## לסיכום

במעבדה זו הכרתם את GitHub Actions, יצרתם Workflow ראשון, למדתם כיצד לקרוא את ה־Logs ולהבין את תהליך הריצה, וכן התנסיתם בשימוש בכלי AI ליצירת Workflow בסיסי.

במעבדות הבאות נמשיך להרחיב את ה־Pipeline ונוסיף אליו יכולות נוספות כחלק מתהליך CI/CD מלא.
