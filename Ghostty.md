## Базовые возможности Ghostty:

Ghostty создан для работы без мышки. Вот главные комбинации:

**Вкладки (Tabs):**
    - `Ctrl + Shift + T` — Открыть новую вкладку.
    - `Ctrl + Shift + W` — Закрыть текущую вкладку (или сплит).
    - `Ctrl + PageDown / PageUp` — Переключение между вкладками.
**Разделение экрана (Splits - Мультиплексинг):** Это киллер-фича. Тебе не нужны сторонние программы.
    - `Ctrl + Shift + Enter` — Разделить экран по вертикали
    - `Ctrl + Shift + D` — Разделить экран по горизонтали (один над другим).
    - `Ctrl + Shift + Стрелки` — Перемещение фокуса между разделенными окнами.

## Текущий тюнинг Ghostty:

Конфиг находится: `nano ~/.config/ghostty/config`:
```
# Тема оформления (в Ghostty встроены сотни тем!)
theme = "catppuccin-mocha"

# Настройка шрифта (укажи свой, если скачал Nerd Font)
font-family = "JetBrainsMono Nerd Font"
font-size = 12

# Отступы от краев окна (чтобы текст не прилипал к рамке)
window-padding-x = 10
window-padding-y = 10

# Скрываем стандартную рамку окна Linux (если поддерживается WSLg)
window-decoration = false

# Стиль курсора
cursor-style = block
cursor-style-blink = true
```
