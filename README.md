# regex_tutorial

# Matching an Email – /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

- `/../` : The expression is enclosed in forward slashes. This indicates a regular expression in most programming languages.

- `^` : The caret indicates the start of a string. The regex will start matching from the beginning of the string.

- `([a-z0-9_\.-]+)` :
`()` indicates a 'captured group'. Captured groups are useful for extracting specific parts of a matched string or for further processing the matched text. This part of the match can be extracted separately if needed.
`[a-z0-9_\.-]` This is a character class that matches any lowercase letter (a-z), digit(0-9), underscore(_), period(.), or hyphen(-).
`+` The plus sign indicates "one or more" in the above character class. This ensures that the local part of the email (before the @ symbol) contains at least one character. 

- `@` : The @ sybol is matched literally.  It's a required part of any email address.

- `([\da-z\.-]+)` : This is another 'captured group'. It matches the domain part of the email address (between the @ and the final .)
`[\da-z\.-]` is similar to the previous character class. However, \d is shorthand for any digit equivalent to 0-9.
`+` Again, this means "one or more" of the preceding characters.

- `\.` : The backslash escapes the period(.) to indicate that we arematch the literal dot rather than the "any character" wildcard.  This matches the dot before the top-level domain (like .com for example)

- `([a-z\.]{2,6})` : Another captured group. This part matches the top-level domain (TLD), such as com or edu.
`[a-z\.]` matches any lowercase letter or period.
`{2,6}` indicates that the previous character class must appear at least 2 times but no more than 6 times.  

- `$` This dollar sign indicates the end of a string.  This ensures that the entire string matches the email format, with nothing extra before or after.

<hr>

# Conclusion:
This regex matches an email address where the local part (before the @) contains one or more lowercase letters, digits, underscores, periods, or hyphens.  The domain part (the part after the @ but before the last .) contains one or more digits, lowercase letters, periods or hyphens.  The TLD (after the last .) consists of 2 to 6 characters that are either lowercase letters or periods.  It is a standard way to validate email addresses, though it might not cover all possible valid email formats.  For example, it does not allow uppercase letters or international characters. 