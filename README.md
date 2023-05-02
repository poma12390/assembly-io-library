# Input/Output library in assembly
---
Лабораторная работа: библиотека ввода-вывода на Assembler



Скрипт `test.py` будет генерировать исполняемый файл с тестом для каждой функции, вы можете отладить его; также см. Appendix A в "Low-level programming: C, assembly and program execution".
 
# Список распространённых ошибок

- Для строки размером `n` байт необходимы `n+1` байт из-за нуль-терминатора.
- Метки функций должны быть глобальными, остальные &mdash; локальными.
- Регистры не хранят ноль "по умолчанию".
- Если вы используете callee-saved регистры, вы должны сохранить их значения.
- Если вы используете caller-saved регистры, вы должны сохранить их значения перед `call` и затем восстанавливать.
- Не используйте буферы в секции `.data`. Вместо этого аллоцируйте место в стеке, уменьшая значение `rsp`.
- Функции принимают аргументы в `rdi`, `rsi`, `rdx`, `rcx`, `r8` и `r9`.
- Не выводите числа символ за символом. Сформируйте строку в памяти и вызовите `print_string`.
- Проверьте, что `parse_int` и `parse_uint` корректно устанавливают `rdx` (очень важно для следующего задания)
- Проверьте, что функции `parse_int`, `parse_uint` и `read_word` правильно работают когда ввод завершается с помощью `Ctrl-D`.

Код решения занимает порядка 250 строк.

