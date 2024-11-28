# Задание 1

## Описание

Основной функционал приложений

1) Регистрация / аутентификация
2) Редактирование профиля
3) Добавление / удаление фотографий
4) Лайки на фотографиях

## Выбор технологии

В силу простоты приложения, было решено выбрать Module federation, 
так как:
- Нет необходимости использовать разные фреймворки
- Можно обмениваться зависимостями во время работы приложения
- Проще внедрить

## Разделение на микрофронтенды

Исходя из функционала приложения, логично выделить 3 микрофронтенда:

1) Авторизация
2) Профиль
3) Карточки

Однако, Профиль пользователя и Карточки реализованы в рамках 
одного компонента Main. 
Также кнопка добавления карточки расположена в блоке профиля.
Разделение этих компонентов потребует дополнительных трудозатрат. 

Для разделения этого блока на два компонента необходимо рассмотреть 
изменения в UI сервиса, в частности вынос кнопки 
добавления карточки в блок с карточками. 
Данные доработки могут быть реализованы в 
рамках вторго этапа перехода на микрофронетнды.

Было принято решение на первом этапе выделить 
два микрофрофронтенда.

1) Авторизация
2) Основной контент (Профиль+Карточки)

## Модульное взаимодействие

Для целей модульного взаимодействия принято решение использовать 
библиотеку ReactContext. Так как она уже используется в 
проекте и потребности в переходе на более продвинутые инструменты нет.

## Структура кода

- Авторизация
    - Login
    - Register

- Основной контент (Профиль+Карточки)
    - Main
    - Card
    - ImagePopup
    - AddPlacePopup
    - EditAvatarPopup
    - EditProfilePopup

- Общие компоненты (host)
    - Footer
    - Header
    - InfoTooltip
    - PopupWithForm
    - App

_Уровень 3 для задания 1 не реализован_
  
# Задание 2

https://drive.google.com/file/d/1doiD2ZgoSXXPnSWKMPIO8HMFOm0ipSzP/view?usp=share_link