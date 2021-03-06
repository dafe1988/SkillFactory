======================================================================
# Проект 2. Определение параметров модели,
предсказывающей результы госэкзамена по математике
======================================================================

## Цели и задачи проекта: 
    * провести разведывательный анализ данных и определить параметры будущей модели;
    * проверить качество данных и очистить их, если это необходимо;
    * оценить распределения признаков и провести корреляционный анализ;
    * сформулировать выводы относительно качества данных и тех переменных, 
    которые буду использовать в дальнейшем построении модели
    * оформить проект в соответствии с критериями оценки и выложить на GitHub
    
=======================================================================    
## Краткая информация о данных

**В датасете представлены следующие данные:

    * school — аббревиатура школы, в которой учится ученик
    * sex — пол ученика ('F' - женский, 'M' - мужской)
    * age — возраст ученика (от 15 до 22)
    * 4 address — тип адреса ученика ('U' - городской, 'R' - за городом)
    * 5 famsize — размер семьи('LE3' <= 3, 'GT3' >3)
    * 6 Pstatus — статус совместного жилья родителей ('T' - живут вместе 'A' - раздельно)
    * 7 Medu — образование матери (0 - нет, 1 - 4 класса, 2 - 5-9 классы, 
    3 - среднее специальное или 11 классов, 4 - высшее)
    * 8 Fedu — образование отца (0 - нет, 1 - 4 класса, 2 - 5-9 классы, 3 - среднее 
    специальное или 11 классов, 4 - высшее)
    * 9 Mjob — работа матери ('teacher' - учитель, 'health' - сфера здравоохранения, 
    'services' - гос служба, 'at_home' - не работает, 'other' - другое)
    * 10 Fjob — работа отца ('teacher' - учитель, 'health' - сфера здравоохранения, 
    'services' - гос служба, 'at_home' - не работает, 'other' - другое)
    * 11 reason — причина выбора школы ('home' - близость к дому, 'reputation' - репутация школы, 
    'course' - образовательная программа, 'other' - другое)
    * 12 guardian — опекун ('mother' - мать, 'father' - отец, 'other' - другое)
    * 13 traveltime — время в пути до школы (1 - <15 мин., 2 - 15-30 мин., 3 - 30-60 мин., 4 - >60 мин.)
    * 14 studytime — время на учёбу помимо школы в неделю (1 - <2 часов, 2 - 2-5 часов, 
    3 - 5-10 часов, 4 - >10 часов)
    * 15 failures — количество внеучебных неудач (n, если 1<=n<=3, иначе 0)
    * 16 schoolsup — дополнительная образовательная поддержка (yes или no)
    * 17 famsup — семейная образовательная поддержка (yes или no)
    * 18 paid — дополнительные платные занятия по математике (yes или no)
    * 19 activities — дополнительные внеучебные занятия (yes или no)
    * 20 nursery — посещал детский сад (yes или no)
    * 21 higher — хочет получить высшее образование (yes или no)
    * 22 internet — наличие интернета дома (yes или no)
    * 23 romantic — в романтических отношениях (yes или no)
    * 24 famrel — семейные отношения (от 1 - очень плохо до 5 - очень хорошо)
    * 25 freetime — свободное время после школы (от 1 - очень мало до 5 - очень мого)
    * 26 goout — проведение времени с друзьями (от 1 - очень мало до 5 - очень много)
    * 27 health — текущее состояние здоровья (от 1 - очень плохо до 5 - очень хорошо)
    * 28 absences — количество пропущенных занятий
    * 29 score — баллы по госэкзамену по математике
=======================================================================
## Этапы работы над проектом:
    * первичный отсмотр данных, определение типов данных в колонках
    * отсмотр каждого столбца по отдельности
    * проверка данных на пустые значения 
    * проверка данных на наличие выбросов
    * проверка данных на дублированные/полностью скоррелированные значения
    * отбор, пригодные для дальнейшего построения модели
    * формулирование выводы 
    * проверка на соответсвие autopep8
    * выложить проект для оценки ментором на github
=======================================================================
## Выводы

**Итак, в результате EDA для анализа влияния условий жизни школьников 
на успеваемость по математике были получены следующие выводы:**

    1. Нет пустых значений только в колонках 'school', 'sex', 'age'
    2. В остальных колонках пропусков до 10%, в строковых типах мы заполнили пропуски значением None, 
    в количественных переменных заполнили пропуски медианным значением, в колонке failures заполнили 
    пропуски нулями в соответсвии с условием
    3. Выбросы найдены в столбцах Fedu, famrel, absences, данные достаточно чистые
    4. Самые важные параметры, которые предлагается использовать в дальнейшем для построения модели:          
   **параметры с положительной корреляцией**
   
    * absences -  возможно, более умные студенты позволяют себе чаще пропускать уроки? 
    * freetime - чем больше свободного времени, тем лучше баллы на экзамене. Очевидно, что наличие 
    свободного времени способствует нормальному психологическому состоянию и позволяет быть успешнее
    * famrel - чем лучше отношения в семье, тем успешнее студент. Тут логично)
    * studytime - чем больше дополнительного времени на учебу, тем лучше результат
    * Fedu - образование отца. Логично, что у умных родителей и дети умнее
    * Medu - образование матери. Интересно, что тут коэффициент корреляции гораздо выше чем у отца. 
    Мама с хорошим образованием, видимо, отлично мотивирует своего ребенка    
   **параметры с отрицательной корреляцией:**
    
    * health - похоже, что более физически здоровые студенты занимаются чем то кроме математики
    * goout - чем больше времени студент проводит с друзьями, тем меньше остается на учебу
    * failures - тут довольно сильная корреляция, количество внеучебных неудач довольно сильно снижает 
    успеваемость
    * traveltime - чем больше времени студент тратит на путь до школы, тем, видимо, у него меньше 
    потом мотивации учиться
    * age - можно предположить, что чем старше студент, тем более сложный у него учебный материал 
    и естесственно, больше студентов начинают отставать

=======================================================================
## Ответы на вопросы саморефлексии:

    1.  Особенно довольна визуализациями, интересно было разобраться с разными инструментами и приемами 
    библиотеки plotly
    
    2. Что не получилось сделать мне пока сложно оценить, поскольку это мой первый проект с EDA и область 
    неизвестного пока весьма обширна
    
    3. Интересного и полезного было все) как минимум, потому что это по сути исследование, принятие решения 
    каким методом где воспользоваться, практическая проверка изученных инструментов
    
    4. Главным результатом, думаю, являются более цельное восприятие структуры работы с EDA, с данными, 
    принятие решения каким методом 
    обработать пропуски и как это может отразиться на результате
    
======================================================================    
    
### USAGE: Запустите файл /SkillFactory/module_2/Project_2_EDA/EDA_stud_math.ipynb через Jupiter Notebook
