## Задача № 1
### Отображение списка
Редкое приложение обходится без отображения списка. Это один из самых популярных компонентов в тестовых заданиях и очень популярный вопрос на собеседованиях.

**Задание:**
В этом домашнем задании дается стартовое приложение, которое показывает список строк простейшим образом. Вам нужно переписать его, используя класс SimpleAdapter и добавить подзаголовок.

Пошаговый план действий:
* Создать xml разметку для элемента списка с двумя текстовыми полями.
* Из массива строк построить список словарей (`List<Map<String, String>>`), необходимый для использования `SimpleAdapter`.
* Вместо `ArrayAdapter` в методе `createAdapter` создать `SimpleAdapter` и вернуть его из этого метода.
* Использовать созданный адаптер в списке.

**Выполнение**

1. Исследуйте стартовое приложение, находящееся в папке `./code`.
2. Добавьте ConstraintLayout в `app/build.gradle`. (`implementation 'androidx.constraintlayout:constraintlayout:1.1.3`).
3. Создать xml файл в папке `res/layout` для элемента списка на основе ConstraintLayout, состоящий из двух TextView, один под другим.
4. Еще раз повторите конструктор `SimpleAdapter`. Без детального понимания следующие два пункта будет сложно выполнить.
5. Изменить метод `prepareContent` так, чтобы он возвращал список словарей строк (`List<Map<String, String>>`), нужный для `SimpleAdapter`.
Из каждого элемента списка мы будем создавать строку в интерфейсе, каждый элемент должен содержать заголовок и подзаголовок.
То есть в каждом элементе списка (`Map<String, String>`) должно быть 2 записи (`MapEntry<String, String>`), одна для заголовка, вторая для подзаголовка.
В качестве заголовка используем элемент массива строк из оригинального приложения (`String[] arrayContent = getString(R.string.large_text).split("\n\n"); arrayContent[i];`), подзаголовком будет длина этой строки (`arrayContent[i].length()`).
6. В методе `createAdapter` измените входной параметр на `List<Map<String, String>>` и создайте `SimpleAdapter` вместо `ArrayAdapter`, так, чтобы заголовок и подзаголовок отображались в каждой строке.
Для этого используйте layout, созданный в пенкте 3, и параметры `from` (ключи словаря с заголовком и подзаголовком из пункта 5) и `to` (id элементов `TextView`, созданных в пункте 3) конструктора `SimpleAdapter`.
7. Запустите приложение, объясните, почему не потребовалось менять тип возвращаемого значения из метода `createAdapter`.

**Результаты и сдача домашнего задания**

В результате должно получиться приложение со списком, где каждый элемент состоит из абзаца текста и цифры его длины, расположенной под этим абзацем.
Выполненное домашнее задание загрузить на GitHub.

Примерный вид экрана

![](https://user-images.githubusercontent.com/9194227/54371882-4267ad00-468b-11e9-846a-1f4578a22cde.png)
