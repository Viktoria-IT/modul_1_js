Модуль 2

Теория - Задание 1

Ранний возврат
В функции может быть больше одного оператора return. Главное помнить, что выполнение функции прерывается когда интерпретатор встречает возврат, и весь код после него будет проигнорирован в текущем вызове функции.

Возьмём уже знакомую нам функцию проверки совершеннолетия. Она работает, но здесь есть «лишний» код, то есть тело функции можно оптимизировать. В данном случае подойдёт приём (паттерн) «ранний возврат».

function checkAge(age) {
let message;

if (age >= 18) {
message = 'Вы совершеннолетний человек';
} else {
message = 'Вы не совершеннолетний человек';
}

return message;
}
Если условие в if выполняется, то есть приводится к true, возвращаем строку 'Вы совершеннолетний человек' и код ниже уже не исполнится.
Если условие в if не выполняется, то есть приводится к false, возвращаем строку 'Вы не совершеннолетний человек'.
Используя паттерн «ранний возврат» и то, что выполнение функции прерывается на операторе return, мы избавляемся от лишней переменной и блока else. То есть этот приём помогает «разгладить» ветвления.

Задание
Запиши условие в инструкции if так, чтобы функция работала правильно.

Тесты
Объявлена функция checkAge(age).
В выражении проверки возраста использован оператор >=.
Вызов checkAge(20) возвращает 'Вы совершеннолетний человек'.
Вызов checkAge(8) возвращает 'Вы не совершеннолетний человек'.
Вызов checkAge(14) возвращает 'Вы не совершеннолетний человек'.
Вызов checkAge(38) возвращает 'Вы совершеннолетний человек'.

Теория - Задание 2

Проверка пароля (ранний возврат)
Задание
Функция checkPassword получает пароль пользователя в параметр password, проверяет его на совпадение с паролем администратора в переменной ADMIN_PASSWORD и возвращает сообщение о результате сравнения.

Проведи рефакторинг кода функции checkStorage используя паттерн «ранний возврат»:

удали переменную message;
удали else;
код должен работать так же, как и до оптимизации.
Тесты
Объявлена функция checkPassword(password).
Вызов checkPassword('mangohackzor') возвращает 'Доступ запрещен, неверный пароль!'.
Вызов checkPassword('polyhax') возвращает 'Доступ запрещен, неверный пароль!'.
Вызов checkPassword('jqueryismyjam') возвращает 'Добро пожаловать!'.

Теория - Задание 3

Склад товаров 3.0
Задание
Функция checkStorage проверяет возможность оформления заказа и возвращает сообщение о результате. Она принимает два параметра, значения которых будут задаваться во время её вызова.

available - доступное количество товаров на складе;
ordered - количество единиц товара в заказе.
Проведи рефакторинг кода функции checkStorage используя паттерн «ранний возврат».

Тесты
Объявлена функция checkStorage(available, ordered).
Вызов checkStorage(100, 50) возвращает 'Заказ оформлен, с вами свяжется менеджер'.
Вызов checkStorage(100, 130) возвращает 'Слишком большой заказ, на складе недостаточно товаров!'.
Вызов checkStorage(70, 0) возвращает 'В заказе еще нет товаров'.
Вызов checkStorage(200, 20) возвращает 'Заказ оформлен, с вами свяжется менеджер'.
Вызов checkStorage(200, 250) возвращает 'Слишком большой заказ, на складе недостаточно товаров!'.
Вызов checkStorage(150, 0) возвращает 'В заказе еще нет товаров'.

Теория - Задание 4

Создание массива
Массив используется для хранения упорядоченной коллекции элементов. Он объявляется открывающей и закрывающей квадратной скобками [] - литералом массива. Внутри скобок каждый элемент массива разделяется запятой.

const planets = ['Земля', 'Марс', 'Венера'];
Полезно
При объявлении переменной для объекта или массива программисты обычно используют const. Они делают это для того, чтобы случайно не перезаписать значение, т.к. попытка перезаписи вызовет ошибку до того как код попадет к пользователю.

Задание
Объяви переменную fruits и присвой ей массив фруктов - строк 'яблоко', 'слива', 'груша' и 'апельсин'.

Тесты
Объявлена переменная fruits.
Значение переменной fruits это массив ['яблоко', 'слива', 'груша', 'апельсин'].

Теория - Задание 5

