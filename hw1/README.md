Решение соревнования https://www.kaggle.com/c/made-thousand-facial-landmarks

1) Взял предтренированный resnet18, картинки размера 256, несколько аугментаций (brightness, contrast, channel_shuffle, to_gray, rgb_shift, coaerse_dropout), разбил на 5 фолдов
2) Заморозил все слои, кроме последнего
3) Обучил 1 эпоху с MSE_loss, 1 эпоху с L1_loss с оптимизатором Adam
4) Разморозил слои
5) Повторил п.3, но по 3 эпохи
6) Обучил еще 20 эпох с оптимизатором AdamW, косинусным отжигом и MSE_loss или L1_loss (2 разные нейронки)
7) Усреднил предсказания для 2 моделей для 5 фолдов
