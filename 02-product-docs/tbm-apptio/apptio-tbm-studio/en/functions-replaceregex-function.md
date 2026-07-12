---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "ReplaceRegex function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "ReplaceRegex function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/replaceregex.html"
images:
  - "03-media/apptio-tbm-studio/studio_diagram_output%20example.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# ReplaceRegex function

*Performs a regular expression-based replacement on text values within a column. Useful for extracting or cleansing data using advanced pattern matching.*

## Syntax

ReplaceRegex(column_name, match_expression, replacement_expression)

## Arguments

column_name : The name of the column containing the text to be replaced.

match_expression : The regular expression that will identify the text to be replaced.

replacement_expression : The regular expression used to create the replacement text.

## Behavior

- Searches each row of the specified column for matches to the given regular expression.
- If a match is found, the result is constructed using the replacement expression, which may include capture groups.
- If no match is found, the original value from the column is returned unchanged. Uses Java regular expression syntax and supports non-greedy matching using '?'.

## Return type

String

## Example

Assume the following syntax:

ReplaceRegex([Source Column],[Regex Statement],[Capture Group])

If the regex statement finds a match in the source column, then the formula will return the value of the capture group. If no match is found, it will return the value of the source column. The regex flavor that is supported in the function is Java.

Here's a specific example:

```
=ReplaceRegex(Journal Entry
      Description,"^.*(INVOICE).{0,8}?(\d{10}).*","$2")
```

This formula will look for the word "INVOICE" (in all caps) in the column Journal Entry Description. If it finds that string, it will return the first 10-digit number it finds within 8 characters of the end of the word. You could use this formula to parse 10-digit invoice numbers out of a free text journal entry description. In this example, the first capture group ($1) is "INVOICE" and the second capture group ($2) is the ten digit number (\d{10}).

Here's an example of its output:

- The final .* matches any character, any number of times.
- Again, the parenthesis specify this number is a capture group. In this case, it's capture group is 2.
- 10} means that the prior rule must apply to 10 characters in a row. So, \d{10} means "match 10 numbers in a row."
- The \d means to match any number.
- The question mark (?) means that the prior match should match the smallest number of characters possible. For example, if you have an 11-digit number, the first 10 digits will be matched by the next term, not the last 10. Removing the ? will match the last 10 instead.
- The period (.) means the same as before. However, the {0,8} means that it matches as few as 0 and as many as 8 characters.
- The parenthesis that invoice is wrapped in specifies that it's value should be captured. The leftmost value wrapped in parenthesis is capture group 1. Each additional capture group increments the number by 1, from left to right.
- The word "INVOICE" means match the exact word INVOICE. It's case sensitive.
- The asterisk (*) means that the preceding criteria can match any number of characters. So, period asterisk (.*) means match any number of any character.
- The period (.) is a wild card that will match any characters.
- The caret (^) means that our regular expression must start matching at the beginning of the value in the Journal Entry Description.

Notice the output of the row:

MY MAIN INVOICE # IS 6872954678, BUT WE ALSO HAVE A MASTER INVOICE OF 1234567890

This output is matching the second invoice number, not the first. This is because of the very first period Asterisk (.*) in the regular expression. This term will match as many characters as it can until it finds one that it cannot match. If we wanted it to instead match the smallest number of characters possible, we could add a ? to our regular expression giving:

```
=ReplaceRegex(Journal Entry
      Description,"^.*?(INVOICE).{0,8}?(\d{10}).*","$2")
```

For more information on regex syntax or to test your own regex statements, visit http://www.rexegg.com/regex-quickstart.html and regex101.com .

- To capture specific parts of the matched string, use parentheses in the match expression and reference them as "\(1", "\)2", etc. in the replacement expression.
- If no match is found in a row, the original column value is returned.
- Make sure to test your regex patterns using online tools or Java-based environments to ensure compatibility.