Доступ к элементам по индексу
Для доступа к значению элемента массива применяют синтаксис квадратных скобок массив[индекс]. Между именем переменной массива и квадратными скобками не должно быть пробела.

Внимание
Индексация элементов массива начинается с нуля.

const planets = ['Земля', 'Марс', 'Венера'];
planets[0]; // 'Земля'
planets[2]; // 'Венера'
Задание
Объяви три переменные и присвой каждой из них значение, используя нотацию квадратных скобок.

Имя переменной Значение переменной
firstElement первый элемент массива
secondElement второй элемент массива
lastElement последний элемент массива
Тесты
Объявлена переменная firstElement.
Значение переменной firstElement это строка 'яблоко'.
Объявлена переменная secondElement.
Значение переменной secondElement это строка 'слива'.
Объявлена переменная lastElement.
Значение переменной lastElement это строка 'апельсин'.

Теория - Задание 6

Переопределение значения элемента
В отличии от строк, элементы массива можно изменять обратившись к ним по индексу и присвоив другое значение.

const numbers = [1, 2, 3, 4, 5];
numbers[0] = 7;
numbers[2] = 14;
console.log(numbers); // [7, 2, 14, 4, 5];
Задание
Переопредели значения элементов с индексами 1 и 3. Замени 'слива' на 'персик', а 'апельсин' на 'банан'.

Тесты
Объявлена переменная fruits.
Значение переменной fruits это массив ['яблоко', 'персик', 'груша', 'банан'].

Теория - Задание 7

Длина массива
Длина массива, то есть число его элементов, хранится в свойстве length. Это динамическая величина, которая изменяется автоматически при добавлении или удалении элементов.

const planets = ['Земля', 'Марс', 'Венера'];
console.log(planets.length); // 3
Задание
Объяви переменную fruitsArrayLength и присвой ей длину массива fruits используя свойство length.

Тесты
Объявлена переменная fruitsArrayLength.
Значение переменной fruitsArrayLength это число 4.

Теория - Задание 8

Индекс последнего элемента
Чаще всего, мы заранее в коде не знаем какая будет длина массива. Для того, чтобы получить значение последнего элемента применяется следующий подход - длина массива всегда на единицу больше, чем индекс последнего элемента. Используя формулу длина_массива - 1 можно получить значение последнего элемента массива произвольной длины.

const planets = ['Земля', 'Марс', 'Венера'];
const lastElementIndex = planets.length - 1;
planets[lastElementIndex]; // 'Венера'
Задание
Объяви две перемнные:

Имя переменной Ожидаемое значение
lastElementIndex индекс последнего элемента масcива fruits через длина_массива - 1
lastElement значение последнего элемента массива
Тесты
Объявлена переменная lastElementIndex.
Значение переменной lastElementIndex это число 3.
Объявлена переменная lastElement.
Значение переменной lastElementIndex это строка 'банан'.

Теория - Задание 9

Крайние элементы массива
Задание
Напиши функцию getExtremeElements(array) которая принимает один параметр array - массив элементов произвольной длины. Функция должна возвращать массив из двух элементов - первого и последнего элемента параметра array.

Тесты
Объявлена функция getExtremeElements(array).
Вызов getExtremeElements([1, 2, 3, 4, 5]) возвращает [1, 5].
Вызов getExtremeElements(['Земля', 'Марс', 'Венера']) возвращает ['Земля', 'Венера'].
Вызов getExtremeElements(['яблоко', 'персик', 'груша', 'банан']) возвращает ['яблоко', 'банан'].

Теория - Задание 10

Метод строк split()
Метод split(delimeter) позволяет превратить строку в массив, «разбив» его по разделителю delimeter. Если разделитель это пустая строка, то получится массив отдельных символов. Разделителем может быть один или несколько символов.

const name = 'Манго';
console.log(name.split('')); // ['M', 'a', 'н', 'г', 'о']

const message = 'JavaScript это интересно';
console.log(message.split(' ')); // ['JavaScript', 'это', 'интересно']
Задание
Дополни код функции splitMessage(message, delimeter) так, чтобы она возвращала в переменной words результат разделения строки message по разделителю delimeter - массив строк.

