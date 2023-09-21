#PHP #webDevelopment 

## String Functions

There are several functions in PHP to manipulate strings.

### strlen() - Return the Length of a String
The PHP `strlen()` function returns the length (number of characters including whitespaces) of a string.
```php
<?php  
echo strlen("Hello world!"); // outputs 12  
?>
```
You can also pass a string variable to this function.
### str_word_count() - Return number of words in a string
The PHP `str_word_count()` function counts the number of words in a string.
```php
<?php  
echo str_word_count("Hello world!"); // outputs 2  
?>
```

### strrev() - Reverse a string
The PHP `strrev()` function reverses a string.
```php
<?php  
echo strrev("Hello world!"); // outputs !dlrow olleH  
?>
```

### strpos() - Search For a Text Within a String
The PHP `strpos()` function searches for a specific text within a string. If a match is found, the function returns the character position of the first match. If no match is found, it will return FALSE.
```php
<?php  
echo strpos("Hello world!", "world"); // outputs 6  
?>
```

### str_replace() - Replace Text Within a String
The PHP `str_replace()` function replaces some characters with some other characters in a string.
```php
<?php  
echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!  
?>
```

## More String Functions
|Function|Description|
|---|---|
|[addcslashes()](https://www.w3schools.com/php/func_string_addcslashes.asp)|Returns a string with backslashes in front of the specified characters|
|[addslashes()](https://www.w3schools.com/php/func_string_addslashes.asp)|Returns a string with backslashes in front of predefined characters|
|[bin2hex()](https://www.w3schools.com/php/func_string_bin2hex.asp)|Converts a string of ASCII characters to hexadecimal values|
|[chop()](https://www.w3schools.com/php/func_string_chop.asp)|Removes whitespace or other characters from the right end of a string|
|[chr()](https://www.w3schools.com/php/func_string_chr.asp)|Returns a character from a specified ASCII value|
|[chunk_split()](https://www.w3schools.com/php/func_string_chunk_split.asp)|Splits a string into a series of smaller parts|
|[convert_cyr_string()](https://www.w3schools.com/php/func_string_convert_cyr_string.asp)|Converts a string from one Cyrillic character-set to another|
|[convert_uudecode()](https://www.w3schools.com/php/func_string_convert_uudecode.asp)|Decodes a uuencoded string|
|[convert_uuencode()](https://www.w3schools.com/php/func_string_convert_uuencode.asp)|Encodes a string using the uuencode algorithm|
|[count_chars()](https://www.w3schools.com/php/func_string_count_chars.asp)|Returns information about characters used in a string|
|[crc32()](https://www.w3schools.com/php/func_string_crc32.asp)|Calculates a 32-bit CRC for a string|
|[crypt()](https://www.w3schools.com/php/func_string_crypt.asp)|One-way string hashing|
|[echo()](https://www.w3schools.com/php/func_string_echo.asp)|Outputs one or more strings|
|[explode()](https://www.w3schools.com/php/func_string_explode.asp)|Breaks a string into an array|
|[fprintf()](https://www.w3schools.com/php/func_string_fprintf.asp)|Writes a formatted string to a specified output stream|
|[get_html_translation_table()](https://www.w3schools.com/php/func_string_get_html_translation_table.asp)|Returns the translation table used by htmlspecialchars() and htmlentities()|
|[hebrev()](https://www.w3schools.com/php/func_string_hebrev.asp)|Converts Hebrew text to visual text|
|[hebrevc()](https://www.w3schools.com/php/func_string_hebrevc.asp)|Converts Hebrew text to visual text and new lines (\n) into <br>|
|[hex2bin()](https://www.w3schools.com/php/func_string_hex2bin.asp)|Converts a string of hexadecimal values to ASCII characters|
|[html_entity_decode()](https://www.w3schools.com/php/func_string_html_entity_decode.asp)|Converts HTML entities to characters|
|[htmlentities()](https://www.w3schools.com/php/func_string_htmlentities.asp)|Converts characters to HTML entities|
|[htmlspecialchars_decode()](https://www.w3schools.com/php/func_string_htmlspecialchars_decode.asp)|Converts some predefined HTML entities to characters|
|[htmlspecialchars()](https://www.w3schools.com/php/func_string_htmlspecialchars.asp)|Converts some predefined characters to HTML entities|
|[implode()](https://www.w3schools.com/php/func_string_implode.asp)|Returns a string from the elements of an array|
|[join()](https://www.w3schools.com/php/func_string_join.asp)|Alias of [implode()](https://www.w3schools.com/php/func_string_implode.asp)|
|[lcfirst()](https://www.w3schools.com/php/func_string_lcfirst.asp)|Converts the first character of a string to lowercase|
|[levenshtein()](https://www.w3schools.com/php/func_string_levenshtein.asp)|Returns the Levenshtein distance between two strings|
|[localeconv()](https://www.w3schools.com/php/func_string_localeconv.asp)|Returns locale numeric and monetary formatting information|
|[ltrim()](https://www.w3schools.com/php/func_string_ltrim.asp)|Removes whitespace or other characters from the left side of a string|
|[md5()](https://www.w3schools.com/php/func_string_md5.asp)|Calculates the MD5 hash of a string|
|[md5_file()](https://www.w3schools.com/php/func_string_md5_file.asp)|Calculates the MD5 hash of a file|
|[metaphone()](https://www.w3schools.com/php/func_string_metaphone.asp)|Calculates the metaphone key of a string|
|[money_format()](https://www.w3schools.com/php/func_string_money_format.asp)|Returns a string formatted as a currency string|
|[nl_langinfo()](https://www.w3schools.com/php/func_string_nl_langinfo.asp)|Returns specific local information|
|[nl2br()](https://www.w3schools.com/php/func_string_nl2br.asp)|Inserts HTML line breaks in front of each newline in a string|
|[number_format()](https://www.w3schools.com/php/func_string_number_format.asp)|Formats a number with grouped thousands|
|[ord()](https://www.w3schools.com/php/func_string_ord.asp)|Returns the ASCII value of the first character of a string|
|[parse_str()](https://www.w3schools.com/php/func_string_parse_str.asp)|Parses a query string into variables|
|[print()](https://www.w3schools.com/php/func_string_print.asp)|Outputs one or more strings|
|[printf()](https://www.w3schools.com/php/func_string_printf.asp)|Outputs a formatted string|
|[quoted_printable_decode()](https://www.w3schools.com/php/func_string_quoted_printable_decode.asp)|Converts a quoted-printable string to an 8-bit string|
|[quoted_printable_encode()](https://www.w3schools.com/php/func_string_quoted_printable_encode.asp)|Converts an 8-bit string to a quoted printable string|
|[quotemeta()](https://www.w3schools.com/php/func_string_quotemeta.asp)|Quotes meta characters|
|[rtrim()](https://www.w3schools.com/php/func_string_rtrim.asp)|Removes whitespace or other characters from the right side of a string|
|[setlocale()](https://www.w3schools.com/php/func_string_setlocale.asp)|Sets locale information|
|[sha1()](https://www.w3schools.com/php/func_string_sha1.asp)|Calculates the SHA-1 hash of a string|
|[sha1_file()](https://www.w3schools.com/php/func_string_sha1_file.asp)|Calculates the SHA-1 hash of a file|
|[similar_text()](https://www.w3schools.com/php/func_string_similar_text.asp)|Calculates the similarity between two strings|
|[soundex()](https://www.w3schools.com/php/func_string_soundex.asp)|Calculates the soundex key of a string|
|[sprintf()](https://www.w3schools.com/php/func_string_sprintf.asp)|Writes a formatted string to a variable|
|[sscanf()](https://www.w3schools.com/php/func_string_sscanf.asp)|Parses input from a string according to a format|
|[str_getcsv()](https://www.w3schools.com/php/func_string_str_getcsv.asp)|Parses a CSV string into an array|
|[str_ireplace()](https://www.w3schools.com/php/func_string_str_ireplace.asp)|Replaces some characters in a string (case-insensitive)|
|[str_pad()](https://www.w3schools.com/php/func_string_str_pad.asp)|Pads a string to a new length|
|[str_repeat()](https://www.w3schools.com/php/func_string_str_repeat.asp)|Repeats a string a specified number of times|
|[str_replace()](https://www.w3schools.com/php/func_string_str_replace.asp)|Replaces some characters in a string (case-sensitive)|
|[str_rot13()](https://www.w3schools.com/php/func_string_str_rot13.asp)|Performs the ROT13 encoding on a string|
|[str_shuffle()](https://www.w3schools.com/php/func_string_str_shuffle.asp)|Randomly shuffles all characters in a string|
|[str_split()](https://www.w3schools.com/php/func_string_str_split.asp)|Splits a string into an array|
|[str_word_count()](https://www.w3schools.com/php/func_string_str_word_count.asp)|Count the number of words in a string|
|[strcasecmp()](https://www.w3schools.com/php/func_string_strcasecmp.asp)|Compares two strings (case-insensitive)|
|[strchr()](https://www.w3schools.com/php/func_string_strchr.asp)|Finds the first occurrence of a string inside another string (alias of strstr())|
|[strcmp()](https://www.w3schools.com/php/func_string_strcmp.asp)|Compares two strings (case-sensitive)|
|[strcoll()](https://www.w3schools.com/php/func_string_strcoll.asp)|Compares two strings (locale based string comparison)|
|[strcspn()](https://www.w3schools.com/php/func_string_strcspn.asp)|Returns the number of characters found in a string before any part of some specified characters are found|
|[strip_tags()](https://www.w3schools.com/php/func_string_strip_tags.asp)|Strips HTML and PHP tags from a string|
|[stripcslashes()](https://www.w3schools.com/php/func_string_stripcslashes.asp)|Unquotes a string quoted with addcslashes()|
|[stripslashes()](https://www.w3schools.com/php/func_string_stripslashes.asp)|Unquotes a string quoted with addslashes()|
|[stripos()](https://www.w3schools.com/php/func_string_stripos.asp)|Returns the position of the first occurrence of a string inside another string (case-insensitive)|
|[stristr()](https://www.w3schools.com/php/func_string_stristr.asp)|Finds the first occurrence of a string inside another string (case-insensitive)|
|[strlen()](https://www.w3schools.com/php/func_string_strlen.asp)|Returns the length of a string|
|[strnatcasecmp()](https://www.w3schools.com/php/func_string_strnatcasecmp.asp)|Compares two strings using a "natural order" algorithm (case-insensitive)|
|[strnatcmp()](https://www.w3schools.com/php/func_string_strnatcmp.asp)|Compares two strings using a "natural order" algorithm (case-sensitive)|
|[strncasecmp()](https://www.w3schools.com/php/func_string_strncasecmp.asp)|String comparison of the first n characters (case-insensitive)|
|[strncmp()](https://www.w3schools.com/php/func_string_strncmp.asp)|String comparison of the first n characters (case-sensitive)|
|[strpbrk()](https://www.w3schools.com/php/func_string_strpbrk.asp)|Searches a string for any of a set of characters|
|[strpos()](https://www.w3schools.com/php/func_string_strpos.asp)|Returns the position of the first occurrence of a string inside another string (case-sensitive)|
|[strrchr()](https://www.w3schools.com/php/func_string_strrchr.asp)|Finds the last occurrence of a string inside another string|
|[strrev()](https://www.w3schools.com/php/func_string_strrev.asp)|Reverses a string|
|[strripos()](https://www.w3schools.com/php/func_string_strripos.asp)|Finds the position of the last occurrence of a string inside another string (case-insensitive)|
|[strrpos()](https://www.w3schools.com/php/func_string_strrpos.asp)|Finds the position of the last occurrence of a string inside another string (case-sensitive)|
|[strspn()](https://www.w3schools.com/php/func_string_strspn.asp)|Returns the number of characters found in a string that contains only characters from a specified charlist|
|[strstr()](https://www.w3schools.com/php/func_string_strstr.asp)|Finds the first occurrence of a string inside another string (case-sensitive)|
|[strtok()](https://www.w3schools.com/php/func_string_strtok.asp)|Splits a string into smaller strings|
|[strtolower()](https://www.w3schools.com/php/func_string_strtolower.asp)|Converts a string to lowercase letters|
|[strtoupper()](https://www.w3schools.com/php/func_string_strtoupper.asp)|Converts a string to uppercase letters|
|[strtr()](https://www.w3schools.com/php/func_string_strtr.asp)|Translates certain characters in a string|
|[substr()](https://www.w3schools.com/php/func_string_substr.asp)|Returns a part of a string|
|[substr_compare()](https://www.w3schools.com/php/func_string_substr_compare.asp)|Compares two strings from a specified start position (binary safe and optionally case-sensitive)|
|[substr_count()](https://www.w3schools.com/php/func_string_substr_count.asp)|Counts the number of times a substring occurs in a string|
|[substr_replace()](https://www.w3schools.com/php/func_string_substr_replace.asp)|Replaces a part of a string with another string|
|[trim()](https://www.w3schools.com/php/func_string_trim.asp)|Removes whitespace or other characters from both sides of a string|
|[ucfirst()](https://www.w3schools.com/php/func_string_ucfirst.asp)|Converts the first character of a string to uppercase|
|[ucwords()](https://www.w3schools.com/php/func_string_ucwords.asp)|Converts the first character of each word in a string to uppercase|
|[vfprintf()](https://www.w3schools.com/php/func_string_vfprintf.asp)|Writes a formatted string to a specified output stream|
|[vprintf()](https://www.w3schools.com/php/func_string_vprintf.asp)|Outputs a formatted string|
|[vsprintf()](https://www.w3schools.com/php/func_string_vsprintf.asp)|Writes a formatted string to a variable|
|[wordwrap()](https://www.w3schools.com/php/func_string_wordwrap.asp)|Wraps a string to a given number of characters|