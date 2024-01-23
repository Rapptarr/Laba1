# Разработка системы рекомендаций для онлайн-платформ на основе данных о поведении пользователей. (Лабораторная №1)
В этом проекте на языке Python я реализовал рекомендательную систему для онлайн-сервиса. В качестве самого сервиса был взял онлайн-кинотеатр. Типом рекомендательной системы в моей работы была коллаборативная система (collaborative filtering). Она основывается на сопоставлении пользователей и товаров (в нашем случае на сопоставлении названий фильмов и соответстующих оценок, которые им поставили зрители). Математически будем работать с матрицами предпочтений (user-item matrix), а непосредственно сама "близость" фильмов высчитывается косинусным сходством.

## Требования.
- Python 3.x
- Google Colab или Jupyter Notebook

## Как работает программа :
1. **Загрузка данных**:
   * Подключаем необходимые библиотеки и набор данных о рейтинге фильмов MovieLens Latest Datasets.
   * Датасет включает в себя названия фильмов (файл movies.csv) и оценки, которые фильмам ставили зрители (файл rating.csv).
   * Файлы прикреплены к работе.

2. **Предварительная обработка данных**:
   * Удаляем ненужные столбцы из обоих файлов.
   * С использованием функции pivot создадим таблицу, в которой по горизонтали представлены фильмы, по вертикали - пользователи, а значениями являются оценки.
   * Пропуски NaN замененяем на нули.
   * С помощью фильтров удаляем ненужные оценки и фильмы.

4. **Преобразование данных**:
   * Используя библиотеку Scipy, преобразуем разреженную матрица в формат csr (compressed sparse row).

5. **Обучение модели**:
   * Для поиска ближайших соседей был использован класс NearestNeighbors с косинусной метрикой.

6. **Поиск и рекомендации**:
   * Для получения рекомендаций был выбран фильм 'Matrix'.
   * Находим индексы и расстояния фильмов, схожих с выбранным фильмом.
   * С помощью цикла был создан список, содержащий название фильма и расстояние до него.
  
## Colab
| Colab                                                                                                                                                                          | Info               |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------ |
| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1gTiJrHKE-2EZPbe9UwMgZYrfEUsGsNkX?usp=sharing) | Laba1 |

## Результат.
В конечном итоге мы получаем список с наиболее близкими фильмам по предпочтениям зрителей.
1. **Фильмы**
   ![xxxx]([https://sun21-2.userapi.com/impg/s1eypwgZ9mPygLHkh0o1AqDRcfGkxW2-RvOrKQ/W0x-9ilUQkQ.jpg?size=570x454&quality=96&sign=33bfa869934f3e8ef4f0eb5ffc6652c6&type=album](https://sun9-1.userapi.com/impg/AilDVz-BS8dfwHLo6R8KhFHahQ5xyzRq2ZCEUA/c0lTbK-Ylt4.jpg?size=442x352&quality=96&sign=763446c626c1450c646b8aa4f8097ce2&type=album)https://sun9-1.userapi.com/impg/AilDVz-BS8dfwHLo6R8KhFHahQ5xyzRq2ZCEUA/c0lTbK-Ylt4.jpg?size=442x352&quality=96&sign=763446c626c1450c646b8aa4f8097ce2&type=album)
  