Тесты
Объявлена функция splitMessage(message, delimeter).
Вызов splitMessage('Манго спешит на поезд', ' ') возвращает ['Манго', 'спешит', 'на', 'поезд'].
Вызов splitMessage('Манго', '') возвращает ['М', 'а', 'н', 'г', 'о'].
Вызов splitMessage('лучшее*за*неделю', '\_') возвращает ['лучшее', 'за', 'неделю'].

Теория - Задание 11

Гравировка украшений
Задание
Сервису гравировки украшений нужна функция, которая бы автоматически считала цену гравировки, в зависимости от количества слов и цены за слово.

Объявлена функция calculateEngravingPrice(message, pricePerWord). Эта функция принимает строку, состоящую из слов разделённых только пробелами (параметр message) и цену гравировки одного слова (параметр pricePerWord).

Напиши тело функции, чтобы она возвращала общую стоимость гравировки всех слов в строке.

Тесты
Объявлена функция calculateEngravingPrice(message, pricePerWord).
Вызов calculateEngravingPrice('JavaScript у меня в крови', 10) возвращает 50.
Вызов calculateEngravingPrice('JavaScript у меня в крови', 20) возвращает 100.
Вызов calculateEngravingPrice('Веб-разработка это творческая работа', 40) возвращает 160.
Вызов calculateEngravingPrice('Веб-разработка это творческая работа', 20) возвращает 80.

Теория - Задание 12

Метод массива join()
Метод массивов join(delimeter) позволяет соединить элементы массива в строку. В строке элементы будут разделены символом или группой символов указанных в delimeter. То есть это операция обратная методу строк split(delimeter).

const words = ['JavaScript', 'это', 'интересно'];
console.log(words.join('')); // 'JavaScriptэтоинтересно'
console.log(words.join(' ')); // 'JavaScript это интересно'
console.log(words.join('*')); // 'JavaScript*это\*интересно'
Задание
Дополни код функции makeStringFromArray(array, delimeter) так, чтобы она возвращала в переменной string результат соединения элементов массива array c разделителем delimeter - строку.

Тесты
Объявлена функция makeStringFromArray(array, delimeter).
Вызов makeStringFromArray(['Манго', 'спешит', 'на', 'поезд'], ' ') возвращает 'Манго спешит на поезд'.
Вызов makeStringFromArray(['М', 'а', 'н', 'г', 'о'], '')) возвращает 'Манго'.
Вызов makeStringFromArray(['лучшее', 'за', 'неделю'], '*') возвращает 'лучшее*за_неделю'.

Теория - Задание 13

Генератор slug
Задание
Термин slug - это человеко-понятный уникальный идентификатор, который используется в веб-разработке для создания читабельных URL-адесов.

Например, вместо того чтобы пользователь увидел в адресной строке mysite.com/posts/1q8fh74tx, можно сделать slug из названия статьи. В результате адрес получится более приятным для восприятия: mysite.com/posts/массивы-для-новичков.

Внимание
Slug это всегда строка в нижнем регистре, слова которой разделены тире.

Напиши функцию slugify(title) которая принимает заголовок статьи, параметр title, и возвращает slug, созданный из этой строки.

Значением параметра title будут строки, слова которых разделены только пробелами.
Все символы slug должны быть в нижнем регистре.
Все слова slug должна быть разделены тире.
Тесты
Объявлена функция slugify(title).
Вызов slugify('Массивы для новичков') возвращает 'массивы-для-новичков'.
Вызов slugify('Английский для разработчика') возвращает 'английский-для-разработчика'.
Вызов slugify('Десять секретов JavaScript') возвращает 'десять-секретов-javascript'.
Вызов slugify('Как стать JUNIOR разработчиком за ДВЕ НЕДЕЛИ') возвращает 'как-стать-junior-разработчиком-за-две-недели'.

Теория - Задание 14

Метод slice()
Метод slice(begin, end) возвращает новый массив, содержащий копию части исходного массива, не изменяя его. Копия делается от begin и до, но не включая, end - индексы элементов исходного массива.

Если begin и end не указаны, будет создана полная копия исходного массива.
Если не указан end, копирование будет от start и до конца исходного массива.
Если значение start отрицательное, а end не указан, то будут скопированы последние N элементов.
const planets = ['Земля', 'Марс', 'Венера', 'Юпитер', 'Сатурн'];

