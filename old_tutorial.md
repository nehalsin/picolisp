# Old Code using Picolisp Functions

A `symbol` Tutorial 

## show function

```
$ pil +
(setq A '(This is the value))-> (This is the value)       
: (put 'A 'key1)
-> NIL
: (show 'A)                 
 A (This is the value)
-> A                         
: (show A)
-> (This is the value)
: (put 'A 'key1 2)         
  -> 2
: (show 'A)                  
A (This is the value)
   key1 2
-> A                         
:
```

### Own Example Code 
```
:(setq radha '(I am a girl)))
-> (I am a girl)            
 : (put 'radha 'age '30)     
 -> 30
(put 'radha 'profession 'doctor)                         
 -> doctor
(put 'radha 'bloodgroup 'bpositive)
-> bpositive
: (show radha)
-> (I am a girl)            
 : (show 'radha)
radha (I am a girl)
   bloodgroup bpositive         
   profession doctor            
   age 30                    
-> radha
```
## match

### Own Example Code 
```
: (match (1 2 3) (4 5 6))   
 -> NIL
: (match (1 2 3) (1 2 3))  
 -> T
```
##  listing in property and further use of show function

Example matching Abu

###  Own 
```
: (put 'B 'profile 'radha)  
 -> radha
: (setq Lst '(A B radha))
-> (A B radha)               
: (show Lst 2 'profile)
radha (I am a girl)
  bloodgroup bpositive             profession doctor           
 age 30                    
-> radha
: (show 'B)                  
B NIL                           
profile radha            
 -> B
: (show 'B 'profile)        
radha (I am a girl)
   bloodgroup bpositive         profession doctor
   age 30                   
-> radha        
```
##  Notes 

 1.  Property helps define further description of a variable. 
 2. This in itself is a list. 
 3. One list can be nested or used as a part of another list in the form of a property. 
 4. This helps save time of the programmer in defining same property of different variables. 
 5. Properties are list that can be linked to any variable for further operations. 
 6. One important thing to understand is that everything in the lisp especially picolisp is essentially a list. 
 7. Different lists can be merged or used in congruence together for different operations. Main thing is to understand and get used to the basic structure of lisp which is a list. List was basically always processing in the form of a list. Once the mind gets used to this notion of programming everything falls into place. 

##  Practicing show function with another example much like the older example. 

See how the lists combine and operate together. 

###  1
```
$ pil +                      
: (setq 'a '(1 2))           
-> (1 2)                     
: (put 'b '1 'a)             
-> a                         
: (show b)
NIL NIL                     
 -> NIL
: (show 'b)                 
 b NIL
   1 a
-> b                       
  : (show 'b '1)             
  a NIL                      
  -> a                        
 : (setq L '(a b c))         
 -> (a b c)
: (put 'b '1 'a)
-> a                         
: (show 'a)                  
a NIL                       
 -> a
: (setq a (1 2))            
 -> (1 2)                     
: (show 'a)                 
 a (1 2)
-> a
: (show 'b)                  
b NIL
   1 a                      
 -> b
: (show 'b '1)
a (1 2)
-> a
```

To be continued and the above example to be corrected.

###   2 
```
$ pil +                      
: (setq A '(This is apple))  
-> (This is apple)           
: (put 'A 'key1 'red)
-> red                       
: (show 'A)                  
A (This is apple)
   key1 red                  
-> A                         
: (setq Lst '(A B C))       
 -> (A B C)
: (put 'B 'key2 'A)
-> A                         
: (show 'B 'key2)            
A (This is apple)
   key1 red
-> A                         
: (put 'C 'key2 'B)          
-> B
: (show 'C 'key2)
B NIL
   key2 A                    
-> B
: (setq B '(This is fruit))
-> (This is fruit)           
: (show 'C 'key2)
B (This is fruit)               
key2 A
-> B                         
: (show 'C 2 'key2)          
NIL NIL
-> NIL                       
: (put 'C 'key2 'A)
-> A                         
: (show 'C 'key2)            
A (This is apple)
   key1 red                  
-> A                         
```
###  3 

