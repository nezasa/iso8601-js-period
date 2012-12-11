# iso8601-js-period

Javascript library for parsing of ISO 8601 durations. Supported are durations of
the form P3Y6M4DT12H30M17S or PT1S or P1Y4DT1H3S etc.

Shared and maintained by [Nezasa](http://www.nezasa.com) | Published under [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0.html)

For documentation of ISO 8601, see

-   http://en.wikipedia.org/wiki/ISO_8601

-   http://www.iso.org/iso/catalogue_detail?csnumber=40874

## API

All methods of this library are published within the namespace
```nezasa.iso8601.period```. The following methods are currently available.

### Method ```Array[int] nezasa.iso8601.period.parse(String period)```

Takes a ISO 8601 formatted duration and returns an array with 6 elements, one
per unit. The order of the units, starting with the first element of the array,
is “year”, “month”, “day”, “hour”, “minute”, “second”.

Example:

-   “PT1S” =\> ```[0, 0, 0, 0, 0, 1]```

-   “P1Y4DT1H3S” =\> ```[1, 0, 4, 1, 0, 3]```

-   “P3Y6M4DT12H30M17S” =\> ```[3, 6, 4, 12, 30, 17]```

### Method ```int nezasa.iso8601.Period.parseToTotalSeconds(String period)```

Takes a ISO 8601 formatted duration and returns the total amount of seconds
represented by the duration.

### Method ```String nezasa.iso8601.Period.parseToString(String period, Array[String] unitNames, Array[String] unitNamesPlural)```

Takes a ISO 8601 formatted duration and returns a more natural representation of
the period. In order to handle different languages, the method takes two input
arrays two define the unit names in singular and plural, e.g., for English it
would be

-   ```['year', 'month', 'day', 'hour', 'minute', 'second']```

-   ```['years', 'months', 'days', 'hours', 'minutes', 'seconds']```

The English versions as shown above are the default in case nothing is defined
and thus hard-coded in the library.

## Sample code

Please see the unit tests (file: unittest.html).