console.log(planets.slice(0, 2)); // ['Земля', 'Марс']
console.log(planets.slice(0, 4)); // ['Земля', 'Марс', 'Венера', 'Юпитер']
console.log(planets.slice(1, 3)); // ['Марс', 'Венера']
console.log(planets.slice(-2)); // ['Юпитер', 'Сатурн']
console.log(planets.slice()); // ['Земля', 'Марс', 'Венера', 'Юпитер', 'Сатурн']
Задание
Дополни код так, чтобы переменные содержали частичные копии исходного массива fruits.

firstTwoEls - массив из первых двух элементов.
nonExtremeEls - массив из всех элементов кроме первого и последнего.
lastThreeEls - массив из трёх последних элементов.
Тесты
Объявлена переменная fruits
Значение переменной fruits это массив ['яблоко', 'слива', 'груша', 'апельсин', 'банан'].
Объявлена переменная firstTwoEls
Значение переменной firstTwoEls это массив ['яблоко', 'слива'].
Объявлена переменная nonExtremeEls
Значение переменной nonExtremeEls это массив ['слива', 'груша', 'апельсин'].
Объявлена переменная lastThreeEls.
Значение переменной lastThreeEls это массив ['груша', 'апельсин', 'банан'].
Переменной lastThreeEls присвоена копия части массива fruits после применения метода slice с правильными аргументами.

Теория - Задание 15

Метод concat()
Метод concat используется для объединения двух или более массивов. Он не изменяет массив на котором вызывается, а возвращает новый. Порядок аргументов метода влияет на порядок элементов нового массива.

const firstArray = ['Меркурий', 'Венера', 'Земля'];
const secondArray = ['Марс', 'Юпитер'];
const thirdArray = ['Сатурн', 'Уран', 'Нептун'];
const allPlanets = firstArray.concat(secondArray, thirdArray);

console.log(firstArray); // ['Меркурий', 'Венера', 'Земля'];
console.log(allPlanets); // ['Меркурий', 'Венера', 'Земля', 'Марс', 'Юпитер', 'Сатурн', 'Уран', 'Нептун'];
Задание
Дополни код так, чтобы в переменной allClients получился массив всех элементов массивов oldClients и newClients.

Тесты
Объявлена переменная oldClients.
Значение переменной oldClients это массив ['Манго', 'Аякс', 'Поли', 'Киви'].
Объявлена переменная newClients.
Значение переменной newClients это массив ['Персик', 'Хьюстон'].
Объявлена переменная allClients.
Значение переменной allClients это массив ['Манго', 'Аякс', 'Поли', 'Киви', 'Персик', 'Хьюстон'].
Переменной allClients присвоен массив после применения метода concat с правильными аргументами.

Теория - Задание 16

Композиция массивов
Задание
Напиши функцию makeArray(firstArray, secondArray, maxLength) для создания нового массива со всеми элементами двух исходных firstArray и secondArray. Параметр maxLength содержит максимально допустимую длину нового массива.

Если количество элементов нового массива больше maxLength, функция должна вернуть копию массива длиной maxLength элементов.

В противном случае функция должна вернуть новый массив целиком.

Тесты
Объявлена функция makeArray(firstArray, secondArray, maxLength)
Вызов makeArray(['Манго', 'Поли'], ['Аякс', 'Челси'], 3) возвращает ['Манго', 'Поли', 'Аякс'].
Вызов makeArray(['Манго', 'Поли', 'Хьюстон'], ['Аякс', 'Челси'], 4) возвращает ['Манго', 'Поли', 'Хьюстон', 'Аякс'].
Вызов makeArray(['Манго'], ['Аякс', 'Челси', 'Поли', 'Хьюстон'], 3) возвращает ['Манго', 'Аякс', 'Челси'].
Вызов makeArray(['Земля', 'Юпитер'], ['Нептун', 'Уран'], 2) возвращает ['Земля', 'Юпитер'].
Вызов makeArray(['Земля', 'Юпитер'], ['Нептун', 'Уран'], 4) возвращает ['Земля', 'Юпитер', 'Нептун', 'Уран'].
Вызов makeArray(['Земля', 'Юпитер'], ['Нептун', 'Уран', 'Венера'], 0) возвращает [].
Вызов функции makeArray() со случайными массивами и случайным числом возвращает правильный массив.

Теория - Задание 17

Цикл for
Циклы используются для многократного повторения кода. Объявление цикла for состоит из трёх выражений.

