# v1/disk

### GET

Данные о Диске пользователя

API возвращает общую информацию о Диске пользователя: доступный объем, адреса системных папок и т. п.

<u>api</u>   

```
API.v1.disk.get()
```   

# v1/disk/operations/:operation_id

### GET

<u>path</u>   

* operation_id {string}    

<u>api</u>   

```
API.v1.disk.operations.:operation_id.getByOperationId(
    operation_id: StringType,
)
```   

# v1/disk/public/resources

### GET

Метаинформация о публичном ресурсе

Зная ключ опубликованного ресурса или публичную ссылку на него, можно запросить метаинформацию об этом ресурсе (свойства файла или свойства и содержимое папки).

<u>query</u>   

* public_key {string}    
* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* sort {string}    
* limit {int32}    
* preview_size {string}    
* preview_crop {boolean}    
* offset {int32}    

<u>api</u>   

```
API.v1.disk.public.resources.get(
    public_key: StringType,
    path: StringType,
    sort: StringType,
    limit: Int32Type,
    preview_size: StringType,
    preview_crop: BooleanType,
    offset: Int32Type,
)
```   

# v1/disk/public/resources/download

### GET

Скачивание публичного файла или папки

Ресурс, опубликованный на Диске, можно скачать, зная его ключ или публичную ссылку на него. Также этой операцией можно скачивать отдельные файлы из публичных папок.

<u>query</u>   

* public_key {string}    
* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   

<u>api</u>   

```
API.v1.disk.public.resources.download.get(
    public_key: StringType,
    path: StringType,
)
```   

### POST

Сохранение публичного файла в «Загрузки»

Файл, опубликованный на Диске, можно скопировать в папку «Загрузки» на Диске пользователя. Для этого нужно знать ключ файла или публичную ссылку на него. Если вы знаете ключ публичной папки, вы также можете копировать отдельные файлы из нее.

<u>query</u>   

* public_key {string}    
* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* name {string}    

<u>api</u>   

```
API.v1.disk.public.resources.download.post(
    public_key: StringType,
    path: StringType,
    name: StringType,
)
```   

# v1/disk/resources

### DELETE

Удаление файла или папки

Удалять файлы и папки на Диске пользователя можно, указывая путь к удаляемому ресурсу. Помните, что перемещение ресурсов в Корзину никак не влияет на доступное место на Диске. Чтобы освободить место, следует также удалять ресурсы из Корзины.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* permanently {boolean}    
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.delete(
    path: StringType,
    permanently: BooleanType,
    fields: StringType,
)
```   

### GET

Метаинформация о файле или папке

Запрашивать метаинформацию о файлах и папках можно, указав путь к соответствующему ресурсу на диске. Метаинформация включает в себя собственные свойства файлов и папок, а также свойства и содержимое вложенных папок.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* fields {string}    
* limit {int32}    
* offset {int32}    
* preview_crop {boolean}    
* preview_size {string}    
* sort {string}    

<u>api</u>   

```
API.v1.disk.resources.get(
    path: StringType,
    fields: StringType,
    limit: Int32Type,
    offset: Int32Type,
    preview_crop: BooleanType,
    preview_size: StringType,
    sort: StringType,
)
```   

### PATCH

Добавление метаинформации для ресурса

Для любого файла или папки, доступной на запись, можно задать дополнительные произвольные атрибуты. Эти атрибуты будут возвращаться в ответ на все запросы метаинформации о ресурсах (список всех файлов, последние загруженные и т. д.).

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.patch(
    path: StringType,
    fields: StringType,
)
```   

### PUT

Создание папки

Создавать папки на Диске можно, указывая требуемый путь к новой папке.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.put(
    path: StringType,
    fields: StringType,
)
```   

# v1/disk/resources/copy

### POST

Копирование файла или папки

Копировать файлы и папки на Диске пользователя можно, указывая путь к ресурсу и требуемый путь к его копии.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* overwrite {boolean}    
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.copy.post(
    path: StringType,
    path: StringType,
    overwrite: BooleanType,
    fields: StringType,
)
```   

# v1/disk/resources/download

### GET

Скачивание файла с Диска

