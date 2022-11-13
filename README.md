# Yandex-Cup-22
Recomender System for Yandex.Cup22

## A. Like prediction
Важной задачей музыкальных рекомендаций является поиск неизвестных пользователю треков, которые ему понравятся. В решении этой задачи важную роль играют модели, анализирующие явный фидбэк пользователя. Явным фидбэком мы считаем такие события как like или dislike, поставленный на трек. Такие действия как play и skip также используются в рекомендациях, но они дают меньше информации о предпочтениях пользователя. Кроме того, гораздо важнее найти трек, которому пользователь поставит лайк, чем трек, который пользователь просто послушает. В этой задаче от вас требуется по предыдущим лайкам предсказать следующий трек, которому пользователь поставит лайк.

## Формат ввода
Прдоставленные вам данные вы можете найти по ссылке  
В архиве `likes_data.zip` три файла:  
`train` - обучающий набор данных. Каждая строка - последовательность id треков, которые лайкнул один пользователь. Гарантируется, что лайки даны в той последовательности, в которой их ставил пользователь.  
`test` - набор тестовых данных. Имеет точно такой же формат, но в каждой строке не хватает последнего лайка, который надо предсказать.  
Тестовые данные разбита на `public` и `private`. Во время соревнования вы будет видеть результаты только на public данных. Финальный подсчет баллов в будет происходить на private данных.  
`track_artists.csv` - информация о исполнителях треков. Гарантируется, что у каждого трека есть ровно один исполнитель. Для треков, у которых фактически несколько исполнителей, мы оставили того, который считается основным исполнителем трека.  
Файл `baseline.py` содержит наивное решение. Обратите внимание, что это решение может выполняться больше одного часа.  
Файл `score.py` содержит код, который вы можете использовать, чтобы локально считать mrr для своего решения.  
Формат вывода  
В качестве решения необходимо отправить файл, в котором для каждого пользователя в отдельной строке будет не более 100 треков, разделенных пробелом.  
  
## Примечания  
В качестве метрики используется MRR@100  
  
## Решение  
В настоящем репозитории находится решение методом SVD Matrix Factorization.  
 - количество пользователей в тестовой выборке: ~290к   
 - размерность пространства после SVD: 15 000  
 - public score (MRR@100): 0.018490026190541704  
