Плагин jquery.generate-url
==============================
Данный плагин позволяет создать ЧПУ из содержимого одного поля и сохранить его в другое.

Параметры
---------
<table>
    <tr>
        <th>Параметр</th>
        <th>Тип</th>
        <th>По умолчанию</th>
        <th>Описание</th>
    </tr>
    <tr>
        <td>urlField *</td>
        <td>jQuery object | jQuery selector</td>
        <td>null</td>
        <td>Поле, в которое будет помещаться созданный ЧПУ.</td>
    </tr>
    <tr>
        <td>emptyOnly</td>
        <td>boolean</td>
        <td>true</td>
        <td>По умолчанию плагин активируется только если поле хранения ЧПУ при инициализации пустое. Это позволяет генерировать ссылку при создании материала, но пердотвращает её изменение при редактировании. Установка данного параметра в false активирует плагин в любом случае.</td>
    </tr>
</table>

События
-------
<table>
    <tr>
        <th>Событие</th>
        <th>Описание</th>
    </tr>
    <tr>
        <td>urlchanged</td>
        <td>Событие срабатывает после изменения значения поля хранения ЧПУ.</td>
    </tr>
</table>

Свойства событий
----------------
<table>
    <tr>
        <th>Свойство</th>
        <th>Тип</th>
        <th>Событие</th>
        <th>Описание</th>
    </tr>
    <tr>
        <td>url</td>
        <td>string</td>
        <td>urlchanged</td>
        <td>Новый ЧПУ.</td>
    </tr>
    <tr>
        <td>sourceField</td>
        <td>jQuery object</td>
        <td>urlchanged</td>
        <td>Исходное поле.</td>
    </tr>
    <tr>
        <td>urlField</td>
        <td>jQuery object</td>
        <td>urlchanged</td>
        <td>Поле хранения ЧПУ.</td>
    </tr>
</table>

Пример использования
--------------------

    $('#name')
		.generateUrl({
			urlField: '#url',
			emptyOnly: false
		})
		.on('urlchanged', function(event) {
			console.log('URL was changed');
		})