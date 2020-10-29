# Cachematrix
> CacheMatrix <-function(matrix())
+ m <-NULL
+       set <-function(y) {
+            x <<-y
+           y<<-NULL
}
+ get <-function() x
+ setinverse <-function(inverse) m <<- inverse
+ getinverse <-function() m
+ list(set = set,get = get,
                 setinverse = setinverse,
                 getinverse = getinverse)
+ }
> 
> cachesolve <- function(x,...) {
+ m <- x$getinverse()
+           if(!ls.null(m)) {
+               message("getting cache data")
+               return(m)
+           }
+           data <- x$get()
+           m <- slove(data,...)
+           x$setinverse(m)
+           m
+ }
>
