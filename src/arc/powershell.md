# Выгрузка DT скриптом powershell

```powershell
PS G:\BSS> get-help .\BackUP.ps1
BackUP_v2.ps1
	[-url_rac] <UriBuilder>
	[-url_1c] <UriBuilder> 
	[[-reindex_1c] <bool>] 
	[[-restart_1c] <bool>] 
	[[-service_1c] <string>] 
	[<CommonParameters>]
```

- url_rac: адрес сервера RAS (default: tcp://127.0.0.1:1545/cluster)
- url_1c: адрес базы 1C	(default: tcp://login:password@127.0.0.1:1641/base_name)
- reindex_1c: Выполнять переиндексацию базы данных (default: $false)
- restart_1c: Перезагружать агента сервера 1С (default: $false)
  - service_1c: Наименование службы агента сервера 1С (default: 1c*)
