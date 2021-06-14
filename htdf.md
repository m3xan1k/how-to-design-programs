# How To Design Functions

## Design recipies

1. Signature, purpose and stub
2. Define examples(test-cases), wrap each with check-equal(or assert in python, js, etc)
3. Function template(define, name, args, return draft)
4. Code function body(based on purpose)
5. Test and debug untill correct result


### Example

```
Create function that takes word and makes it plural.
For simplicity just add "s" at the end.
```

1. Signature, purpose and stub

Think about problem. `Take word and produce plural`.
Looks like function may take a string and return a string.
```
String -> String
```

What's the purpose?
```
Take string and add "s" at the end.
```

Stub
```
(define (make-plural word) "")
```

2. Examples(test-cases)

```
(check-equal (make-plural "book") "books")
(check-equal (make-plural "airplane") "airplanes")
```

3. Template is just a copy of stub. Try to run it and check you have only tests failed and not other errors.
```
(define (make-plural word) "")
```

4. Code function body. Look at purpose. Looks like we want to append "s" to given word.
```
(define (make-plural word)
  (string-append word "s"))
```

5. Run file and check that all tests have passed.


## Full source code example

```
#lang racket

(require rackunit)


;; Signature
;; String -> String

;; Purpose
;; Make word plural(Take string and add "s" at the end)

;; Tests. You can move them to another module as you wish.

(check-equal (make-plural "book") "books")
(check-equal (make-plural "airplane") "airplanes")

;; Template
;; (define (make-plural word) "")

;; Source code of the function
(define (make-plural word)
  (string-append word "s"))

```
