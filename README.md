# TSLint issue when there is not "import"

TSLint is not always working when the .ts file to lint doesn't have any `import` statements...

Here's an example of two files with the same error. They are using `let` where `const` must be used since the
"`prefer-const`" rule is set to `true`. The one with an `import` will properly display the error, the other
won't output anything!

To reproduce:

`npm install -g tslint`

Go to this project root and :

`tslint --config tslint.json --project ./import/tsconfig.json`

> _ERROR: C:/XXXXX/import/test-import.ts[3, 5]: Identifier 'someConstant' is never reassigned; use 'const' instead of 'let'._

But :

`tslint --config tslint.json --project ./no-import/tsconfig.json`

> No error!!
