>Alek Hanušić
## Exercise 1.1
```r
is_arithmetic <- function(seq) {
  if(length(seq)< 2) {
    return(FALSE)
  }
  diff <-seq[2] -seq[1]
  
  for(i in 2:length(seq)) {
    if(seq[i]-seq[i-1] !=diff) {
      return(FALSE)
    }
  }
  
  return(TRUE)
}
#TEST

x=c(1,2,3,4,5,6)
is_arithmetic(x)
```


## Exercise 1.2
```r
is_geo_seq <- function(seq) {
  if (length(seq) <= 1) return(FALSE)
  ratio <- seq[2]/seq[1]
  for (i in 2:length(seq)) {
    if (seq[i] != seq[i-1] * ratio) return(FALSE)
  }
  return(TRUE)
}
#TEST

x=c(1,2,4,8,16,32,64)
is_geo_seq(x)
```

## Exercise 1.3
```r
harmonic_seq <- function(seq) {
  if (length(seq) <= 1) {
    return(FALSE)
  }
  if (all(seq > 0)) {
    reciprocals <- 1/seq
    diffs <- diff(reciprocals)
    if (all(diffs == diffs[1])) {
      return(TRUE)
    }
  } 
  return(FALSE)
}
#TEST
seq1 <- c(1, 1/2, 1/3, 1/4)
harmonic_seq(seq1)
```

## Exercise 1.4
```r
is_alternating_sequence <- function(seq) {
  if (length(seq) < 2) {
    return(FALSE)
  }
  is_alternating <- all(seq[1:length(seq)-1] * seq[2:length(seq)] < 0)
  return(is_alternating)
}
# the function then checks if the product of each adjacent 
#pair of elements in the sequence is negative.

# Testing
seq1 <- c(1, -2, 3, -4, 5)
is_alternating_sequence(seq1)
n = c(1,2,3,4,5,6,7,8,9,10,11,12,13,14)
lol = 1/(n*(n+1))
plot(lol)
```

