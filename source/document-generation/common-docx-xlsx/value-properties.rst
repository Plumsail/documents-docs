Value properties in DOCX, XLSX and PPTX templates
=================================================

You can access different methods and properties on tag values. For example, you can bring a string to the lowercase, get a day, month or year from a date, get a number of items in an array. 

Value properties work the same in DOCX, XLSX and PPTX templates.

Just use **dot** after tag value as in the example below:

.. list-table::
    :header-rows: 1

    *   - Template
        - Data
        - Result
    *   - .. code-block:: json
    
            {{stringVal.ToLower}}
            {{dateVal.Year}}
            {{arrayVal.Length}}

        - .. code-block:: json

            {                     
                "stringVal": "Jessica Adams",
                "dateVal": "2012-04-21T18:25:43-05:00",
                "arrayVal": [ 1, 2, 3, 4, 5],
            }         

        - .. code-block:: json
    
            jessica adams
            2012
            5

There are three possible types of values you can call properties on. You can find the list of properties for each of them below:

.. contents::
   :local:
   :depth: 1

String
------

:code:`Length` - gets the number of characters in the current String object.

:code:`ToLower` - returns a copy of this string converted to lowercase.

:code:`ToUpper` - returns a copy of this string converted to uppercase.

:code:`Trim` - removes all leading and trailing white-space characters from the current String object.

:code:`GetHashCode` - returns the hash code for this string.(Overrides Object.GetHashCode().)

.. _strings:

Date and time
-------------

:code:`Date` - the date component without time.	

:code:`Day` - the day of the month.

:code:`DayOfWeek` - the day of the week.

:code:`DayOfYear` - the day of the year.

:code:`Hour` - the hour component of the date.

:code:`Millisecond` - the milliseconds component of the date.

:code:`Minute` - the minute component of the date.

:code:`Month` - the month component of the date.

:code:`Second` - the seconds component of the date.

:code:`Ticks` - the number of ticks that represent the date and time.

:code:`TimeOfDay` - the time of day for this instance.

:code:`Year` - the year component of the date.

:code:`GetHashCode` - returns the hash code for this date.

:code:`ToLongDateString` - converts the value of the current DateTime object to its equivalent long date string representation.

:code:`ToLongTimeString` - converts the value of the current date and time object to its equivalent long time string representation.

:code:`ToOADate` - converts the value of this instance to the equivalent OLE Automation date.

:code:`ToShortDateString` - converts the value of the current date and time object to its equivalent short date string representation.

:code:`ToShortTimeString` - converts the value of the current date and time object to its equivalent short time string representation.

:code:`IsDaylightSavingTime` - indicates whether this instance of date and time is within the daylight saving time range for the current time zone.

:code:`ToFileTime` - converts the value of the current DateTime object to a Windows file time.

:code:`ToFileTimeUtc` - converts the value of the current DateTime object to a Windows file time.

Array
-----

:code:`Length` - gets the total number of elements in all the dimensions of the array.