for (Инициализация; Условие; Пост - выражение) {
// Тело цикла
}
Инициализация - выполняется один раз перед началом цикла. Используется для создания переменной-счётчика и указания её начального значения.
Условие - выражение, оцениваемое перед каждой итерацией (повторением) цикла. Тело цикла выполняется только тогда, когда выражение приводится к true. Цикл завершается, если значение будет false.
Пост-выражение - выполняется в конце каждого повторения цикла, перед проверкой условия. Используется для обновления переменной-счётчика.
Тело - набор инструкций для выполнения на каждом повторении. Выполняется, если выражение условия приводится к true.
for (let i = 0; i <= 20; i += 5) {
console.log(i);
}
В примере объявляется переменная i, инициализируется значением 0 и цикл выполняется (его тело) до тех пор, пока i <= 20, то есть условие приводится к true. После каждой итерации счётчик увеличивается на 5.

Задание
Дополни цикл for так, чтобы он логировал все целые числа в диапазоне от start до end включительно.

Тесты
Объявлена переменная start.
Значение переменной start это число 3.
Объявлена переменная end.
Значение переменной end это число 7.
Объявлена переменная i - счётчик цикла.
Начальное значение переменной i равно 3.
Условие цикла приводится к true до тех пор, пока i меньше либо равно 7.
На каждой итерации значение переменной i увеличивается на единицу.
Вывод в консоль переменной i покажет числа 3, 4, 5, 6, 7.

Теория - Задание 18

Сумма чисел (цикл for)
Задание
Напиши функцию calculateTotal(number), которая принимает целое число (параметр number) и возвращает сумму всех целых чисел от единицы и до этого числа. Например, если number равно 3, то сумма это 1 + 2 + 3, то есть 6.

Тесты
Объявлена функция calculateTotal(number).
Вызов функции calculateTotal(1) возвращает 1.
Вызов функции calculateTotal(3) возвращает 6.
Вызов функции calculateTotal(7) возвращает 28.
Вызов функции calculateTotal(18) возвращает 171.
Вызов функции calculateTotal(24) возвращает 300.
Вызов функции calculateTotal() со случайным числом возвращает правильное значение.

Теория - Задание 19

Итерация по массиву
Цикл for можно использовать для итерации по массиву, то есть «перебрать» его поэлементно.

const planets = ['Земля', 'Марс', 'Венера'];

for (let i = 0; i < planets.length; i += 1) {
console.log(planets[i]);
}
Для доступа к элементам используется синтаксис квадратных скобок массив[индекс], где индекс - это значение счётчика цикла от 0 и до последнего индекса массива, который на единицу меньше длины массива.

Задание
Дополни код цикла for так, чтобы он последовательно логировал все элементы массива fruits.

Тесты
Объявлена переменная fruits.
Значение переменной fruits это массив ['яблоко', 'слива', 'груша', 'апельсин'].
Объявлена переменная i - счётчик цикла.
Начальное значение переменной i равно 0.
Условие цикла приводится к true до тех пор, пока i меньше 4.
На каждой итерации значение переменной i увеличивается на единицу.
В теле цикла for объявляется переменная const fruit и этой переменной присваивается значение - элемент массива.
В теле цикла for используется вывод в консоль переменной fruit.

Теория - Задание 20

Подсчёт суммы покупки
Задание
Напиши функцию calculateTotalPrice(order), которая принимает один параметр order - массив чисел, и рассчитывает общую сумму его элементов. Общая сумма элементов должна сохраняться в переменной total, которая возвращается, как результат работы функции.

Тесты
Объявлена функция calculateTotalPrice(order).
Вызов функции calculateTotalPrice([12, 85, 37, 4]) возвращает 138.
Вызов функции calculateTotalPrice([164, 48, 291]) возвращает 503.
Вызов функции calculateTotalPrice([412, 371, 94, 63, 176]) возвращает 1116.
Вызов функции calculateTotalPrice() со случайным массивом возвращает правильное значение.

Теория - Задание 21

Поиск самого длинного слова
Задание
Напиши функцию findLongestWord(string) которая принимает произвольную строку состоящую только из слов разделённых пробелом (параметр string) и возвращает самое длинное слово в этой строке.

