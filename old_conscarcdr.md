# cons, car, cdr

[Helpful reference](https://stackoverflow.com/questions/8358783/what-was-a-reason-to-introduce-dotted-pair-in-lisp)
```
: (setq r (1 2 3))
-> (1 2 3)
: (cdr r)
-> (2 3)
: (cons (car r) (cdr r))
-> (1 2 3)
: (prin r)
123-> (1 2 3)
: (cons (1 2) (1 2))
-> ((1 2) 1 2)
: (cons (1 2) 3)
-> ((1 2) . 3)
```
```
: (setq a (1 2 3 4))
-> (1 2 3 4)
: (car a)
-> 1
: (cdr a)
-> (2 3 4)
```
```
: (prin (cons (car a) (cdr a)))
1234-> (1 2 3 4)
: (prin (cons (car a) 2))
12-> (1 . 2)
: (prin (cons (cdr a) (1)))
2341-> ((2 3 4) 1)
: (prin (cons (cdr a) 1))
2341-> ((2 3 4) . 1)
```
```
: (setq a (1 2))
-> (1 2)
: (setq b (3 4))
-> (3 4)
: (cons a b)
-> ((1 2) 3 4)
: (cons a 'b)
-> ((1 2) . b)
```
```
(cons 'a 'b)
-> (a . b)
: (prin (a . b))
Segmentation fault
$ pil
: (setq a (1 2))
-> (1 2)
: (setq b (3 4))
-> (3 4)
: (prin (cons 'a 'b))
ab-> (a . b)
```
```
: (prin a b)
1234-> (3 4)
: (prin 'a 'b)
ab-> b
```
```
: (cons (+ 1 2) (+ 3 4))
-> (3 . 7)
```
```
: (cons g h j k)
-> (NIL NIL NIL)
: (cons 1 2 6 8)
-> (1 2 6 . 8)
```
```
: (cons a b 5 6)
-> (NIL NIL 5 . 6)
```
```
: (setq a (1 2 3))
-> (1 2 3)
: (cons 5 a)
-> (5 1 2 3)
```
```
: (cons (cons 1 2) (cons 3 4))
-> ((1 . 2) 3 . 4)
: (cons (cons 1 2 (cons 3 4)))
-> ((1 2 3 . 4))
```
```
: (cons 1 2 (cons 1 2))
-> (1 2 1 . 2)
: (cons (cons 1 2) (cons 1 2))
-> ((1 . 2) 1 . 2)
: (cons (cons 1 2) 1 2)
-> ((1 . 2) 1 . 2)
```
## could not understand
```
: (cons 'a (1 2) "ok")
-> (a (1 2) . "ok")
: (list 'a (1 2) "ok")
-> (a (1 2) "ok")
```





