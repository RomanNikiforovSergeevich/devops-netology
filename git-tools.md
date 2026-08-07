## Задание 1. Поиск хеша коммита `aefea`
* **Полный хеш:** `aefead2207ef7e2aa5dc81a34aedf0cad4c32545`
* **Комментарий:** `Update CHANGELOG.md`
* *Метод получения:* Использована команда `git show aefea`.

## Задание 2. Тег для коммита `85024d3`
* **Ответ:** Тег `v0.12.23`.
* *Метод получения:* Использована команда `git describe --tags 85024d3`.

## Задание 3. Родители коммита `b8d720`
* **Количество родителей:** 2
* **Хеши родителей:** 
  1. `56cd7859e05c36c06b56d013b55a252d0bb7e158`
  2. `9ea88f22fc6269854151c571162c5bcf958bee2b`
* *Метод получения:* Использована команда `git show --pretty=%P b8d720`.

## Задание 4. Коммиты между тегами v0.12.23 и v0.12.24
* **Метод получения:** Выполнена команда `git log --oneline v0.12.23..v0.12.24`
* **Список коммитов:**
  * `33ff1c03bb` (tag: v0.12.24) v0.12.24
  * `b14b74c493` [Website] vmc provider links
  * `3f235065b9` Update CHANGELOG.md
  * `6ae64e247b` registry: Fix panic when server is unreachable
  * `5c619ca1ba` website: Remove links to the getting started guide's old location
  * `06275647e2` Update CHANGELOG.md
  * `d5f9411f51` command: Fix bug when using terraform login on Windows
  * `4b6d06cc5d` Update CHANGELOG.md
  * `dd01a35078` Update CHANGELOG.md
  * `225466bc3e` Cleanup after v0.12.23 release

## Задание 5. Создание функции `providerSource`
* **Метод получения:** Выполнена команда `git log -S "func providerSource" --oneline`. Самый нижний (первый по хронологии) коммит в выводе является точкой создания функции.
* **Коммит создания:** `8c928e8358` с комментарием `main: Consult local directories as potential mirrors of providers`.

## Задание 6. Изменения функции `globalPluginDirs`
* **Метод получения:** Поиск выполнен через отслеживание изменений строк с помощью команды `git log -G "globalPluginDirs" --oneline`.
* **Список коммитов:**
  * `7c4aeac5f3` stacks: load credentials from config file on startup (#35952)
  * `22a2580e93` main: Use the new cliconfig package credentials source
  * `35a058fb3d` main: configure credentials from the CLI config file
  * `c0b1761096` prevent log output during init
  * `8364383c35` Push plugin discovery down into command package

## Задание 7. Автор функции `synchronizedWriters`
* **Метод получения:** Сначала с помощью `git log -S "synchronizedWriters" --oneline` были найдены коммиты, связанные с функцией. Затем команда `git show --name-only bdfea50cc8` определила имя файла, в котором она находилась — `synchronized_writers.go`. Наконец, автор строки объявления функции был найден с помощью команды `git blame 5ac311e2a9 -- synchronized_writers.go`.
* **Автор:** Martin Atkins
