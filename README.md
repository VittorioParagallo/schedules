# Schedules

A Dart-only package for managing recurring events.

## Features

Create a "Schedule" for recurring events. Then, determine if that event occurs on a given date.

Great for scheduling recurring events, such as:
  * Paydays
  * Bill due dates
  * Birthdays
  * Anniversaries
  * Holidays
  * Etc.

## Getting started

As a Dart-only package, all you need to do is install the most recent version to your dependencies:

```yaml
dependencies:
  schedules: ^0.0.1
```

## Usage

Use one of the Schedule classes to represent a recurring event:

#### Singular (one-time event)

```dart
// One time on January 1, 2023
final singular = Singular(
  date: DateTime(2023, 01, 01),
);
```

#### Daily

Repeats every _n_ days

```dart
// Every other day, beginning on January 1, 2023.
final daily = Daily(
  startDate: DateTime(2023, 01, 01),
  interval: 2,
);
```

#### Weekly

Repeats every _n_ weeks on the specified weekdays.

```dart
// Every other week on Monday and Thursday, 
// beginning on January 1, 2023.
final weekly = Weekly(
  startDate: DateTime(2023, 01, 01),
  frequency: 2,
  days: [DateTime.monday, DateTime.thursday],
);
```

#### Monthly

Repeats every _n_ months on the specified days.

```dart
// Every month on the 1st and 15th,
// beginning on January 1, 2023.
final monthly = Monthly(
  startDate: DateTime(2023, 01, 01),
  frequency: 1,
  days: [1, 15],
);
```

#### Yearly

Repeats every _n_ years on the specified date.

```dart
// Every 3 years on January 1st, 
// beginning on January 1, 2023.
final yearly = Yearly(
  startDate: DateTime(2023, 01, 01),
  frequency: 3,
);
```

### Occurrence

Once you have your Schedule, you can use it to determine which dates it falls on at any point in time (after its start date).

```dart
// Every month on the 1st and 15th.
final payday = Monthly(
  startDate: DateTime(2023, 01, 01),
  frequency: 1,
  days: [1, 15],
);

final isPayday = payday.occursOn(DateTime(2024, 06, 15)); // true
```