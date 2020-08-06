Решения всех задач реализованы на языке C++.

Disclaimer:
* В задачах task2 и task3 помимо вывода команд в файл, они выводятся и в консоль. При выводе в консоль могут быть проблемы вывода русских слов. Например: у меня в eclipse в консоль выводится все верно, но если запускаю программу в Windows Terminal, то в консоль выводятся машинные символы, вместо русских слов. Однако запись команд в файл всегда работает хорошо и записывает правильно русскими буквами.

Task 1:
* В качестве крестика использовался маленький регистр английской буквы икс - 'x', а в качество нолика использовался большой регистр английской буквы 'O'.
* Поскольку условие задачи не дает условия выигрыша в крестики-нолики для N > 3, поэтому я искал эти условия в Интернете и взял за основу из статьи в Википедии следующее: при размещении n >= 3 идентичных знаков подряд (крестики или нолики), тогда это считается победой на большом поле (>= 3 на 3).
Я прилагаю статью: https://ru.wikipedia.org/wiki/Крестики-нолики#Более_длинные_линии
* Но также, чтобы не было недоразумений в будущем и чтобы моя программа была более универсальной, я написал код в программе, который определяет победителя из условия, что ОДНА из диагоналей (или вертикалей, или горизонталей) ПОЛНОСТЬЮ заполнена одинаковыми символами (то есть крестиками или ноликами). Пример: если дано поле 6 на 6, то победитель будет тот, чьи символы занимают либо все 6 ячеек по горизонтале, либо все 6 ячеек по вертикале, либо все 6 ячеек по одной из диагоналей. Одновременно полностью заполнить 2 вертикали/горизонтали/диагонали (хотя диагонали тут явно лишние) нельзя. Для того, чтобы использовать данное условие, как выигрышное, необходимо закомментить 374 строку "string s = Board.check_func();" в функции main() и раскомментить 382 строку "string s = Board.check_func_n();" тоже в функции main().

Task 2:
* В условии не сказано в какой поток ввода подается поле и команды, поэтому я сделал ввод поля размера 9 на 9 из файла (также из файла считываются 10 команд, которые идут сразу после поля с новой строки), а вывод в cin и каждый раз в отдельный файл, как просят в конце задач. Регистр символа (английская буква икс), обозначающего палубу корабля, 'x' может быть любой. Я сделал в условном операторе как для маленького 'x', так и для большого 'X'.
* Для вывода русского текста в консоль использовалась функция setlocale(LC_ALL, "Russian");

Task 3:
* Пожалуй, для меня это оказалась самая трудная задача из всех трех. Для прохождения лабиринта (любого лабиринта с заданным финишем на краю карты, как в условии) я реализовал волновой алгоритм (алгоритм Ли, как его еще иногда называют). Соседние ячейки классифицировал по окрестности фон Неймана. Вот ссылка на википедию про алгоритм: https://ru.wikipedia.org/wiki/Алгоритм_Ли
* В решении предполагается, что выход из лабиринта точно есть. Программа способна обходить петли в лабиринте, тупики, перекестки. Она находит кратчайший путь от старта до финиша и выводит в поток cout набор команд, а также записывает их в файл (ну собственно, как это и делалось в предыдущих двух программах). Ввод лабиринта я сделал из файла (так гораздо удобнее с этим заданием). На первой строчке должно быть N - число, обозначающее размеры лабиринта. Со следующей строчки должна начинаться карта лабиринта. Именно так и написано в условии задачи. Кстати в условии написано, что команды должны быть следующими: "Наверх!", "Направо!", "Вниз!", "Налево!", а в примере выходных данных вместе команды "Наверх!" выводится "Вверх!". Я сделал по условию и использовал команду "Наверх!", но я думаю в этой задаче эта информация не столь важна :)
