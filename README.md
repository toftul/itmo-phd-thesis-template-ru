# Шаблон кандидатской диссертации в Университете ИТМО в LaTeX

Это не оффициальный шаблон. 

Если вы пишете диссертацию на английском языке, то сущетсвует [toftul/itmo-phd-thesis-template-en](https://github.com/toftul/itmo-phd-thesis-template-en).

Видео инструкция на YouTube:

[<img src="https://wiki.physics.itmo.ru/images/3/31/%D0%94%D0%B8%D1%81%D1%81%D0%B5%D1%80_%D0%B2_%D1%82%D0%B5%D1%85%D0%B5.png" width="50%">](https://youtu.be/ghJgTtJuJPE "Кандидатская диссертация в LaTeX. Шаблон и инструкция")

## Зачем это

Есть оффициальный шаблон на сайте [диссовета ИТМО](https://dissovet.itmo.ru/index.php?main=110), что явлется форком другого известного шаблона [AndreyAkinshin/Russian-Phd-LaTeX-Dissertation-Template](https://github.com/AndreyAkinshin/Russian-Phd-LaTeX-Dissertation-Template). 

Но что первый, что второй шаблоны очень перегружены и ими довольно сложно пользоваться, не обладая большим опытом в программировании и $\LaTeX$. Кроме того, там учтено множество возможностей (презентация, docker, отдельная компиляция автореферата, выбор разных движков всего подряд и т.д.), которые не пригождаются при написании диссертации в ИТМО. Оказывается, что можно выкинуть больше половины, что и было сделано.


## Что измененено

1. Убраны все файлы, которые вам не пригодятся при компиляции в Overleaf. Также убраны папки с документациями и ГОСТом;
2. Убран выбор между `bibtex` и `biblatex` в пользу последнего, т.к. это наболее современный вариант сборки библиографии;
3. Реферат и Synopsys вставленны внутрь основного документа, как этого требует шаблон ИТМО;
4. Переделаны счётчики и вывод своих статей (сколько всего, сколько в Scopus и т.д.).
5. Многие настройки совмещены, чтобы файлов стало меньше.
6. В папке `Dissertation` теперь только про диссертацию, а не про настройку шаболна.


## Как пользоваться

### Начало
* Скачиваете `zip` этого репозитория;
* Заливаете его на [Overleaf](https://www.overleaf.com/).

### Дополнительные настройки и пакеты
Все свои доп. пакеты и кастомные функции закидывайте в файл `Dissertation/custom.tex`, чтобы не трогать другие файлы, которые отвечают за стилистику и работу шаблона.

### Литература
Есть два файла с литературой (**очень советую делать bib-записи через [BibItNow!](https://chrome.google.com/webstore/detail/bibitnow/bmnfikjlonhkoojjfddnlbinkkapmldg?hl=en-US)**):
1. `biblio/references.bib` — стандартный bib-файл, куда идут все источники, которые вы собираетесь цитировать, включая свои работы;
2. `biblio/own.bib` — тут только ваши статьи и конференци, для автоматического вывода в характеристике работы. К каждой нужно будет руками добавить нужные `keywords`, чтобы все работало.

Возможные `keywords` такие: 
* `own` — это ваша статья, не конференция;
* `wos` — Web if Science;
* `scopus` — Scopus;
* `vak` — ВАК;
* `other` — статья/просидинг из других источников;
* `conf` — конференция.

Пример:
```bib
@article{Toftul2019Oct,
        keywords = {own, scopus, wos},  % <--- here!
        author = {Toftul, I. D. and Bliokh, K. Y. and Petrov, M. I. and Nori, F.},
        title = {{Acoustic Radiation Force and Torque on Small Particles as Measures of the Canonical Momentum and Spin Densities}},
        journal = {Phys. Rev. Lett.},
        volume = {123},
        number = {18},
        pages = {183901},
        year = {2019},
        month = {Oct},
        issn = {1079-7114},
        publisher = {American Physical Society},
        url = {https://doi.org/10.1103/PhysRevLett.123.183901},
        doi = {10.1103/PhysRevLett.123.183901},
}

%Sorry for this but this works
@article{metanano2021,
        keywords = {conf},  % <--- here!
	author = {\textbf{METANANO}},
	year={2021},
	journal = {13-17 September 2021 Saint Petersburg, Russia (Online)},
	title = {{Two talks: High-Q states in acoustic apple-shaped resonators., Nonlinear circular dichroism in Mie-resonant nanoparticle dimers}}
}
```

### Компиляция оффлайн

- Используйте [texstudio](https://www.texstudio.org/)
- Убедитесь, что установлен `biber`
- Измените движок библиографии с `bibtex` на `biber`

### Остальное

Всё остальное должно быть интуитивно понятно при работе.


## Возможные проблемы и решения

### Ошибка U+0301

Самое простое решение: удалите все символы `\'` в `biblio/references.bib`.

### Не компилирует ссылки

* Убедитесь, что стоит движок библиографии `biber` в настройках вашего редактора.
* Убедитесь, что установлен свежий дистрибутив теха.