Чтобы получить URL для непосредственной загрузки файла, необходимо передать API путь на Диске, по которому загруженный файл должен быть доступен.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.download.get(
    path: StringType,
    fields: StringType,
)
```   

# v1/disk/resources/files

### GET

Плоский список всех файлов

API возвращает плоский список всех файлов на Диске в алфавитном порядке. Плоский список не учитывает структуру каталогов, поэтому в нем удобно искать файлы определенного типа, разбросанные по разным папкам.

<u>query</u>   

* limit {int32}    
* media_type {string}    
* offset {int32}    
* fields {string}    
* preview_size {string}    
* preview_crop {boolean}    

<u>api</u>   

```
API.v1.disk.resources.files.get(
    limit: Int32Type,
    media_type: StringType,
    offset: Int32Type,
    fields: StringType,
    preview_size: StringType,
    preview_crop: BooleanType,
)
```   

# v1/disk/resources/last-uploaded

### GET

Последние загруженные файлы

API возвращает список последних файлов, загруженных на Диск. Список можно фильтровать по типу файла (аудио, видео, изображение и т. д.). Диск определяет тип каждого файла при загрузке.

<u>query</u>   

* limit {int32}    
* media_type {string}    
* fields {string}    
* preview_size {string}    
* preview_crop {boolean}    

<u>api</u>   

```
API.v1.disk.resources.last-uploaded.get(
    limit: Int32Type,
    media_type: StringType,
    fields: StringType,
    preview_size: StringType,
    preview_crop: BooleanType,
)
```   

# v1/disk/resources/move

### POST

Перемещение файла или папки

Перемещать файлы и папки на Диске можно, указывая текущий путь к ресурсу и его новое положение.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* overwrite {boolean}    
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.move.post(
    path: StringType,
    path: StringType,
    overwrite: BooleanType,
    fields: StringType,
)
```   

# v1/disk/resources/public

### GET

Список опубликованных ресурсов

API возвращает список опубликованных ресурсов на Диске пользователя. Ресурсы в списке отсортированы от опубликованных позже к опубликованным раньше.

<u>query</u>   

* limit {int32}    
* offset {int32}    
* type {string}    
* fields {string}    
* preview_size {string}    

<u>api</u>   

```
API.v1.disk.resources.public.get(
    limit: Int32Type,
    offset: Int32Type,
    type: StringType,
    fields: StringType,
    preview_size: StringType,
)
```   

# v1/disk/resources/publish

### PUT

Публикация ресурса

Ресурс становится доступен по прямой ссылке. Опубликовать ресурс можно только с OAuth-токеном владельца файла.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   

<u>api</u>   

```
API.v1.disk.resources.publish.put(
    path: StringType,
)
```   

# v1/disk/resources/unpublish

### PUT

Закрытие доступа к ресурсу

Ресурс теряет атрибуты public_key и public_url, публичные ссылки на него перестают работать. Закрыть доступ к ресурсу можно только с OAuth-токеном владельца ресурса.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   

<u>api</u>   

```
API.v1.disk.resources.unpublish.put(
    path: StringType,
)
```   

# v1/disk/resources/upload

### GET

Запрос URL для загрузки

Сообщив API Диска желаемый путь для загружаемого файла, вы получаете URL для обращения к загрузчику файлов.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* overwrite {boolean}    
* fields {string}    

<u>api</u>   

```
API.v1.disk.resources.upload.get(
    path: StringType,
    overwrite: BooleanType,
    fields: StringType,
)
```   

### POST

Скачивание файла из интернета на Диск

Яндекс.Диск может скачать файл на Диск пользователя. Для этого следует передать в запросе URL файла и следить за ходом операции. Если при скачивании возникла ошибка, Диск не будет пытаться скачать файл еще раз.

<u>query</u>   

* url {string}    
* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* fields {string}    
* disable_redirects {boolean}    

<u>api</u>   

```
API.v1.disk.resources.upload.post(
    url: StringType,
    path: StringType,
    fields: StringType,
    disable_redirects: BooleanType,
)
```   

# v1/disk/trash/resources

### DELETE

Очистка Корзины

Файлы, перемещенные в Корзину, можно окончательно удалить. Корзина считается папкой на Диске, поэтому доступное на Диске место при этом увеличивается.

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   

<u>api</u>   

```
API.v1.disk.trash.resources.delete(
    path: StringType,
)
```   

# v1/disk/trash/resources/restore

### PUT

<u>query</u>   

* path {string} Путь к нужному ресурсу относительно корневого каталога Диска.   
* name {string}    
* overwrite {boolean}    

<u>api</u>   

```
API.v1.disk.trash.resources.restore.put(
    path: StringType,
    name: StringType,
    overwrite: BooleanType,
)
```   
