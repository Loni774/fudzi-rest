from aiogram import Bot, Dispatcher, types
from aiogram.types import (
    ReplyKeyboardMarkup,
    KeyboardButton,
    InlineKeyboardMarkup,
    InlineKeyboardButton
)

main = ReplyKeyboardMarkup(
    keyboard=[
        [KeyboardButton(text='Меню')],
        [KeyboardButton(text='О нас', url='https://fudzi.rest/about')],
        [
            KeyboardButton(text='Условия доставки', url='https://fudzi.rest/usloviya-dostavki'),
            KeyboardButton(text='Контакты', url='https://fudzi.rest/contacts')
        ]
    ],
    resize_keyboard=True,
    input_field_placeholder='Выберите пункт меню...')


menu_items = [
    ('Популярное', 'https://fudzi.rest/'),
    ('Пицца и бургеры', 'https://fudzi.rest/'),
    ('Роллы', 'https://fudzi.rest/'),
    ('Маки роллы', 'https://fudzi.rest/'),
    ('Теплые роллы', 'https://fudzi.rest/'),
    ('Сеты', 'https://fudzi.rest/'),
    ('Салаты', 'https://fudzi.rest/'),
    ('Супы', 'https://fudzi.rest/'),
    ('Горячие блюда', 'https://fudzi.rest/'),
    ('Лапша и рис', 'https://fudzi.rest/'),
    ('Десерты', 'https://fudzi.rest/'),
    ('Детское меню', 'https://fudzi.rest/'),
    ('Напитки', 'https://fudzi.rest/'),
    ('Лимонады', 'https://fudzi.rest/'),
    ('Коктейли', 'https://fudzi.rest/'),
    ('Гарниры', 'https://fudzi.rest/'),
    ('Завтраки', 'https://fudzi.rest/'),
    ('Сашими', 'https://fudzi.rest/'),
    ('Суши', 'https://fudzi.rest/'),
    ('Гунканы', 'https://fudzi.rest/'),
    ('Хлеб', 'https://fudzi.rest/'),
    ('Соусы', 'https://fudzi.rest/'),
    ('Сок натуральный', 'https://fudzi.rest/'),
    ('Свежевыжатый сок', 'https://fudzi.rest/'),
    ('Кофе и какао', 'https://fudzi.rest/'),
    ('Холодный кофе', 'https://fudzi.rest/')
]

menu_rows = []
for i in range(0, len(menu_items), 2):
    row = []
    for item in menu_items[i:i+2]:
        row.append(InlineKeyboardButton(text=item[0], url=item[1]))
    menu_rows.append(row)

menu = InlineKeyboardMarkup(inline_keyboard=menu_rows)

get_number = ReplyKeyboardMarkup(
    keyboard=[[KeyboardButton(text='Отправить номер', request_contact=True)]],
    resize_keyboard=True)
