# Визуализация оптического потока <br> (Optical flow visualization)
В репозитории представлен метод визуализации оптических потоков
из **flow** файлов (**.flo**) с настраиваемыми параметрами отображения.
Проект предназначен только для визуализации результатов оценки
смещений, записанных в **flow** файлы.

## Запуск
Запуск осуществляется скриптом `run.py`.
В нем же задаются параметры визуализации.

## Описание
В `run.py` можно задавать следующие параметры: <br>
`args.color` – цвет векторов; <br>
`args.step` – расстояние между ближайшими векторами
(плотность отображения векторов); <br>
`args.size_vec` – масштаб векторов; <br>
`args.figsize` – размер изображения; <br>
`args.figure_dpi` – **dpi** изображения; <br>
`args.background` – изображение на фоне; <br>
`args.colormaps` – цветовая карты на фоне. <br>
Описание файлов: <br>
`readFlowFile.py` – чтение **flow** файлов (**.flo**). <br>
`computeColor.py` – визуализация смещений через цветовой круг,
альтернатива `visualizationFlow.py` (не настраиваемая визуализация). <br>
`visualizationFlow.py` – визуализация векторного поля (оптического потока). <br>
`demonstration.py` – демонстрация различных сценариев визуализации,
пример загрузки пользовательской цветовой карты. <br>
Пример работы `visualizationFlow` с отображением векторного поля

<p float="left">
<img src="/demos/DNS_turbulence.gif" width="300" />
<img src="/demos/example_1.png" width="353" />
</p>

Пример работы `computeColor`

<p float="left">
<img src="/demos/Color.gif" width="400" />
<img src="/demos/example_Color.png" width="367" />
</p>

Пример работы `visualizationFlow` только с цветовой картой

<p float="left">
<img src="/demos/vortexPair.gif" width="300" />
<img src="/demos/example_2.png" width="338" />
</p>

В каталоге [demos](/demos) находятся **flow** файлы, изображения и пример
пользовательской цветовой карты, которые использовались в `demonstration.py`.

## Замечания
- Нельзя одновременно выбрать фон (`args.background = …`) и 
цветовую карту (`args.colormaps = …`), нужно выбирать что-то одно.
- Если задать масштаб векторов равным нулю (`args.size_vec = 0`)
при использовании цветовой карты (`args.colormaps = …`), то 
вектора не будут отображаться.
- Можно посмотреть список всех доступных встроенных цветовых карт.
Для этого присвойте `args.help_color = “colormaps”`.
- Не добавлена возможность менять толщину стрелок векторов смещения.
