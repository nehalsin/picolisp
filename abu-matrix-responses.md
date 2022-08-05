# Abu replies 

## 2022-07-15

Yes, CVS is automatically generated as a side-effect of reports.

The whole database, or parts of it, can be exported with 'dump' from @lib/too.l (and then imported elsewhere with a normal 'load').

## 2022-07-20

Q: > <@abu:7fach.de> Yes, CVS is automatically generated as a side-effect of reports.
> 
> The whole database, or parts of it, can be exported with 'dump' from @lib/too.l (and then imported elsewhere with a normal 'load').

And can PicoLisp import CSV files? 

----

abu: CSV files can easily be parsed. (while (line) (let L (split @ "\t") ..

Or, the example I posted on twitter (in (list "xlsx2csv" "-dtab" "-aei" File) ... for non-TAB-separated files

But then of course it depends on the type of data. CSVs are tables, and the Pil DB is a graph.

## 2022-07-21

Q: > <@abu:7fach.de> But then of course it depends on the type of data. CSVs are tables, and the Pil DB is a graph.

For a concrete example let us take the csv file attached. How will it be represented internally as data structures, symbols etc?

----

abu: It is the concrete application which has to know the meaning of the data.

It could read it into a database, where each column in the CSV goes to some property of one ore several objects.

The most simple case is just reading it into a list of lists:

```
: (make
   (in "example.csv"
      (while (line)
         (link (split @ ",")) ) ) )
-> ((("a") ("b") ("c")) (("1") ("2") ("3")) (("4") ("5") ("6")) (("x") ("y") ("z")))
```
This gives lists of lists of strings. You could then convert numbers with 'format' and/or intern symbols with 'intern'.

It all depends on the purpose.

