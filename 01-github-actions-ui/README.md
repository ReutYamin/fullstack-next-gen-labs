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

### שלבי העבודה

1. היכנסו ל־Repository שלכם ב־GitHub.
2. פתחו את לשונית **Actions**.
3. בחרו אחת מהתבניות המוצעות (לדוגמה: **Simple Workflow** או **Node.js**).
4. מחקו את פקודות ברירת המחדל שבחלק `steps`.
5. הוסיפו שתי פקודות `run`:

   * פקודת `echo` שמדפיסה הודעה לבחירתכם.
   * פקודה המציגה את גרסת שפת הפיתוח של הפרויקט (לדוגמה `node --version` או `python --version`).
6. בצעו Commit ישירות לענף `main`.
7. חזרו ללשונית **Actions** ועקבו אחר הריצה עד לסיומה.
8. פתחו את ה־Logs ובדקו שכל השלבים הושלמו בהצלחה.

---

## משימה 2 – יצירת תקלה וניתוח ה־Logs

### שלבי העבודה

1. צרו שגיאת Runtime מכוונת בפרויקט (לדוגמה פקודה שאינה קיימת או שגיאת Syntax).
2. בצעו:

   * `git add`
   * `git commit`
   * `git push`
3. עברו ללשונית **Actions**.
4. אתרו את ה־Workflow שנכשל.
5. פתחו את הריצה ובדקו:

   * איזה Job נכשל.
   * איזה Step נכשל.
   * מהי הודעת השגיאה.
6. תקנו את הבעיה.
7. בצעו Push נוסף וודאו שה־Pipeline מסתיים בהצלחה.

---

## משימה 3 – יצירת Workflow באמצעות AI

במשימה זו תשתמשו בכלי AI כדי ליצור Workflow שמריץ את תהליך ה־Lint של הפרויקט.

### שלבי העבודה

1. פתחו את ChatGPT, Gemini או Claude.
2. העתיקו את הפרומפט הבא.
3. החליפו את המידע שבסוגריים במידע מהפרויקט שלכם.
4. בקשו מהמודל ליצור את קובץ ה־Workflow.
5. עברו על הקובץ והבינו כל חלק לפני שאתם משתמשים בו.
6. הוסיפו את הקובץ ל־Repository ובדקו שהוא פועל.

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

1. מהו Workflow?
2. מהו Event ב־GitHub Actions?
3. מה ההבדל בין Workflow, Job ו־Step?
4. מהו GitHub Runner?
5. מדוע יש להשתמש ב־`actions/checkout`?
6. היכן ניתן למצוא את הודעת השגיאה המלאה כאשר Workflow נכשל?
7. מה ההבדל בין שגיאת YAML לבין שגיאת Runtime?
8. מדוע חשוב להבין את הקוד שנוצר על ידי AI לפני שמשתמשים בו?

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
