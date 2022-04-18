1. Сделать папку dir_1  
    `mkdir dir_1`  

2. Зайти в папку dir_1  
    `cd dir_1`  

3. Создать папку inner_dir_1  
    `mkdir inner_dir_1`  

4. Посмотреть где ты находишься  
    `pwd`  
    `/d/Documents/YandexDisk/QA/Linux/HW_2/dir_1`  

5. Находясь в папке dir_1 создать пустой текстовый файл tf_1.txt  
    `touch tf_1.txt`  

6. Находясь в папке dir_1 через команду cat создать текстовый файл tf_2.txt со следующими строками:
    - the first 1
    - the second 2
    - the third 3  
        `cat > tf_2.txt`  
        ```
        the first 1
        the second 2
        the third 3
        ```  
        Enter  
        Ctrl + `d`  

7. Зайти в папку inner_dir_1  
    `cd inner_dir_1/`  

8. Через cat сделать текстовый файл tf_3.txt  c любыми строками  
    `cat > tf_3.txt`  
    ```
    1. any string
    2. another string
    3. completely different string
    ```  
    Enter  
    Ctrl + `d`   

9. Через cat добавить в текстовый файл tf_3.txt строку “the second 2”  
    `cat >> tf_3.txt`  
    `the second 2` Enter  
    Ctrl + `d`  

10. Через cat добавить в текстовый файл tf_3.txt строку “the sec 2”  
    `cat >> tf_3.txt`  
    `the sec 2` Enter  
    Ctrl + `d`  

11. Через cat добавить в текстовый файл tf_2.txt строку “the sec 3”  
    `cat >> ../tf_2.txt`  
    `the sec 3` Enter  
    Ctrl + `d`  

12. Через cat добавить в текстовый файл tf_3.txt строку “the SeCoNd 2”  
    `cat >> tf_3.txt`  
    `the SeCoNd 2` Enter  
    Ctrl + `d`  
    
13. Через cat добавить в текстовый файл tf_2.txt строку “the seConD 2”  
    `cat >> ../tf_2.txt`  
    `the SeCoNd 2` Enter  
    Ctrl + `d`  

14. Сделать текстовый файл tf_4.txt в котором будет 15 строк.  
    `vim tf_4.txt`    
    `:set number` Enter  
    `i` `string to copy`  
    Esc  
    `yy14p` Enter  
    `:wq` Enter    

15. Сделать текстовый файл tF_5.txt в котором будет 13 строк.  
    `vim tF_5.txt`  
    `:set number` Enter  
    `i` `string to copy one more time`  
    Esc  
    `yy12p` Enter  
    `:wq` Enter  

16. Вывести список всех файлов в папке.  
    `ls -la | grep ^-`   

17. Выйти из папки inner_dir_1  
    `cd..`  

18. Вывести содержимое файла tf_3.txt в терминал.  
    `cat inner_dir_1/tf_3.txt`  
    ```
    1. any string
    2. another string
    3. completely different string
    the second 2
    the sec 2
    the SeCoNd 2 
    ```

19. Найти путь к файлу tf_4.txt  
    `find -name tf_4.txt -exec readlink -f '{}' ';'`  
    `/d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/inner_dir_1/tf_4.txt`  

20. Отчистить файл tf_4.txt от содержимого без удаления самого файла.  
    `:> dir_1/inner_dir_1/tf_4.txt`  

21. Найти путь к файлам у которых есть  “tf” в названии.  
    `find -name '*tf*' -exec readlink -f '{}' ';'`  
    ```
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/inner_dir_1/tf_3.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/inner_dir_1/tf_4.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/tf_1.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/tf_2.txt
    ```  
22. Найти путь к файлам у которых есть  “tf” в названии и буквы в любом регистре.   
    `find -iname '*tf*' -exec readlink -f '{}' ';'`
    ```
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/inner_dir_1/tf_3.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/inner_dir_1/tf_4.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/inner_dir_1/tF_5.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/tf_1.txt
    /d/Documents/YandexDisk/QA/Linux/HW_2/dir_1/tf_2.txt
    ```
