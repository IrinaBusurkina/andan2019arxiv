# Исследуем корпус научных статей Arxiv
на хакатоне, [на АнДане, на Летней школе](https://letnyayashkola.org/andan/)

**🔥 презентация результатов: [ссылка](https://docs.google.com/presentation/d/e/2PACX-1vRoOlAfA2eQ2_0XPdL30cxxz4tVRicYEUsgQDTDBswwt1K7MrH1Ub72BpUEDmzFdrrowtNBJ1aDFBHm/pub?start=false&loop=false&delayms=60000)**

Кураторы: Олег Сериков, Даниил Скоринкин  
Тренировочный подкорпус для ознакомления: [data_examples/arxiv_data_small.csv](https://github.com/andan2019sysblockhackathon-arxivtask/arxivTask/blob/master/data_examples/arxiv_data_small.csv)  
Полный корпус скачать: https://transfer.sh/Ty5yp/arxiv_data_full.csv


* [Тема](https://github.com/andan2019sysblockhackathon-arxivtask/arxivTask#тема)
* [Описание корпуса](https://github.com/andan2019sysblockhackathon-arxivtask/arxivTask#Описание-корпуса)
* [Задачи для исследований](https://github.com/andan2019sysblockhackathon-arxivtask/arxivTask#Задачи-для-исследований)


## Тема

Абстракты и метаданные по 31000+ статей с сайта arXiv по машинному обучению/компьютерному зрению/компьютерной лингвистике и NLP/прочему AI и Data Science — с 1992 по 2018 год.


## Описание корпуса
<!-- (версия 1.0) -->

Данные по 31000+ статей с сайта arXiv. Сайт arXiv — это открытый ресурс для публикации научных статей, очень популярный у физиков, математиков, программистов и — особенно в последние годы — у датасаентистов. В нашем датасете представлены статьи по машинному обучению (machine learning), компьютерной лингвистике и обработке языка (CL, NLP), компьютерному зрению (CV), а также ИИ в широком смысле (AI). Для каждой статьи есть абстракт, то есть короткая выжимка с основным содержанием статьи, и метаинформация: заглавие, авторы, дата написания, гиперссылка на статью на самом arXiv, e-mail-ы авторов (не для всех статей). Временной диапазон статей — с 1992 по 2018 год. 

Формат данных — CSV


## Исследовательские сценарии

### Парсинг и анализ данных
* Сеть связей между вузами (связь — соавторство над статьей, достаем из поля "email")
* Посмотреть активность публикаций в течение года (по месяцам), построить граик помесячной активности — поле "month"
* Построить графики появления конкретных слов/ словосочетаний в абстрактах статей (например, "rule-based", "neural", "neural network", "deep learning"... ) — поле "abstract"
* Когда научный мир начал использовать электронные адреса, как это соотносится с общемировым развитием электронной почты? Агрегировать по времени количество электронных адресов или статей с электронными адресами, сравнить с какой-то статистикой из интернета. Поле "email"
* Сейчас в AI редко кто-то пишет статьи в одиночку. Было ли так всегда или коммуникация стала особенно важна в какой-то (какой?) момент? Поле "author" (либо сделанное на его основе поле "число авторов")

### Тематическое моделирование абстрактов
* Правда ли, что NLP (автоматическая обработка естественного языка) отстаёт от CV (компьютерное зрение) на несколько лет? Подзадачи: 
  * Достаём подкорпусы про NLP и CV
  * Делаем топик моделинг в этих областях в общем и по временным интервалам
  * Находим общие топики/ключевые слова/что-то ещё и смотрим, есть ли временная задержка в популярности технологий в области исследований
* найти обзорные статьи статьи (например, на медиуме или хабре) “топ трендов такого-то года”, попробовать сопоставить с результатами топик моделинга

## ~~[старое] Задачи для исследований~~

### ~~Тематическое моделирование~~
1. ~~Правда ли, что NLP (автоматическая обработка естественного языка) отстаёт от CV (компьютерное зрение) на несколько лет?~~
    *   ~~Достаём подкорпусы про NLP и CV~~
    *   ~~Делаем топик моделинг в этих областях в общем и по временным интервалам~~
    *   ~~Находим общие топики/ключевые слова/что-то ещё и смотрим, есть ли временная задержка в популярности технологий в области исследований~~
1. ~~Как вообще ведут себя хайповые темы в машинном обучении и анализе данных? Например, в 2018 было много всего про transfer learning в NLP ([BERT, ELMO, GPT2](http://jalammar.github.io/illustrated-bert)). Было бы полезно уметь автоматически замечать зарождение хайпа (может, например, всё начинается с пейпера гугла-фейсбука, а заканчивается появлением какого-то следующего классного пейпера. а может, нет), интересно также, сколько популярные темы остаются популярными~~
    *   ~~можно построить графики популярности ключевых слов по времени, будет интересно взглянуть~~
    *   ~~можно посмотреть на статьи (например, на медиуме или хабре) «топ трендов такого-то года», попробовать сопоставить с результатами топик моделинга (это, кстати, может сработать и в другую сторону, позволив оценить объективность таких подборок)~~
1. ~~Есть ли что-то общее у статей, впервые затрагивающих популярные в будущем вопросы. Например, может, авторы таких статей уже опытные и много публиковались в т.ч. на arxiv или более-менее связаны друг с другом историей совместных публикаций.~~
    *   ~~Стоит попробовать придумать разные предикторы и посмотреть, коррелируют ли они с таргетом, описанным в вопросе~~


### ~~Парсинг, анализ и обработка метаданных~~

1. ~~Визуализация научного сотрудничества -- какие универы работают с какими и над какими областями; переходят ли исследователи в процессе такого сотрудничества из универа в универ; сколько аффилиаций сменяет один человек за время научной деятельности~~
    *   ~~В метаданных нет аффилиаций, но зато есть электронные адреса авторов. Домен электронной почты человека, аффилированного с институтом, обычно связан с институтом~~
1. ~~В последнее время большое количество прорывов приходит из Google, Facebook и других технологических AI-компаний. Когда это началось? (Может, с приходом моды на нейросети?)~~
    *   ~~Связь авторов с техногигантом можно понять из электронных адресов авторов~~
    *   ~~Когда нейросети стали модными -- из топик моделинга по временным интервалам~~
1. ~~Когда научный мир начал использовать электронные адреса, как это соотносится с общемировым развитием электронной почты?~~
    *   ~~Агрегировать по времени количество электронных адресов или статей с электронными адресами, сравнить с какой-то статистикой из интернета~~
1. ~~Сейчас в AI редко кто-то пишет статьи в одиночку. Было ли так всегда или коммуникация стала особенно важна в какой-то (какой?) момент?~~

<!-- Куда делись мемы про from xgboost import * ?-->

**~~Список идей пополняется. Предлагайте свои идеи!~~**
