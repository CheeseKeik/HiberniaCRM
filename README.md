# HiberniaCRM
HiberniaCRM - front-end часть системы учёта и управления данными школы ирландский танцев Hibernia.
Данный проект является курсовой работой по дисциплине "Программные средства манипулирования данными", а также его продолжением в виде практических работ. \
Основной модуль и все зависимости находятся в [данном репозитории](https://github.com/AipNooBest/Hibernia).

## Установка проекта
Рекомендуется устанавливать проект с использованием Docker Compose, как это сделать описано [здесь](https://github.com/AipNooBest/Hibernia#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B0-docker-compose).
Однако, в целях разработки, нежелания использовать Docker или необходимости распределения комплекса на разные машины можно установить данную часть отдельно.

```shell
git clone https://github.com/CheeseKeik/HiberniaCRM.git
cd HiberniaCRM
npm install
# Здесь указывается адрес бэкенда
VITE_APP_API=http://localhost:3000/api/v1 npm run dev
```

