# drupal7_uc_paymaster

UC Paymaster module for Drupal 7

Модуль предназначен для работы с Drupal 7 и Ubercart 3

1. Закачать файлы из архива через ftp в папку sites/all/modules/modules/ubercart/payment/uc_paymaster. 

2. В директории сайта /admin/store/settings/payment/method/paymaster произвести настройки: 
- Merchant id — идентификатор сайта (его можно взять в личном кабинете PayMaster);
- Merchant secret key — секретный ключ (изначально задается в личном кабинете PayMaster);
- Currency - валюта, а точнее ее код (для рублей RUB). Так смотрите коды валют по ISO 4217 на странице https://ru.wikipedia.org/wiki/%D0%9A%D0%BE%D0%B4%D1%8B_%D0%B8_%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B_%D0%B2%D0%B0%D0%BB%D1%8E%D1%82;
- Payment details - здесь просто пишите описание платежа, именно он будет отображаться в интерфейсе PayMaster;
- Order status after payment - статус заказа после успешной оплаты, 
- VAT for XXX for online invoicing - здесь XXX тип товара в Ubercart, разные товары могут иметь разные ставки НДС. Это необходимо для работы нового федерального закона от 22.05.2003 N 54-ФЗ «О применении контрольно-кассовой техники при осуществлении наличных денежных расчетов и (или) расчетов с использованием платежных карт». То есть вы можете создать в Ubercart разные товары с разными ставками НДС - это как раз необходимо для онлайн кассы;
- VAT for delivery for online invoicing - ставка НДС для товара типа (точнее услуги) доставка.

3. В личном кабинете PayMaster (Список сайтов->Настройки->Обратные вызовы):

В Payment notification выбрать POST-запрос и прописать: http://ВАШ_САЙТ.ru/cart/paymaster/result

В Success redirect выбрать POST-запрос и прописать: http://ВАШ_САЙТ.ru/cart/paymaster/success

В Failure redirect выбрать POST-запрос и прописать: http://ВАШ_САЙТ.ru/cart/paymaster/fail

Также очень важно не забыть прописать в интерфейсе PayMaster.ru "Технические параметры->Тип подписи->md5" 
И также очень важно прописать "Секретный ключ", который скрыт в целях безопасности, он нужен для верификации оплаты и должен совпадать с "Merchant secret key" из пункта 2. 

_Все вопросы по разработке/доработке модуля присылайте на awa77 собака mail.ru
Автор Алексей А._ 