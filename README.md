# Web-Virtual-Library

Описание предметной области:   
Админка книжного интернет-магазина, которая будет предоставлять возможности просмотра каталога книг, их сортировки, фильтрации, добавления, удаления и редактирования.

Стек:   
TypeScript, React, Next.js

Описание страниц:   
Страница со списком карточек книг - изображения книг с названиями   
Страница с подробностями по конкретной книге - вся информация о данной книге   
Страница с редактированием/добавлением информации о книге:   
	форма для редактирования - форма с валидацией   
	Основные поля книги:   
		- Изображение   
		- Идентификатор книги (маленьким шрифтом под изображением)   
		- Название книги   
		- Автор   
		- Жанр   
		- Год издания   
		- Издательство   
		- Описание сюжета   
		- Цена   
		- Отзывы   
Страница ошибок:   
	404   
	500   
Навигация через таббар или кнопки назад на главную страницу   

Фильтрация   
	Все книги   
		- По названию   
		- По жанру   
		- По автору   
		- По году издания   
		- По цене   
Сортировка   
	Все книги   
		- По названию   
		- По жанру   
		- По автору   
		- По году издания   
		- По цене   


Список API:     

Эндпоинт: /get_books   
Возвращает список всех книг для нужной  страницы, дополнительные параметры определяют фильтрацию и сортировку   
Http метод: GET   
Параметры:   
	page: number   
	category: Category | undefined   
	countPerPage: number | undefined   
	orderBy: SortingKey | undefined   
	filters: Filters | undefined   

Эндпоинт: /add_book   
Добавление новой книги   
Http метод: POST   
Параметры: Все параметры, описывающие добавляемый объект   

Эндпоинт: /update_book/:id   
Обновление полей уже существующей книги по id   
Http метод: PATCH   
Параметры:   
	- Изображение   
	- Год издания   
	- Издательство   
	- Описание сюжета   
	- Цена   

Эндпоинт: /get_book/:id   
Возвращает книгу по id   
Http метод: GET   

Эндпоинт: /remove_book/:id   
Удаляет книгу по id   
Http метод: DELETE   

Эндпоинт: /get_validation_schema   
Нужно, чтобы тянуть с сервера схему, в соотвтествии с которой мы будем валидировать формы добавления и обновления продукта   
Http метод: GET   
Параметры:   
	category: Category   
