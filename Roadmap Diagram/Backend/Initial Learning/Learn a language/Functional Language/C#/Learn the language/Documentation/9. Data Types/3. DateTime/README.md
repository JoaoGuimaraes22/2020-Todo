# DateTime

## Overview

- The DateTime struct is used to work with dates and times;
- To create a DateTime object, do:
  - `DateTime dt = new DateTime(); // assigns default value 01/01/0001 00:00:00`;
- Use different constructors of the DateTime struct to assign an initial value to a DateTime object:

```c#
//assigns default value 01/01/0001 00:00:00
DateTime dt1 = new DateTime();

//assigns year, month, day
DateTime dt2 = new DateTime(2015, 12, 31);

//assigns year, month, day, hour, min, seconds
DateTime dt3 = new DateTime(2015, 12, 31, 5, 10, 20);

//assigns year, month, day, hour, min, seconds, UTC timezone
DateTime dt4 = new DateTime(2015, 12, 31, 5, 10, 20, DateTimeKind.Utc);
```

## Ticks

- Ticks is a date and time expressed in the number of 100-nanosecond intervals that have elapsed since January 1, 0001, at 00:00:00.000 in the Gregorian calendar;
- Example:

```c#
DateTime dt = new DateTime(636370000000000000);
DateTime.MinValue.Ticks;  //min value of ticks
DateTime.MaxValue.Ticks; // max value of ticks
```

## DateTime Static Fields

- The DateTime struct includes static fields, properties, and methods;
- Example:

```c#
DateTime currentDateTime = DateTime.Now;  //returns current date and time
DateTime todaysDate = DateTime.Today; // returns today's date
DateTime currentDateTimeUTC = DateTime.UtcNow;// returns current UTC date and time

DateTime maxDateTimeValue = DateTime.MaxValue; // returns max value of DateTime
DateTime minDateTimeValue = DateTime.MinValue; // returns min value of DateTime
```

## TimeSpan

- TimeSpan is a struct that is used to represent time in days, hour, minutes, seconds, and milliseconds;
- Example:

```
DateTime dt = new DateTime(2015, 12, 31);

TimeSpan ts = new TimeSpan(25,20,55);

DateTime newDate = dt.Add(ts);

Console.WriteLine(newDate);//1/1/2016 1:20:55 AM
```

- Subtraction of two dates results in TimeSpan;

## Operators

- The DateTime struct overloads +, -, ==, !=, >, <, <=, >= operators to ease out addition, subtraction, and comparison of dates;
- Example:

```c#
DateTime dt1 = new DateTime(2015, 12, 20);
DateTime dt2 = new DateTime(2016, 12, 31, 5, 10, 20);
TimeSpan time = new TimeSpan(10, 5, 25, 50);

Console.WriteLine(dt2 + time); // 1/10/2017 10:36:10 AM
Console.WriteLine(dt2 - dt1); //377.05:10:20
Console.WriteLine(dt1 == dt2); //False
Console.WriteLine(dt1 != dt2); //True
Console.WriteLine(dt1 > dt2); //False
Console.WriteLine(dt1 < dt2); //True
Console.WriteLine(dt1 >= dt2); //False
Console.WriteLine(dt1 <= dt2);//True
```

## Convert DateTime to String

- The DateTime struct includes the following methods to convert a date and time to string:
  - ToString:
    - Converts a DateTime value to a string in the specified format of the current culture;
  - ToShortDateString:
    - Converts a DateTime value to a short date string (M/d/yyyy pattern) in the current culture;
  - ToShortTimeString:
    - Converts a DateTime value to a short time string (h:mm:ss pattern) in the current culture;
  - ToLongDateString:
    - Converts a DateTime value to a long date string (dddd, MMMM d, yyyy pattern) in the current culture;
  - ToLongTimeString:
    - Converts a DateTime value to a long time string (h:mm:ss tt pattern) in the current culture;

## Convert String to DateTime

- A valid date and time string can be converted to a DateTime object using Parse(), ParseExact(), TryParse() and TryParseExact() methods;
- Example:

```c#
var str = "5/12/2020";
DateTime dt;

var isValidDate = DateTime.TryParse(str, out dt);

if(isValidDate)
    Console.WriteLine(dt);
else
    Console.WriteLine($"{str} is not a valid date string");
```

**Link:**

- <https://www.tutorialsteacher.com/csharp/csharp-datetime> ;
