# test_solution
Задача

Необходимо реализовать чтение значений со входа АЦП с использованием DMA с дискретизацией 5 КГц и установки полученных усреднённых значений на выходе ЦАП раз в 25 милисекунд.  А также выдаче усреднённых за 1 секунду значений по SWD интерфейсу в терминал IDE Keil. Полученные значения выводить в мили вольтах, формат представления в ASCII кодах с символом перевода строки на конце (пример: «1500 mV\r\n»).
Выбор ножек на ваше усмотрение.

Проект необходимо сгенерировать в STM32CubeMX для среды Keil с использованием библиотек «LL» для АЦП, для остальной периферии на «HAL».

Описание полученного кода сформировать в формате Doxygen.

По факту выполнения выложить в доступный GIT репозиторий.

Решение

1. Запуск Таймера на частоте 5кГц
2. Запуск преобразования ADC по переполнению таймера
3. Сбор данных ADC при помощи DMA в буфер на 125 значений
4. При заполнении буфера (раз в 25мс)- расчёт среднего значния и высталвение значения в DAC
5. Раз в секунду, из суммы 5000 значений находится среднее и передаётся в терминал
