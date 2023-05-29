
![](./images/data_cleaning.png)
# <center> Анализ результатов А/В тестирования </center>
## Оглавление
1. [Описание проекта](#Описание-проекта)
2. [Описание данных](#Описание-данных)
3. [Зависимости](#Зависимости)
4. [Установка проекта](#Установка-проекта)
5. [Использование проекта](#Использование-проекта)
6. [Авторы](#Авторы)
7. [Выводы](Использование-проекта)

## Описание проекта

> **Компания планирует запустить новую акцию, чтобы продать как можно больше туров. Команда разработала два варианта посадочной страницы официального сайта компании и провела A/B-тестирование. 
Для решения настоящей бизнес-задачи выполнено следующее: проанализирована эффективность обоих вариантов посадочной страницы сразу по двум критериям: конверсии покупки и среднему чеку. На основе проведенного анализа  сделаны выводы о том какой из вариантов дизайна более предпочтительный.

## Описание данных
В этом проекте используются данные результатов А/В тестирования, полученные от применения двух вариантов дизайна посадочных страниц офиального сайта туристической компании.

Требования компании определить какой дизайн посадочной страницы более эффективно решает задачу: продать как можно больше туров. 

Исходный датасет представляет собой набор данных из таблицы с информацией о ID-пользователя посетившего страницу, дате захода на сайт, группе теста (контрольная — А или тестовая — B), признаке покупки: совершил ли пользователь покупку тура (1 — да, 0 — нет), цене купленного тура (если покупка не состоялась, цена равна 0)

Файл с данными можно найти [здесь](https://drive.google.com/file/d/1FdMCttChuBBRRK6CVIsEzuvytlbMCYTh/view?usp=share_link).

## Используемые зависимости
* Python (3.9):
    * [numpy (1.20.3)](https://numpy.org)
    * [pandas (1.3.4)](https://pandas.pydata.org)
    * [matplotlib (3.4.3)](https://matplotlib.org)
    * [seaborn (0.11.2)](https://seaborn.pydata.org)
    
scipy.stats import norm
scipy.stats import t
scipy.stats import ttest_ind, shapiro, f_oneway, mannwhitneyu
statsmodels.stats.proportion import proportions_ztest

## Установка проекта

```
git clone https://github.com/Oksana8346/Project_3.git
```

## Использование
Вся информация о работе представлена в jupyter-ноутбуке Template_EDA_5.ipynb.

## Авторы

* [Оксана Г.](ссылка на ваши соц сети)

## Выводы

Итак, для того, чтобы правильно интерпретировать результаты А/В тестирования, и оценить на сколько применение варианта А или варианта В способно решить поставленную задачу, вернемся к цели, которую ставила перед собой компания. А звучала она так: "Компания планирует запустить новую акцию, чтобы продать как можно больше туров. Команда разработала два варианта посадочной страницы официального сайта...". То есть цель - продать как можно больше туров. Но оценить эффективность каждого варианта предполагалось не только по конверсии, но и по размеру среднего чека.

По итогам всех манипуляций с данными, как говориться "в сухом остатке" мы имеем: конверсии в обоих группах одинаковые, средний чек выше в группе В. К каким выводам нас это подводит?

 Изначально мы рассмотривали туры, предусматривающие три вида отдыха: Санкт-Петербург - городской отдых в культурной среде с посещением достопримечательностей, Камчатка - отдых для любителей красоты и величия уникальной природы этого края, Турция, Тайланд, Мальдивы - пляжный отдых. Большинство тех, кто заходит на сайт тур-оператора заранее определились с видом отдыха и рассмотривают варианты уже внутри одного их этих трех направлений. То, что по направлению "пляжный отдых" Мальдивы рассматривают люди, готовые к существенным тратам на путешествие, может означать, что компании слолжно предложить им достаточно "дорогой" (выгодный, привлекательный) акционный кейс. Поэтому на приобрешение туров по направлению Мальдивы акции, предлагаемые компанией не влияют (продажи в обоих группах сопоставимы). Туры на Камчатку и в Санкт-Петербург являются уникальными в своих направлениях. Например Камчатке можно предпочесть Байкал или Карелию, но не Тайланд, а Санкт-Петербургу - Москву, Казань или Нижний Новгород, но не Турцию (продажи в обоих группах по этим направлениям также сопоставимы). Таким образом мы подходим к тому, что предоставлением акционных кейсов можно стимуллировать покупательную способность на относительно бюджетный отдых у моря. 

 Поэтому мой совет компании, доработать дизайн посадочной страницы именно с акцентом на направления Турция, Тайланд.

 Пару слов о том, почему при наличии более высокого среднего чека в группе В, я не советую однозначно принимать этот вариант дизайна, как единственно предпочтительный. Мы выяснили, что средний чек в группе В выше за счет большего числа покупки туров в Тайланд. Следует учесть, что на некоторых курортах Тайланда очень продолжительный сезон дождей, и естественным образом это обстоятельство снизит спрос на туры в Тайланд на этот период. Именно поэтому дизайн, который имеет преимущества по чеку только за счет туров в Тайланд не обеспечит высокий чек на долгосрочную перспективу.
 
 Не могу не отметить, что данная работа не предполагает анализ тех посетителей сайта, которые были вначале исключены из данных, по причине того, что пользовались и А и В версией, то есть попали в обе группы. Возможно, если посмотреть как вели себя пользователи которые имели возможность сравнить два варианта, то можно было бы сделать предположения на тему сниженного спроса на туры в Турцию в группе В и проработать конкретно это направление, тем более что из 1895 исключенных пользователей 460 все таки совершили покупки. 

 Учитывая, что при постановке задачи по увеличению продажи туров, речь шла о том, что компания планирует запустить новую акцию. Мы не знаем, какая это акция, но понимаем, что акции бывают очень разными от бесплатной расширенной страховки, бесплатного трансфера до скидок на товары компаний-партнеров, поэтому возможно компании стоит пересмотреть само содержание акции. Главное, на отдыхе люди хотят отдыхать, а не решать проблемы, поэтому та компания, которая предложит наиболее эффективное решение всех возможных трудностей, та и получит клиента, а это и конверсия и высокий чек.