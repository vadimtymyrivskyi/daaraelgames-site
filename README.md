# daaraelgames.com

Статичний сайт студії на GitHub Pages. Тут живуть головна, юридичні сторінки й `app-ads.txt`.

## Структура

```
.nojekyll                                  ← щоб Jekyll не чіпав файли
CNAME                                      ← daaraelgames.com
style.css                                  ← спільний стиль усіх сторінок
index.html                                 ← головна (див. нижче, ЧОМУ вона потрібна)
404.html                                   ← GitHub Pages сам підхоплює цей файл
app-ads.txt                                ← заповнений, див. нижче
hyper-impulse/privacy-policy/index.html
hyper-impulse/terms/index.html
```

Тека з `index.html` дає чистий URL: `daaraelgames.com/hyper-impulse/terms/`.
Друга гра = ще одна тека поруч із `hyper-impulse/`.

## Навіщо головна

⚠ **Не для `app-ads.txt`.** Краулер іде прямо на `/app-ads.txt` і головної не читає — файл
працював і тоді, коли корінь віддавав 404.

Головна потрібна **для перевірки в Play**: у лістингу є поле сайту розробника, і рецензент
туди клікає. Домен, що віддає 404, читається як покинутий або підставний.

Тому вона свідомо мінімальна — назва студії, гра, обидва юридичні посилання, пошта. Це не
маркетингова сторінка; роздувати її нема потреби.

## Підставлені значення

Заглушок у сторінках не лишилось:

| Що | Значення |
|---|---|
| пошта підтримки | `daaraelgames@gmail.com` |
| дата чинності | `15 September 2026` |

Пошта буде ПУБЛІЧНА на сторінці Play. Міняти її треба у ДВОХ місцях одночасно: Play Console →
Store listing → Contact details і тут, в обох `index.html`.

⚠ Дату чинності оновлювати щоразу, коли міняєш текст документів — це не декор, вона показує
гравцеві, що умови змінились.

## app-ads.txt

✅ **Готовий і живий 2026-09-15.** Publisher ID — `pub-4783100930867336`; він звірив його
з AdMob → Settings → Account information і запушив. Перевірено ззовні:
`https://daaraelgames.com/app-ads.txt` віддає 200.

⚠ **Лишився один крок, і він не в цьому репозиторії:** у Play Console на картці розробника
має стояти `https://daaraelgames.com`. Краулер бере домен ЗІ СТОРІНКИ ЗАСТОСУНКУ — без цього
посилання файл висить правильний, але його ніхто не звірить.

## Налаштування GitHub Pages

1. Settings → Pages → Source: **Deploy from a branch**, гілка `main`, тека `/ (root)`.
2. Custom domain: `daaraelgames.com` → Save (файл `CNAME` уже в репозиторії).
3. Дочекатись перевірки DNS, тоді увімкнути **Enforce HTTPS**.

DNS у реєстратора (apex-домен):

```
A     @    185.199.108.153
A     @    185.199.109.153
A     @    185.199.110.153
A     @    185.199.111.153
CNAME www  <твій-логін>.github.io
```

## Після публікації

У грі кнопки `Terms of Use` / `Privacy Policy` (`OpenUrlButton`) досі вказують на
`https://example.com` — перебити на:

```
https://daaraelgames.com/hyper-impulse/terms/
https://daaraelgames.com/hyper-impulse/privacy-policy/
```

Ту саму адресу політики вписати в Play Console → App content → Privacy policy.
