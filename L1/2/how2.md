[Назад](/L1/L1_.md) 
## как диагностировать, что программа заснула, а не в дедлоке

- Профилирования памяти pprof
- Проверка работы процессора. Если программа заснула, вы можете увидеть, что процессор не активен или показывает низкую загрузку.
- Логирование,  между слипами  может происходить вывод данных в лог
- Отладка delve

--------------------------------------
Чтобы диагностировать, что программа заснула, а не находится в состоянии дедлока, можно использовать следующие подходы:

1. Профилирование памяти: Используйте инструменты профилирования памяти, такие как go tool pprof, чтобы анализировать профили памяти вашей программы. Если программа заснула, вы можете увидеть, что память остается стабильной или медленно увеличивается, что может указывать на то, что она не активна и заснула.

2. Профилирование CPU: Используйте инструменты профилирования CPU, такие как go tool pprof, чтобы анализировать профили CPU вашей программы. Если программа заснула, вы можете увидеть, что процессор не активен или показывает низкую загрузку.

3. Логирование: Добавьте логирование в критические части вашего кода, чтобы отслеживать, когда они выполняются. Если программа заснула, вы можете увидеть, что логи не обновляются или остаются на одном и том же значении.

4. Использование отладчика: Запустите вашу программу с использованием отладчика, такого как GDB или Delve, и установите точку останова в критических участках кода. Если программа заснула, вы можете увидеть, что выполнение останавливается на этой точке останова.

5. Мониторинг сетевых соединений: Если ваша программа выполняет сетевые операции, вы можете мониторить активность сетевых соединений, чтобы определить, находится ли программа в состоянии ожидания или в дедлоке. Например, вы можете использовать инструменты мониторинга сети, такие как Wireshark или tcpdump, для анализа сетевого трафика вашей программы.

6. Анализ стека вызовов: Используйте инструменты анализа стека вызовов, такие как go tool pprof или delve, чтобы анализировать текущее состояние стека вызовов вашей программы. Если программа заснула, вы можете увидеть, что стек вызовов застрял в определенной функции или блокировке.

Комбинирование этих подходов поможет вам определить, находится ли ваша программа в состоянии засыпания или дедлока.