# 1-lexer-re-antlr

## TODO 2025
- [ ] Check Clang Lexer Code
- [ ] EOF (Check the grammar `C.g4`)
- [ ] `-` 三种用途：减法、取反、负数（如何区分它们；如何区分词法分析部分与语法分析部分）

## Outline

### Grammar
- `|`
- `[a-z]` vs. `'a' .. 'z'` (范围运算符)
- `+`, `*`
- `?`

- play with it
	- WS `-> skip`
	- `fragment`: not lexer rules; cannot be used in grammar rules

### gradle
- Gradle `generateGrammarSource`
	- `build/generated-src/antlr/main/simpleexpr/`
	- `SimpleExprLexer`
		- literal names vs. symbolic names
	- `SimpleExpr.tokens`
	- `Alt + Insert`: Generate Lexer Rules for Literals
		- `if` vs. `ID`
		- grammar rules => implicit lexer rules => explict lexer rules

### non-greedy
#### Comments
- `.`: match any single character, including `\n`
- `.*`: greedy
  - till *the last* `\n`
- `.*?`
	- `+?`, `*?`, `??`

### Matching Principles
- longest
  - `float`
  - 3.1415926
- priority:
  - in this order: single-line comment, doc comment, multi-line comment
- non-greedy

### Strings

### Testing
- `@header`
- error listener

### lexer grammar
- `lexer grammar`
  - 4.1 (1) 语法导入
