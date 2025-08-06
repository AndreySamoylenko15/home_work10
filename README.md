📚 Address Book (OOP)
Цей проєкт реалізує адресну книгу з використанням об'єктно-орієнтованого підходу. Ви можете зберігати, змінювати, шукати й видаляти контакти та номери телефонів.

🧩 Основні класи
Field
Базовий клас для інших полів (наприклад, імʼя або номер телефону).

Name(Field)
Представляє ім’я користувача. Не може бути порожнім.

Phone(Field)
Валідує номер телефону: лише 10 цифр.

Record
Один запис у адресній книзі. Містить:

ім’я (Name)

список телефонів (Phone)

методи:

add_phone(phone)

edit_phone(old, new)

find_phone(phone)

remove_phone(phone)

AddressBook(UserDict)
Контейнер для обʼєктів Record. Має методи:

add_record(record)

find(name)

delete(name)

🧪 Приклад використання
python
Копіювати
Редагувати
book = AddressBook()

 Додаємо запис для John
john_record = Record("John")
john_record.add_phone("1234567890")
john_record.add_phone("5555555555")
book.add_record(john_record)

 Додаємо запис для Jane
jane_record = Record("Jane")
jane_record.add_phone("9876543210")
book.add_record(jane_record)

Виводимо всі записи
for name, record in book.data.items():
    print(record)

Редагуємо телефон John
john = book.find("John")
john.edit_phone("1234567890", "1112223333")
print(john)

 Шукаємо конкретний телефон
found_phone = john.find_phone("5555555555")
print(f"{john.name}: {found_phone}")

 Видаляємо запис Jane
book.delete("Jane")
💡 Приклад виводу
text
Копіювати
Редагувати
Contact name: John, phones: 1234567890; 5555555555
Contact name: Jane, phones: 9876543210
Contact name: John, phones: 1112223333; 5555555555
John: 5555555555
{'John': <__main__.Record object at 0x...>}
🧼 Валідація
Телефонні номери мають містити рівно 10 цифр, інакше буде викинута ValueError.

🛠 Вимоги
Python 3.6+

Бібліотеки: лише стандартна бібліотека (collections)
