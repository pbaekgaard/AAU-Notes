---
link: https://www.notion.so/Recursive-Descent-26c3cbff31ab4da7bfe83ab42edfb766
notionID: 26c3cbff-31ab-4da7-bfe8-3ab42edfb766
---
Resurive Descent technique is pretty much rewriting the [[Context-free grammar (CFG)]] as code.
![[Pasted image 20230213142452.png]]

Using AC as an example, we know the *Stmts* can is either a statement followed by another statements OR it is the empty string.

In code, as seen above. Furthermore the *Stmt* has two predictors. Predictors help us identify the coming syntax. *Stmt* can either be an *id assign Val Expr* or *print id*. The identifiers for *Stmt* is therefore *id* and *print* as they are the two starting terminals, that are easily used to identify what will happen.

Looking back at *stmts*, using the predictors it is checked for the predictors of the *stmt*. If none of the predictors are found then it must be an empty string. The empty string is checked for, if this isn't found then there can only be an error and an error is called.

If the predictors are found the *stmt* procedure is called checking for the *stmt* and the *stmts* is recursively called as *stmts* can contain "infinitely" many *stmts*.

