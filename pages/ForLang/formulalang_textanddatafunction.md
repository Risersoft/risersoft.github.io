---
title: Text and Data Functions
keywords: Text and Data Functions
sidebar: forlang_sidebar
permalink: formula-language/text-and-data-functions.html
folder: Forlang
hide_sidebar: false
comments: false
---

# Text and Data Functions


## CHAR

Returns the character specified by the code number from the character set for your computer.


## CODE

Gives you the numeric code corresponding the first character in a specific text string.



**CODE(Text)**

Text is a text string of at least one character in length. This function returns the numeric code of the first character in Text. These code values correspond to those used by your machine to encode the text characters in a string (e.g., Unicode).

If Text is an empty string of zero length, then this function returns the code zero.


## CONCATENATE

Combines two or more text values into a single text string.



**CONCATENATE (text1, text2, ..., textN)**

Text1, text2, ..., textN are multiple text values that you want to concatenate into one text string. These text values may be text strings, numbers (which will be converted into text), or a single value reference (such as a cell reference) containing such a value.

This function provides for elementary text processing in UnitCAD, such as when building message text or appending some connective text or punctuation to the results of evaluating other text-bearing expressions.


## FIND

Finds one piece of text within another piece of text.



**FIND (text_to_find, text_to_search, starting_point)**

Text_to_find is the piece of text you want to find. It can be a reference (for example, a NamedReference to a constant text string or a CalcSettings reference to a TextBox on the form). It should be shorter in length than the text_to_search.

Text_to_search is the piece of text you want to search for text_to_find within. It's commonly a reference to a text string that you want to search.

Starting_point is the one-based character position inside of text_to_search at which UnitCAD will begin searching. This argument is optional and if omitted, the search will begin at the first character.

If text_to_find is not found this function returns a Value error, otherwise it returns the starting position of text_to_find within text_to_search.


## FIXED

Formats a numeric value rounded to a specified number of decimal places and with optional thousands separators.



**FIXED (value, decimal_places, exclude_thousands_separators)**

Value is the numeric value to be rounded and formatted as text.

Decimal_places indicate how many places to the right of the decimal point the value should be rounded. If omitted, rounding occurs to two decimal places.

Exclude_thousands_separators are a boolean value (TRUE or FALSE) indicating whether commas should appear in the formatted text value. By default the formatted text includes commas as thousands separators.

This function may not return text values consistent with your locale's formatting of numbers because it operates using culture invariant settings (these include commas as thousands separators and decimal points) to facilitate unambiguously parsing the text values it formats into numeric values for subsequent calculations. Applications may instead choose to format numeric values after UnitCAD has finished processing them, but before presenting them to their end user.


## LEFT

Gets the leftmost characters from a text value, up to the specified number of characters.



**LEFT (text_value, num_chars)**

Text_value is a piece of text or reference to some text starting with a substring you want to retrieve.

Num_chars indicate the number of characters retrieved from the beginning of text_value. An error value is returned if this argument is less than zero. If this argument exceeds the length of text_value, then all of text_value is retrieved. If omitted, the first character of text_value is retrieved.


## LEN

Counts the number of characters in a text value.



**LEN(text_value)**

Text_value is any text string or reference to a text value for which you want a character count. The number of characters, including all whitespace, determines the length of the text string.

Depending on the character encoding used, some whitespace characters such as line-breaks may count as two characters (one character is a carriage return, the other character is a line feed).

An empty text string contains no characters.


## LOWER

Converts a text value to all lowercase letters.



**LOWER(text_value)**

Text_value is a piece of text you want converted into lowercase. The invariant culture is used to translate characters; therefore, this function may not be suitable for use with localizable text values.



## MID

Gets a specified number of characters from the middle of a text string, starting from a specified position in that string.



**MID (text_value, starting_point, character_count)**

Text_value is a piece of text containing the substring you want to retrieve, when you know the position and length of your desired substring.

Character_count specifies how long of a substring to retrieve from text_value measured as a number of characters. If the requested length, when added to the specified starting_point, exceeds the length of text_value then the remainder of the string starting at starting_point is returned.

Starting_point is the one-based position within text_value of the first character in the substring you want to retrieve. If this argument exceeds the length of text_value then the function will return an empty string.

If either character_count or starting_point has a negative value, or evaluate to an error value, then the function returns an error value.



## REPLACE

Replaces a substring of a text value with some new text. This substring is specified by giving it's starting point and its length in characters, within the original text value.

**REPLACE (text_value, starting_point, character_count, new_text_value)**

Text_value is the original text within which you want to replace some substring of text, and you already know the starting_point and character_count of that substring.

Starting_point is the one-based position within text_value where the replaced substring begins.

Character_count is the length of the substring being replaced as a count of the characters it contains. If this value when added to starting_point would exceed the length remaining in text_value then the entire remainder of text_value is replaced.

New_text_value is some new text that replaces the text of the specified substring. It is not required to be the same length as the replaced substring.

When starting_point or character_count are error values, or less than zero, an error value is returned. If starting_point exceeds the length of text_value then an error value is returned.

It is possible to use the REPLACE () function with other UnitCAD functions to express the replacement of one substring with another. The following UnitCAD expression replaces the word "Old" with the word "New" in the original text value.

**REPLACE ("Hello Old World", FIND("Old"), LEN("Old"), "New")**


## RIGHT

Gets the rightmost characters from a text value, up to the specified number of characters.

**RIGHT (text_value, num_chars)**

Text_value is a piece of text or reference to some text ending with a substring you want to retrieve.

Num_chars indicate the number of characters retrieved from the end of text_value. An error value is returned if this argument is less than zero. If this argument exceeds the length of text_value, then all of text_value is retrieved. If omitted, the last character of text_value is retrieved.



## TRIM

Removes any leading or trailing spaces from a text value, and normalizes runs of whitespace within a text value.

**TRIM(text_value)**

Text_value is a piece of text to trim and normalize the white space of. Trimming removes all leading and trailing white space. Normalization reduces runs of consecutive whitespace appearing within the text_value to single blank spaces.


## UPPER

Converts all lowercase letters in a text string to uppercase.

**UPPER(text_value)**

Text_value is the text you want to convert to uppercase. UPPER does not change characters in text that are not letters.


## VALUE

Retrieves the numeric value of a piece of text that is supposed to represent either a number or a currency.

**VALUE(text_value)**

Text_value is any text value or single-value reference to a text string that you want to convert into a number. It may have been formatted with a sign, currency symbol, or thousands separator. These characters will be stripped to yield the numeric value of the text.

If the text_value is an error value or could not be converted into a numeric value then the function returns an error value.
