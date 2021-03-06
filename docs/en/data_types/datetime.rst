DateTime
--------

Date with time. Stored in four bytes as a Unix timestamp (unsigned). Allows storing values in the same range as for the Date type. The minimal value is output as 0000-00-00 00:00:00. The time is stored with accuracy up to one second (without leap seconds).


Time zones
~~~~~~~~~~~~~

The date with time is converted from text (divided into component parts) to binary and back, using the system's time zone at the time the client or server starts. In text format, information about daylight savings is lost.

Note that by default the client adopts the server time zone at the beginning of the session. You can change this behaviour with the --use_client_time_zone command line switch.

Supports only those time zones that never had the time differ from UTC for a partial number of hours (without leap seconds) over the entire time range you will be working with.

So when working with a textual date (for example, when saving text dumps), keep in mind that there may be ambiguity during changes for daylight savings time, and there may be problems matching data if the time zone changed.
