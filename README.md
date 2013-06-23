Datepicker
==========

The one and only datepicker with no dependencies.

How to
----------
* Include
```
<script src="datepicker.js"></script>
```
* Select
```
var elem = document.querySelector('#date');
```
* Apply
```
new Datepicker(elem);
```

Actually getting a date from datepicker
----------

Each time the date changes and when it first starts up, the `onDateChange` option will be called with the selected date as its first argument.

Pass it an options object as the second argument.

```javascript
/* Print the new date on the console */
new Datepicker(elem, {
  onDateChange: function (newDate) {
    console.log(newDate);
  }
});
```

More options
----------

Override names of months...

```javascript
/* Months in spanish */
new Datepicker(elem, {
  onDateChange: function (newDate) {
    console.log(newDate);
  }
  monthNames: ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Setiembre', 'Octubre', 'Noviembre', 'Diciembre']
})
```

...and names of days too.

```javascript
/* Months and days in spanish */
new Datepicker(elem, {
  onDateChange: function (newDate) {
    console.log(newDate);
  }
  monthNames: ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Setiembre', 'Octubre', 'Noviembre', 'Diciembre'],
  dayNames: ['Domingo', 'Lunes', 'Martes', 'Miercoles', 'Jueves', 'Viernes', 'Sabado']
})
```

Contributing
-----------

Seriously? Thank you!
