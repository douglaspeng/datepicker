Datepicker
==========

The one and only datepicker with no dependencies.

How to
----------

Standalone

```html
<div id="my-datepicker"></div>

<script src="datepicker.min.js"></script>
<script>
  var elem = document.querySelector('#my-datepicker');

  new Datepicker(elem, {
    onDateChanged: function (selectedDate) {
      console.log(selectedDate);
    }
  });

  elem.datepicker.incrementMonth();
</script>
```

With AngularJS

```html
<sexy-datepicker on-data-changed="dateChangedHandler"></sexy-datepicker>

<script src="angular-1.1.5.js"></script>
<script src="angular.datepicker.min.js"></script>
<script>
  angular.module('myApp', ['sexyDatepicker'])
    .controller('myController', function ($scope, $element) {
      $scope.dateChangedHandler = function (selectedDate) {
        console.log(selectedDate);
      };

      $element.find('sexy-datepicker').datepicker.incrementMonth();
    });
</script>
```

With jQuery:

```html
<div id="my-datepicker"></div>

<script src="jquery.js"></script>
<script src="jquery.datepicker.min.js"></script>
<script>
  $('#my-datepicker').datepicker({
    onDateChanged: function (selectedDate) {
      console.log(selectedDate);
    }
  });

  $('#my-datepicker').get(0).datepicker.incrementMonth();
</script>
```

Interacting with datepicker
----------

The following are not available on the jQuery plugin.

Going back and forth in months programatically.

```javascript
/* Create datepicker with current date set to today.
   July 1st. */
var datepicker = new Datepicker(...);

/* Select August 1st. */
datepicker.incrementMonth();

/* Change date to 2 months later. */
datepicker.incrementMonth(2);

/* Change it back to July 1st. */
datepicker.incrementMonth(-3);

/* Move to the next year. */
datepicker.incrementMonth(12);

/* Move back to the year selected before. */
datepicker.incrementMonth(-12);
```

Changing selected date.

```javascript
/* New datepicker with today's date. July 1st. */
var datepicker = new Datepicker(...);

/* Make it select my birthday. */
var myBirthday = new Date('6/22/2013');
datepicker.setSelectedDate(myBirthday);
```

Re-build datepicker.

```javascript
var datepicker = new Datepicker(...);
datepicker.build();
```

Remove datepicker completely.

```javascript
var datepicker = new Datepicker(...);
datepicker.destroy();
```

Actually getting a date from datepicker
----------

Each time the date changes and when it first starts up, the `onDateChanged` option will be called with the selected date as its first argument.

Pass it an options object as the second argument.

```javascript
/* Print the new date on the console */
new Datepicker(elem, {
  onDateChanged: function (newDate) {
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
  onDateChanged: function (newDate) {
    console.log(newDate);
  }
  monthNames: ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Setiembre', 'Octubre', 'Noviembre', 'Diciembre']
})
```

...and names of days too.

```javascript
/* Months and days in spanish */
new Datepicker(elem, {
  onDateChanged: function (newDate) {
    console.log(newDate);
  }
  monthNames: ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Setiembre', 'Octubre', 'Noviembre', 'Diciembre'],
  dayNames: ['Domingo', 'Lunes', 'Martes', 'Miercoles', 'Jueves', 'Viernes', 'Sabado']
})
```

When using the AngularJS directive:

```html
<!-- Add `month-names` and `day-names` attributes to element. -->
<sexy-datepicker month-names="months" day-names="days" on-date-changed="dateChangedHandler"></sexy-datepicker>
```

```javascript
angular.module('myApp', ['sexyDatepicker'])
  .controller('myController', function ($scope) {
    /* Create arrays with name on the $scope. */
    $scope.months = ['Enero', 'Febrero', 'Marzo', 'Abril', 'Mayo', 'Junio', 'Julio', 'Agosto', 'Setiembre', 'Octubre', 'Noviembre', 'Diciembre'];
    $scope.days = ['Domingo', 'Lunes', 'Martes', 'Miercoles', 'Jueves', 'Viernes', 'Sabado'];
  });
```

To-do
-----------
* Build with Grunt.
* Add tests.

Contributing
-----------

Seriously? Thank you!

Use it
-----------
Copyright (c) 2013 Federico Baña.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
