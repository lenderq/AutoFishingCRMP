# Auto Fish Bot

## Описание проекта

Auto Fish Bot — скрипт автоматизации рыбалки в играх. Использует шаблонное сопоставление изображений (OpenCV TM_CCOEFF_NORMED) для распознавания ключей (S, SHIFT, V, W, D, CTRL, C, SPACE), рыб (RedFish/WhiteFish) и экранов. Автоклик pyautogui/keyboard, коррекция координат bbox, GUI tkinter full-screen.

## Ключевые возможности

- Распознавание шаблонов с threshold=0.8 (ключи/рыбы/OVER-экран)
- Авто-действия: press/press-and-release по найденным объектам
- Коррекция размеров bbox (fish1/2, key1/2 коэффициенты)
- Захват экрана PIL+OpenCV (grayscale), отображение в окнах
- Логика: процессинг рыбы/ключей, проверка OVER -> esc/t/fish/enter
- Полноэкранный overlay tkinter (screen width/height)


## Технологический стек

| Компонент | Библиотеки / Инструменты |
| :-- | :-- |
| Computer Vision | OpenCV (matchTemplate), NumPy |
| Автоматизация | PyAutoGUI (press), Keyboard |
| Захват экрана | PIL ImageGrab |
| GUI | Tkinter (full-screen overlay) |
| Utils | Time, cv2.imshow/waitKey |

## Установка и запуск

1. **Клонирование репозитория**:

```
git clone https://github.com/lenderq/AutoFishingCRMP.git
cd auto-fish-bot
```

2. **Установка зависимостей**:

```
pip install opencv-python pyautogui pillow keyboard numpy
```

3. **Настройка**:
    - Поместите шаблоны в `assets/` (S.png, RedFish1.png и т.д.)
    - Отрегулируйте bbox: fish (956,1271,1616,1324), keys/fish области
    - Коэффициенты: correct_width_fish1=2.0966 и др.
4. **Запуск**:

```
python main.py
```

Нажмите 'q' для выхода (cv2.waitKey).
5. **Тестирование**:
Запустите в игре с рыбалкой, бот найдет/кликнет автоматически.

## Использование

- **process_key_templates**: Ключи клавиатуры
- **process_fish_templates**: Рыбы (red/white)
- **OVER check**: Авто-submit (esc/t/fish/enter)
- Показ: cv2.imshow (Fish Capture, Key Capture, Over Check)

Проект демонстрирует CV в геймдеве/автоматизации — полезно для ботов, распознавания UI в играх.