23. Найти строки в файлах где есть комбинация букв “sec” в текущей папке   
    `grep "sec" ./*`    
    ```
    grep: ./inner_dir_1: Is a directory
    ./tf_2.txt:the second 2
    ./tf_2.txt:the sec 3
    ```
 24. Найти строки в файлах где есть комбинация букв “sec” в любом регистре в текущей папке  
    `grep -i "sec" ./*`  
        ```
        grep: ./inner_dir_1: Is a directory
        ./tf_2.txt:the second 2
        ./tf_2.txt:the sec 3
        ./tf_2.txt:the SeCoNd 2
        ```
25. Найти строки в файлах где есть только комбинация букв “sec” в текущей папке  
    `grep -w "sec" ./*`  
    ```
    grep: ./inner_dir_1: Is a directory
    ./tf_2.txt:the sec 3
    ```  

26. Найти строки в файлах где есть только комбинация букв “sec” в любом регистре в текущей папке    
    `grep -wi "sec" ./*`  
    ```
    grep: ./inner_dir_1: Is a directory
    ./tf_2.txt:the sec 3
    ```  

27. Найти строки в файлах где есть комбинация букв “second” в текущей папке  
    `grep "second" ./*`  
    ```
    grep: ./inner_dir_1: Is a directory
    ./tf_2.txt:the second 2
    ```  

28. Найти строки в файлах где есть комбинация букв “second” в любом регистре в текущей папке  
    `grep -i "second" ./*`
    ```
    grep: ./inner_dir_1: Is a directory
    ./tf_2.txt:the second 2
    ./tf_2.txt:the SeCoNd 2
    ```  
29. Найти строки в файлах где есть комбинация букв “second” во всех папках ниже уровнем  
    `grep -r "second"`
    ```
    inner_dir_1/tf_3.txt:the second 2
    tf_2.txt:the second 2
    ```
    
30. Найти только путь и название файла в строках которых есть комбинация букв “second” в текущей папке  
    `grep -l "second" ./*`
    ```
    grep: ./inner_dir_1: Is a directory
    ./tf_2.txt
    ```
31. Найти все строки во всех файлах где нет комбинации “second”  
    `grep -rv "second"`
    ```
    inner_dir_1/tf_3.txt:1. any string
    inner_dir_1/tf_3.txt:2. another string
    inner_dir_1/tf_3.txt:3. completely different string
    inner_dir_1/tf_3.txt:the sec 2
    inner_dir_1/tf_3.txt:the SeCoNd 2
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tf_4.txt:string to copy
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    inner_dir_1/tF_5.txt:string to copy one more time
    tf_2.txt:the first 1
    tf_2.txt:the third 3
    tf_2.txt:the sec 3
    tf_2.txt:the SeCoNd 2
    ```
32. Найти только название и путь к файлам где нет комбинации “second”  
    `grep -rvl "second"`
    ```
    inner_dir_1/tf_3.txt
    inner_dir_1/tf_4.txt
    inner_dir_1/tF_5.txt
    tf_2.txt
    ```
33. Вывести в терминал 4 последних строк любого текстового файла  
    `tail -n4 tf_2.txt`  
    ```
    the second 2
    the third 3
    the sec 3
    the SeCoNd 2
    ```
34. Вывести в терминал 4 первые строки любого текстового файла.  
    `head -n4 tf_2.txt`  
    ```
    the first 1
    the second 2
    the third 3
    the sec 3
    ```  

35. Команда в одну строку. Создать папку и создать текстовый файл с содержиммым.  
    `mkdir inner_dir_2 | echo some content > tf_6.txt`  
36. Команда в одну строку. Переместить в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”  
    ```
    mv `find ./* -maxdepth 0 -type f -exec grep -l "sec" '{}' ';'` inner_dir_2
    ```

37. Команда в одну строку. Скопировать в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”  
    ```
    cp `find ./* -type f -exec grep -l "sec" '{}' ';'` inner_dir_2
    ```
38. Команда в одну строку. Найти все строки c “sec” во всех текстовых файлах, скопировать и вставить эти строки в один новый созданный текстовый файл.  
    ```
    echo `find ./* -type f -exec grep "sec" '{}' ';'` > tf_7.txt
    ```
39. Команда в одну строку. Удалить текстовые файлы у которых в содержимом есть слово “sec”  
    ```
    rm `find ./* -type f -exec grep -l "sec" '{}' ';'`
    ```
40. Просто вывести в терминал строку “Good job!!”
    `echo "Good job!!"`