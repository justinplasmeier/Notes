# Quip

A simple command-line utility for messing with `.csv` files. 

### Design


### User Interface

Give a range of columns and a range of rows and return it. 

```
street,city,zip,state,beds,baths,sq__ft,type,sale_date,price,latitude,longitude
```
_sample csv file_

`quip -cols 0:3,4,6 -rows 0:2`
returns

```
street,city,zip,state,beds,sq__ft
```

(define process-rows
  (lambda (row row-ctr)
    (conj row row-ctr)))
    
(define index-rows
	(lambda (start end row-ctr)
	(subvec row-ctr start end)))
	
### Implementation

Or, Bad Ideas

Using `doall`.
