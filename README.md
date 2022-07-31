# Parsing_mirea_bot

Бот анализирует конкурсные списки РТУ МИРЭА. Данные берутся с https://vuzopedia.ru/admission-aggregate/753 
и https://priem.mirea.ru/accepted-entrants-list/. Если у человека статут "согласие на другом конкурсе" или он подал оригинал и аттестат в другой вуз, то в рейтинге бота не отображается/

Пример:
1)user1
2)user2  (согласие на другом конкурсе)
3)user3  (подал в другой вуз)
4)user4

Бот выведет , что у user4 - 2 место, поскольку user2, user3 подали согласия и оригиналы в другое место.
Код сопоставляет списки с 2-ух сайтов, причем рассматриваются конкретно бюджетные направления.

Необходимые библиотеки:
import requests
from bs4 import BeautifulSoup
import pandas as pd
import telebot
