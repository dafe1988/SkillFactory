 Программа угадывает случайно загаданное число, выводит среднее количество попыток за 1000 игр
 
 Цель - угадать число менее чем за 30 попыток в среднем 

Предложено 2 варианта алгоритма угадывания:

1.  game_core_v3 - перебираем случайные числа в интервале, 
    задаваемом от предсказанного числа меньше загаданного 
    до предсказанного числа больше загаданного. 
    
    Данный алгоритм угадывает число в среднем за 8 попыток
    
2.  game_core_v4 - также перебираем числа в интервале 
    от предсказанного числа меньше загаданного 
    до предсказанного числа больше загаданного, 
    но тут задаем функцию определения середины промежутка midpoit() 
    и следующее предсказанное число будет вдвое сокращать исследуемую область. 
    
    Данный алгоритм угадывает число в среднем за 6 попыток. 
    
    Также в этом алгоритме выведены промежуточные результаты всех попыток
    
    
USAGE: Запустите файл module_0/Project_0_GitHub_game_core-final.ipynb через Jupiter Notebook
