# Дмитрук Степан

## Контакты
- Email: [stepandzm6@gmail.com](mailto:stepandzm69@gmail.com)
- Telegram: [oddlystepan](https://t.me/oddlystepan)

## Навыки
- C++
- HTML & CSS
- Git
- Photoshop

## Образование
Я студент четвертого курса ГГТУ. Решил изучить что-то новое, а тут попался этот курс. Это главная причина, по которой я решил попробовать школу rs. Надеюсь, мое усердие и курсы помогут мне получить полезные знания.

## Пример кода
Задание звучало: Создание журнала системы с использованием syslog: Реализуйте программу, которая пишет системные логи в /var/log/syslog.
```C++
#include <stdio.h>
#include <stdlib.h>
#include <syslog.h>
#include <string.h>

void log_message(int level, const char *message) {
    syslog(level, "%s", message);
}

int main() {
    openlog("MySyslogProgram", LOG_PID | LOG_CONS, LOG_USER);

    int choice;
    char message[256];

    while (1) {
        printf("Выберите что вы хотите вывести в /var/log/syslog:\n");
        printf("1. Информация\n");
        printf("2. Предупреждение\n");
        printf("3. Ошибка\n");
        printf("4. Выход\n");
        printf("Введите ваш выбор (1-4): ");
        scanf("%d", &choice);

        if (choice == 4) {
            break;
        }

        printf("Введите сообщение: ");
        getchar();
        fgets(message, sizeof(message), stdin);
        message[strcspn(message, "\n")] = 0; 

        switch (choice) {
            case 1:
                log_message(LOG_INFO, message);
                break;
            case 2:
                log_message(LOG_WARNING, message);
                break;
            case 3:
                log_message(LOG_ERR, message);
                break;
            default:
                printf("Неверный выбор. Попробуйте снова.\n");
                break;
        }
    }

    closelog();

    return 0;
}
``` 
## Языки
- Немецкий
- Английский
- Русский
