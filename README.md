Task 1:
Поскольку условие задачи не дает условия выигрыша в крестики-нолики для N > 3, поэтому я искал эти условия в Интернете и взял за основу из статьи в Википедии следующее: при размещении n >= 3 идентичных знаков подряд (крестики или нолики), тогда это считается победой.
Я прилагаю статью: https://ru.wikipedia.org/wiki/Крестики-нолики#Более_длинные_линии

Task 2:
В условии не сказано в какой поток ввода подается поле и команды, поэтому я сделал ввод в поток cout, а вывод в cin и каждый раз в отдельный файл, как просят в конце задач. Регистр символа, обозначающего палубу корабля, 'x' может быть любой. Я сделал в условном операторе как для маленького 'x', так и для большого 'X'.
Для вывода русского текста в консоль использовалась функция setlocale(LC_ALL, "Russian");
