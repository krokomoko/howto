# Emacs howto

## Установка (linux ubuntu)

	sudo apt update
	sudo apt install emacs

Затем скрываем Tool Bar в верхнем меню в Options > Show/Hide > Tool Bar > None.

## Конфигурационный файл

Конфигурационный файл находится по пути ~/.emacs

## Установка пакетов

### Дополнительные источники пакетов

Пакеты можно устанавливать из дополнительных источников.  
Для этого необходимо добавить ссылку на них в конфигурационный файл. Например:

	(require 'package)
	(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/"))

Для стабильной версии последнюю строку необходимо изменить следующим образом:
	
	(add-to-list 'package-archives '("melpa-stable" . "https://stable.melpa.org/packages/"))

([MELPA](https://github.com/melpa/melpa))

### Установка

Перед установкой внутри emacs необходимо выполнить команду:

	M-x package-list-packages
	или
	M-x package-refresh-contents

Где M-x - это сочетание клавиш Alt+x(английская "икс").  
Выполнение одной из этих команд приведёт к обновлению списка пакетов.

Для установки пакета выполняем команду:

	M-x package-install [RET] package_name [RET]

\[RET\] - означает "нажать Enter".  
package_name - название пакета, который вы хотите установить.  

Вместо:

	M-x package-install

Можно использовать:

	M-x p-ins

### Удаление

	M-x package-delete [RET] package_name [RET]


## Настройки внешнего вида

### Размер шрифта

Для установки шрифта и его размера в конфигурационный файл прописываем:

	(set-frame-font "Monospace 10")

Получаем дефолтный шрифт "Monospace" c 10 размером.


## Дополнительно

### Настройки для Go

#### Размер табуляции

Установка размера табуляции в 4 пробела:

	(require 'go-mode)
	(add-hook 'go-mode-hook (lambda () (setq tab-width 4)))

Первая строчка "включает" пакет "go-mode".