Тесты
Объявлена функция findLongestWord(string).
Вызов функции findLongestWord('The quick brown fox jumped over the lazy dog') возвращает jumped.
Вызов функции findLongestWord('Google do a roll') возвращает Google.
Вызов функции findLongestWord('May the force be with you') возвращает force.
Вызов функции findLongestWord() со случайной строкой возвращает правильное значение.

Теория - Задание 22

Метод push()
Метод push() позволяет добавить один или несколько элементов в конец массива, без необходимости указывать индексы добавляемых элементов.

const planets = ['Земля', 'Марс', 'Венера'];
planets.push('Юпитер');
planets.push('Сатурн', 'Уран', 'Нептун');

console.log(planets); // ['Земля', 'Марс', 'Венера', 'Юпитер', 'Сатурн', 'Уран', 'Нептун']
Задание
Дополни код функции createArrayOfNumbers(min, max) так, чтобы она возвращала массив всех целых чисел от значения min до max.

Тесты
Объявлена функция createArrayOfNumbers(min, max).
Вызов функции createArrayOfNumbers(1, 3) возвращает [1, 2, 3].
Вызов функции createArrayOfNumbers(14, 17) возвращает [14, 15, 16, 17].
Вызов функции createArrayOfNumbers(29, 34) возвращает [29, 30, 31, 32, 33, 34].
Вызов функции createArrayOfNumbers() со случайными min и max возвращает правильный массив.
В цикле for использовался метод push.

Теория - Задание 23

Фильтрация массива чисел
Задание
Напиши функцию filterArray(numbers, value), которая принимает массив чисел (параметр numbers) и возвращает новый массив, в котором будут только те элементы массива numbers, которые больше чем значение параметра value (число).

Тесты
Объявлена функция filterArray(numbers, value).
Вызов функции filterArray([1, 2, 3, 4, 5], 3) возвращает [4, 5].
Вызов функции filterArray([1, 2, 3, 4, 5], 4) возвращает [5].
Вызов функции filterArray([1, 2, 3, 4, 5], 5) возвращает [].
Вызов функции filterArray([12, 24, 8, 41, 76], 38) возвращает [41, 76].
Вызов функции filterArray([12, 24, 8, 41, 76], 20) возвращает [24, 41, 76].
Вызов функции filterArray() со случайным массивом и числом возвращает правильный массив.
В цикле for использовался метод push.

Теория - Задание 24

Метод includes()
Метод includes(value) проверяет есть ли в массиве элемент со значением value и возвращает true или false соответственно. Область применения этого метода сводится к ситуациям, когда необходимо проверить есть ли элемент в массиве и не важна его позиция (индекс).

const planets = ['Земля', 'Марс', 'Венера'];

console.log(planets.includes('Земля')); // true
console.log(planets.includes('земля')); // false
console.log(planets.includes('Венера')); // true
console.log(planets.includes('Юпитер')); // false
Задание
Функция checkFruit(fruit) принимает строку с названием фрукта (параметр fruit), и проверяет есть ли такой фрукт в массиве fruits.

Дополни код функции так, что если:

фрукт есть в массиве, то функция возвращает true;
фрукта нет в массиве, то функция возвращает false.
Тесты
Объявлена функция checkFruit(fruit).
Вызов checkFruit('слива') возвращает true.
Вызов checkFruit('мандарин') возвращает false.
Вызов checkFruit('груша') возвращает true.
Вызов checkFruit('Груша') возвращает false.
Вызов checkFruit('яблоко') возвращает true.
Вызов функции checkFruit() со случайным словом возвращает правильное значение boolean.
В функции использовался метод includes.

Теория - Задание 25

Общие элементы
Задание
Общими элементами массивов называют те элементы, которые присутствуют во всех массивах.

Например, в двух массивах [1, 3, 5] и [0, 8, 5, 3] общими будут числа 3 и 5, т.к. они присутствуют в обоих исходных массивах. А числа 0, 1 и 8 присутствуют только в одном из массивов.

Напиши функцию getCommonElements(array1, array2) которая получает два массива произвольной длины в параметры array1 и array2, и возвращает новый массив, состоящий из тех элементов, которые присутствуют в обоих исходных массивах.

