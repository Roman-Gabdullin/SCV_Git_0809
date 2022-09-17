![Logo](Git_logo.jpg)
![Logo](Kontr_ver.jpg)
# **Работа с Git** 

## **1. Проверка наличия установленного Git**
*В терминале выполнить команду `git version`
Если Git установлен, появится сообщение с информацией о версии программы. Иначе будет сообщение об ошибке.*

## **2. Установка Git**
*Загружаем последнюю версию с сайта [https://git-scm.com/downloads](https://git-scm.com/downloads/) 
Устанавливаем с настройками по умолчанию.*

## **3. Настройка Git**
*При первом испольозвании Git необходимо представиться. Для этого нужно ввести в терминале две команды:*
```
git config --global user.name «Ваше имя английскими буквами»

git config --global user.email ваша почта@example.com
```
## **4. Инициализация репозитория**
Получить репозиторий можно двумя способами.
1. В терминале переходим к папке, в которой хотим создать репозиторий.
Выполняем команду: 

`git init`

В исходной папке появится скрытая папка __.git__
2. Клонировать существующий репозиторий Git из любого места. Для этого используется команда: 

`git clone<адрес репозитория>`.

### **Команда `git status`**
*Показывает текущее состояние гита, есть 
ли изменения, которые нужно закоммитить
(сохранить).*

>Чтобы вызвать ранее введённую команду, пользуемся стрелками на клавиатуре. Перебираем недавно введённые команды нажатием стрелки «вверх».

### **Команда `git add`**
*Добавляет содержимое рабочего каталога 
в индекс (staging area) для последующего коммита. Эта команда дается после добавления
файлов. Писать название целиком не обязательно: терминал дозаполнит данные автоматически.*
### **Команда `git commit`**
*Зафиксировать или сохранить*

>По умолчанию `git commit` использует лишь этот индекс, так что вы можете использовать git add для сборки слепка вашего следующего коммита.
Команда `git commit` берёт все данные, добавленные в индекс с помощью `git add`, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.
### **Команда `git log`**
* *Журнал изменений.*
* *Перед переключением версии файла в Git
используйте команду* `git log`, *чтобы увидеть
количество сохранений.*

>Нажатие клавиши ‘q’ возвращает в исходное окно терминала.
### **Команда `git checkout`**
* *Переключение между версиями.*
* *Для работы нужно указать не только
интересующий вас коммит, но и вернуться 
в тот, где работаем, при помощи команды* 
`git checkout master`.
### **Команда `git diff`**
* *Показывает разницу между текущим файлом
и сохранённым.*
* *Перед переключением версии файла в Git
используйте команду* `git log`*, чтобы увидеть
количество сохранений.*
## **5. Запись изменений в репозиторий**
Чтобы посмотреть состояние файлов в репозитории необходимо выполнить команду `git status`.
Для того, чтобы начать отслеживать новый файл, используется команда  `git add<имя файла с расширением>`.
## **6. Игнорирование файлов**
Для того чтобы, начать игнорировать файлы в папке репозитория, которые нужно игнорировать, необходимо создать файл `".gitignore"`, в котором запиываются имена файлов (с расширением), которые Git будет игнорировать. 
## **7. Работа с ветками**
1. Создание веток
Для того чтобы создать ветку используется команда `"git branch <имя ветки>"`. Чтобы создать ветку и сразу перейти в нее используется команда `"git checkout -b <имя ветки>"`.

2. Слияние веток
Для того чтобы слить ветки, нам необходимо:
* Перейти к той ветке в которую мы будем загружать информацию из другой ветки
* Ввести команду `"git merge <имя ветки из которой мы загружаем информацию в текущую ветку>"`

3. Конфликты при слиянии ветвей

Процесс слияния далеко не всегда проходит гладко. Если в двух ветках, которые
вы собираетесь слить, вы внесли разные изменения в один и тот же файл, Git не
сможет просто взять и объединить их. В этом случае Git не может автоматически создать коммит слияния. Система приостанавливает процесс до момента разрешения конфликта.Все, что относится к области конфликта слияния, помечено как неслитое (`"unmerged"`).
Система Git добавляет к проблемным файлам стандартные метки, позволяющие
открывать эти файлы вручную и разрешать конфликты. При этом на экране появляется две версии. Версия с указателем `"HEAD"` (из вашей ветки текущей ветки, так как именно в нее вы перешли перед выполнением команды merge) располагается в верхней части блока (то есть выше набора символов =======), а версия из ветки (источника слияния) показана
в нижней части. Для разрешения конфликта следует или выбрать одну из версий,
или каким-то образом объединить их.

4. Удаление веток

Для удаления ветки используем команду `"git
branch -d <имя удаляемой ветки>"`
> Обратите внимание, необходимо указывать d маленькую. d большая тоже будет удалять, но
лучше пользоваться маленьким. Это позволит Git выполнять удаление только тогда, когда у
нас всё в порядке. Только тогда, когда у нас эта ветка полностью объединена с другой и
удаление ничего не поломает.