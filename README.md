# second-messenger-desk
import time
from plyer import notification
from datetime import datetime

# Настройки уведомления
title = "Ежедневная сводка"
message = "Не забудьте выполнить важные задачи на сегодня!"

# Время показа уведомления (24-часовой формат)
notification_time = "09:00"  # Время, когда должно появляться уведомление

def show_notification(title, message):
    notification.notify(
        title=title,
        message=message,
        app_name='Daily Summary',
        timeout=10  # Длительность отображения уведомления в секундах
    )

def main():
    while True:
        # Получаем текущее время
        current_time = datetime.now().strftime("%H:%M")
        
        # Если текущее время совпадает с временем уведомления
        if current_time == notification_time:
            show_notification(title, message)
            time.sleep(60)  # Ждем 60 секунд, чтобы не показывать уведомление несколько раз

        time.sleep(1)  # Проверяем время каждую секунду

if __name__ == "__main__":
    main()