Тесты
Объявлена функция getCommonElements(array1, array2).
Вызов getCommonElements([1, 2, 3], [2, 4]) возвращает [2].
Вызов getCommonElements([1, 2, 3], [2, 1, 17, 19]) возвращает [1, 2].
Вызов getCommonElements([24, 12, 27, 3], [12, 8, 3, 36, 27]) возвращает [12, 27, 3].
Вызов getCommonElements([10, 20, 30, 40], [4, 30, 17, 10, 40]) возвращает [10, 30, 40].
Вызов getCommonElements([1, 2, 3], [10, 20, 30]) возвращает [].
Вызов функции getCommonElements() со случайными двумя массивами возвращает правильный массив.
В цикле for использовались методы includes и push.

Теория - Задание 26

Цикл for...of
Инструкция for...of объявляет цикл, перебирающий итерируемые объекты, такие как массивы и строки. Тело цикла будет выполняться для значения каждого элемента. Это хорошая замена циклу for, если не нужен доступ к счётчику итерации.

for (const variable of iterable) {
// тело цикла
}
variable — переменная, которая будет хранить значение элемента на каждой итерации.
iterable — коллекция, которая имеет перечислимые элементы, например массив.
const planets = ['Земля', 'Марс', 'Венера'];

for (const planet of planets) {
console.log(planet);
}
Задание
Выполни рефакторинг кода функции calculateTotalPrice(order) заменив цикл for на for...of.

Тесты
Объявлена функция calculateTotalPrice(order).
Вызов функции calculateTotalPrice([12, 85, 37, 4]) возвращает 138.
Вызов функции calculateTotalPrice([164, 48, 291]) возвращает 503.
Вызов функции calculateTotalPrice([412, 371, 94, 63, 176]) возвращает 1116.
Вызов функции calculateTotalPrice([]) возвращает 0.
Вызов функции calculateTotalPrice() со случайным массивом чисел возвращает правильную сумму.

Теория - Задание 27

Фильтрация массива чисел 2.0
Задание
Выполни рефакторинг функции filterArray(numbers, value) заменив цикл for на for...of.

Тесты
Объявлена функция filterArray(numbers, value).
Вызов функции filterArray([1, 2, 3, 4, 5], 3) возвращает [4, 5].
Вызов функции filterArray([1, 2, 3, 4, 5], 4) возвращает [5].
Вызов функции filterArray([1, 2, 3, 4, 5], 5) возвращает [].
Вызов функции filterArray([12, 24, 8, 41, 76], 38) возвращает [41, 76].
Вызов функции filterArray([12, 24, 8, 41, 76], 20) возвращает [24, 41, 76].
Вызов функции filterArray() со случайным массивом и числом возвращает правильный массив.

Теория - Задание 28

Оператор %
Вместо того, чтобы возвращать результат деления, операция по модулю (%) возвращает целочисленный остаток от деления двух чисел - делимого и делителя.

5 % 1 = 0
// 5, разделенное на 1, равно 5, а остаток - 0

5 % 2 = 1
// 5, разделенное на 2, равно 2, а остаток - 1

5 % 3 = 2
// 5, разделенное на 3, равно 1, а остаток - 2

5 % 4 = 1
// 5, разделенное на 4, равно 1, а остаток - 1

5 % 5 = 0
// 5, разделенное на 5, равно 1, а остаток - 0
Задание
Дополни выражения остатка от деления так, чтобы код проходил тесты.

Тесты
Объявлена переменная a.
Значение переменной a это число 0.
Объявлена переменная b.
Значение переменной b это число 1.
Объявлена переменная c.
Значение переменной c это число 3.
Объявлена переменная d.
Значение переменной d это число 5.
Объявлена переменная e.
Значение переменной e это число 2.

Теория - Задание 29

Чётные числа
Проверка на четность

function isEven (num) {
return num % 2 === 0;
}
Задание
Напиши функцию getEvenNumbers(start, end) которая возвращает массив всех чётных чисел от start до end. Чётным считается число которое делится на 2 без остатка.

Тесты
Объявлена функция getEvenNumbers(start, end).
Вызов функции getEvenNumbers(2, 5) возвращает [2, 4].
Вызов функции getEvenNumbers(3, 11) возвращает [4, 6, 8, 10].
Вызов функции getEvenNumbers(6, 12) возвращает [6, 8, 10, 12].
Вызов функции getEvenNumbers(8, 8) возвращает [8].
Вызов функции getEvenNumbers(7, 7) возвращает [].
Вызов функции getEvenNumbers() со случайными start и end возвращает правильный массив.

Теория - Задание 30

Теория - Задание 31

Теория - Задание 32