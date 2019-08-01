# Oracle String Functions

| Function | Example | Result | Purpose |
| --- | --- | --- | ---|
| ASCII |	ASCII(‘A’) | 65 |	Returns an ASCII code value of a character.|
|CHR	|CHR(’65’)	|‘A’	|Converts a numeric value to its corresponding ASCII character.|
|CONCAT	|CONCAT(‘A’,’BC’)	|‘ABC’	|Concatenate two strings and return the combined string.|
|CONVERT	|CONVERT( ‘Ä Ê Í’, ‘US7ASCII’, ‘WE8ISO8859P1’ )	| ‘A E I’|	Convert a character string from one character set to another.|
|DUMP	|DUMP(‘A’)	|Typ=96 Len=1: |65|	Return a string value (VARCHAR2) that includes the datatype code, length measured in bytes, and internal representation of a specified expression.|
| INITCAP	 |INITCAP(‘hi  there’)	|‘Hi There’|	Converts the first character in each word in a specified string to uppercase and the rest to lowercase.|
| INSTR	|INSTR( ‘This is a playlist’, ‘is’)|	3	|Search for a substring and return the location of the substring in a string|
| LENGTH	|LENGTH(‘ABC’)	|3	|Return the number of characters (or length) of a specified string|
|LOWER	|LOWER(‘Abc’)	|‘abc’|	Return a string with all characters converted to lowercase.|
|LPAD	|LPAD(‘ABC’,5,’*’)	|‘**ABC’|	Return a string that is left-padded with the specified characters to a certain length.|
|LTRIM	|LTRIM(‘ ABC ‘)	|‘ABC  ‘|	Remove spaces or other specified characters in a set from the left end of a string.|
|REGEXP_COUNT	|REGEXP_COUNT(‘1 2 3 abc’,’\d’)|	3|	Return the number of times a pattern occurs in a string.|
|REGEXP_INSTR	|REGEXP_INSTR( ‘Y2K problem’,’\d+’)	|2|	Return the position of a pattern in a string.|
|REGEXP_LIKE	|REGEXP_LIKE( ‘Year of 2017′,’\d+’ )|	true|	Match a string based on a regular expression pattern.|
|REGEXP_REPLACE	|REGEXP_REPLACE( ‘Year of 2017′,’\d+’, ‘Dragon’ )	 |‘Year of Dragon’|	Replace substring in a string by a new substring using a regular expression.|
|REGEXP_SUBSTR	|REGEXP_SUBSTR( ‘Number 10’, ‘\d+’ )	 |10	|Extract substrings from a string using a pattern of a regular expression.|
|REPLACE	|REPLACE(‘JACK AND JOND’,’J’,’BL’);	 |‘BLACK AND BLOND’|	Replace all occurrences of a substring by another substring in a string.|
|RPAD	 |RPAD(‘ABC’,5,’*’)	|‘ABC**’|	Return a string that is right-padded with the specified characters to a certain length.|
|RTRIM	|RTRIM(‘ ABC ‘)	|‘ ABC’|	Remove all spaces or specified character in a set from the right end of a string.|
|SOUNDEX	|SOUNDEX(‘sea’)	|‘S000’|	Return a phonetic representation of a specified string.|
|SUBSTR	|SUBSTR(‘Oracle Substring’, 1, 6 )|	‘Oracle’|	Extract a substring from a string.|
|TRANSLATE	 |TRANSLATE(‘12345’, ‘143’, ‘bx’)	 |‘b2x5’|	Replace all occurrences of characters by other characters in a string.|
|TRIM	|TRIM(‘ ABC ‘)	|‘ABC’	|Remove the space character or other specified characters either from the start or end of a string.|
|UPPER	|UPPER(‘Abc’)	|‘ABC’|	Convert all characters in a specified string to uppercase.|
