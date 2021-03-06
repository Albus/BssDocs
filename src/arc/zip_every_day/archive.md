# archive.cmd

создаёт архив, с выборкой файлов за определённый период

{{#include inc/download.md}}

## Параметры

{{#include ./../../inc/console_params_rules.md}}

- **-src** - источник данных (папка или файл) для архивации
  
- **-name** - имя файла архива (расширение не имеет значения, все равно будет zip)
  
    Описание периода выборки. Указывается в формате `YYYYMMDD` (`ГГГГММДД`). Файлы отбираются по дате создания.
  
    - **-tac** - начало периода выборки файлов, попадает в период выборки
      
    - **-tbc** - окончание периода выборки файлов, не попадает в период выборки
      
      Пример: `20211231` (31 декабря 2021 года).
      Для выборки файлов за 2020 год писать так `-tac20200101 -tbc20210101`

- *--y* - пропускать паузу перед началом архивации, скрипт показывает параметры процесса и спрашивает разрешение продолжить работу

## Пример
```dos,no_run,noplayground
archive.cmd ^
    -src c:\folder\SourceOfArch ^
    -name c:\folder\DestOfArch\the_file_name.zip ^
    -tac 20191201 -tab 20200101 --y
```
