# daaraelgames.com

Статичний сайт студії на GitHub Pages. Тут живуть тільки юридичні сторінки й `app-ads.txt`.

## Структура

```
.nojekyll                                  ← щоб Jekyll не чіпав файли
CNAME                                      ← daaraelgames.com
style.css                                  ← спільний стиль усіх сторінок
app-ads.txt                                ← ⚠ ЩЕ НЕМАЄ, див. нижче
hyper-impulse/privacy-policy/index.html
hyper-impulse/terms/index.html
```

Тека з `index.html` дає чистий URL: `daaraelgames.com/hyper-impulse/terms/`.
Друга гра = ще одна тека поруч із `hyper-impulse/`.

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

⚠ **Не класти порожній або шаблонний `app-ads.txt` у корінь.** Файл без правильного рядка
означає «цьому сайту ніхто не дозволений продавати рекламу» — це гірше, ніж його відсутність:
покупці перестануть купувати покази. Тому він лежить як `app-ads.txt.TEMPLATE`.

Коли зʼявиться додаток в AdMob:
1. AdMob → Settings → Account information → скопіювати **Publisher ID** (`pub-…`).
2. Підставити його замість `pub-XXXXXXXXXXXXXXXX` у `app-ads.txt.TEMPLATE`.
3. Перейменувати файл на `app-ads.txt` і закомітити.
4. У Play Console картка розробника має містити `https://daaraelgames.com` — краулер AdMob
   шукає файл саме за адресою зі сторінки додатка.
5. Перевірити, що відкривається `https://daaraelgames.com/app-ads.txt`.

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
