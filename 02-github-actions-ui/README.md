# GitHub Actions Lab 02: Building a Professional Workflow

במשימה זו תבנו Workflow חדש מאפס עבור הפרויקט שלכם.

המטרה אינה להעתיק Workflow קיים, אלא לתכנן ולבנות Pipeline ברור, קריא ומסודר, בדיוק כפי שהייתם עושים בפרויקט אמיתי.

מותר להשתמש בתיעוד הרשמי של GitHub ובכלי AI, אך עליכם להבין כל שורה שאתם מוסיפים.

---

## הדרישות

בנו Workflow חדש העומד בכל הדרישות הבאות.

### Trigger

ה-Workflow יופעל בעת:

- Push לענף `main`

---

### Runner

ה-Workflow חייב לרוץ על:

```yaml
ubuntu-latest
```

---

### Checkout

השלב הראשון ב-Workflow חייב להשתמש ב:

```yaml
actions/checkout@v4
```

---

### Setup

הכינו את סביבת העבודה בהתאם לפרויקט שלכם.

בחרו אחת מהאפשרויות:

#### Node.js

השתמשו ב:

```yaml
actions/setup-node@v4
```

והגדירו את גרסת Node באמצעות `with`.

או

#### Python

השתמשו ב:

```yaml
actions/setup-python@v5
```

והגדירו את גרסת Python באמצעות `with`.

---

### Workflow Steps

הוסיפו לפחות חמישה Steps בעלי שמות ברורים.

דוגמאות:

- Checkout repository
- Setup Node.js
- Display Node version
- Install dependencies
- Run project check

אין חובה להשתמש דווקא בשמות אלו.

---

### run

השתמשו בלפחות שלוש פקודות `run`.

לדוגמה:

- הדפסת גרסת השפה
- התקנת תלויות
- הרצת בדיקה בסיסית

---

### Documentation

לפני הוספת כל Action חדש:

- פתחו את ה-README שלו.
- ודאו שאתם משתמשים בגרסה העדכנית.
- בדקו אילו פרמטרים ניתן להעביר באמצעות `with`.

---

### AI Review

לאחר שסיימתם, העתיקו את ה-Workflow לכלי AI ובקשו ממנו לבצע Code Review.

השתמשו בפרומפט הבא:

```text
You are a Senior DevOps Engineer reviewing a GitHub Actions workflow.

Explain every section of the workflow.

Identify possible improvements.

Do not rewrite the entire workflow unless necessary.

Focus on readability, structure and best practices.
```

אם ה-AI מציע שיפור שנראה לכם נכון — יישמו אותו.

---

## Challenge

לאחר שה-Workflow עובד בהצלחה:

צרו תקלה מכוונת אחת.

לדוגמה:

- מחיקת `actions/checkout`
- שינוי גרסת Node לגרסה שאינה קיימת
- הרצת פקודה שאינה קיימת

בצעו Push.

פתחו את ה-Logs.

זהו:

- באיזה Step התקלה התרחשה.
- מה הייתה הודעת השגיאה.
- כיצד פתרתם אותה.

לאחר מכן תקנו את התקלה והריצו שוב את ה-Workflow עד לקבלת ריצה תקינה.

---

## שאלות לבדיקה עצמית

- מתי משתמשים ב-`run` ומתי ב-`uses`?
- למה `actions/checkout` בדרך כלל מופיע ראשון?
- מה תפקידו של `setup-node` או `setup-python`?
- למה חשוב לקרוא את ה-README של Action לפני השימוש?
- מתי כדאי להיעזר ב-AI ומתי כדאי להיעזר בתיעוד הרשמי?

---

## טעויות נפוצות

- שכחתם לבצע `git push`.
- ה-Workflow נמצא בתיקייה שגויה.
- שימוש ב-Action ללא קריאת התיעוד.
- שימוש ב-`run` במקום `uses`.
- ניסיון להריץ פקודות לפני `actions/checkout`.
- העתקת Workflow שנוצר על ידי AI מבלי להבין אותו.

---

## לסיכום

במעבדה זו תכננתם ובניתם Pipeline מלא עבור הפרויקט שלכם, תוך שימוש ב-GitHub Marketplace, בתיעוד הרשמי ובכלי AI.

בנוסף, תרגלתם Debug של Workflow, קריאת Logs ושיפור Pipeline קיים — מיומנויות שהן חלק בלתי נפרד מעבודת CI/CD בעולם האמיתי.