2020-08-13

```
$ pil +
(setq neha '(works in infosys))
-> (works in infosys)
: (put 'neha 'color 'red)
-> red
: (put 'neha 'dress 'saree)
-> saree
:(put 'neha 'hobby 'reading))
-> reading
: (put 'neha 'loves 'nature)
-> nature
(setq Girls '(neha shiela lila cora))
-> (neha shiela lila cora)
: (show 'neha)
neha (works in infosys)
   loves nature
   hobby reading
   dress saree
   color red
-> neha
: (put 'lila 'color 'neha)
-> neha
: (show 'lila 'color)
neha (works in infosys)
   loves nature
   hobby reading
   dress saree
   color red
-> neha
: (show 'lila)
lila NIL
   color neha
-> lila
(setq Lst (neha shiela lila cora))
-> NIL
: (show 'lila Lst 'color)
NIL NIL
-> NIL
: (show 'lila 'color)
neha (works in infosys)
   loves nature
   hobby reading
   dress saree
   color red
-> neha
: (show 'Lst)
Lst NIL
-> Lst
: (show 'Girls)
Girls (neha shiela lila cora)
-> Girls
: (show Lst 3 'color)
NIL NIL
-> NIL
: (show Girls 3 'color)
neha (works in infosys)
   loves nature
   hobby reading
   dress saree
   color red
-> neha
```
##  more 

###  Own 2020-08-13
```
: (more Girls)
neha
shiela
lila
cora
-> NIL

: (more '(lila neha))
lila
neha
-> NIL

: (more '(lila neha) show)
lila NIL
   color neha

neha (works in infosys)
   loves nature
   hobby reading
   dress saree
   color red

-> NIL
```
###  Own 2020-08-18

#### 1
```
$ pil +
(setq Lst '(amma baba pota poti))
-> (amma baba pota poti)
: (more Lst)
amma
baba
pota
poti
-> NIL
: (more Lst)
amma.
-> T
: (more Lst)
amma
baba.
-> T
:
```
#### 2
```
-> T
: (setq Ram '(I live in a village))
-> (I live in a village)
: (setq Shyam '(I am neighbor of Ram))
-> (I am neighbor of Ram)

: (setq Bhola '(Ram told me to learn programming))
-> (Ram told me to learn programming)
: (setq Lst '(Ram Shyam Bhola))
-> (Ram Shyam Bhola)
: (more Lst)
Ram
Shyam
Bhola
-> NIL
: (more Lst show)
Ram (I live in a village)

Shyam (I am neighbor of Ram)

Bhola (Ram told me to learn programming)

-> NIL
: (more Lst pp)
(de Ram I
   live
   in
   a
   village )

(de Shyam I
   am
   neighbor
   of
   Ram )

(de Bhola Ram
   told
   me
   to
   learn
   programming )

-> NIL
:
```
##  who 

###  Own 2020-08-13
```
: (who 'red)
-> (pico)
: (who 'neha)
-> (Girls pico)
: (who 'color)
-> (pico)
: (who 'Girls)
-> (pico)
```
##  Functions 2020-08-19

###  Functions and 'more'

#### Own 

##### 1 
```
$ pil +
: (de hello (X)
(prinl "hello" X))
-> hello
: (hello "tom")
hellotom
-> "tom"

: (de hello1 (X)
(prinl "Hi " X))
-> hello1
: (hello1 "tom")
Hi tom
-> "tom"
: (de hello2 (X)
(prinl "go to hell " X))
-> hello2
: (hello2 "tom")
go to hell tom
-> "tom"
(setq Lst '(hello hello1 hello2))
-> (hello hello1 hello2)

: (more Lst pp)
(de hello (X)
   (prinl "hello" X) )

(de hello1 (X)
   (prinl "Hi " X) )

(de hello2 (X)
   (prinl "go to hell " X) )

-> NIL
:
```
##### 2 (2020-08-24)
```
: (de addme (X) (prinl "Adding  " X "
to another " X " gives " (+ X X)))
-> addme
: (addme 4)
Adding  4to another 4 gives 8
-> 8
```



