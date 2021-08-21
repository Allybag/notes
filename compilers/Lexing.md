Lexing, or tokenising is probably the simplest part of compiling a program.

Lexing is the process of turning a line (or whatever) of code into a stream of tokens:

`int total = bag.calcTotal();`

becomes a stream of tokens:

`Token("int"), Token("total"), Token("="), Token("bag"), Token("."), Token("calcTotal"), Token("("), Token (")"), Token(";")`

Where each token might have some sort of TokenType, and value, for example if "int" is a keyword then the TokenType might be "int", but if "int" is just a type, then it might be an "identifier" with the value "int"

Many tokens are very easy to find, for example a ";" will normally be it's own token, but "=" will often be a valid token, but can also be half of a valid "==" token, so we would not be able to assign "=" to a token before checking the next character. Unless, for example we had some grammar where an "=" and a "==" token were never both syntactically valid at the same time

Identifiers like "bag" above are normally any sequence of chars, after checking that the sequence is not a reserved word.
