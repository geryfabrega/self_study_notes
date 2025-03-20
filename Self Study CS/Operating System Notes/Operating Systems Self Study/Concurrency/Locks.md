When you have a portion of code that is a [[critical Section]] you will use locks to to protext other threads some read and writing from a protected piece of memory that may affect another thread.

example

```
pthread_mutex_t lock;
pthread_mutex_lock(&lock);
x = x++;
pthread_mutex_unlock(&lock)
```

Remember C is not object oriented. We are not created an object above. We are creating a lock type and passing it into a pthread_mutex_lock function, all memory used in this chunk of code is off limits to other threads that request it in this time.

Other threads will wait forever until the resource is unlocked.

Proper way to initialize a lock see below

```
int rc = pyhread_mutex_init(&lock,NULL)
assert(rc == 0);
```
Always assert if lock creation fails

Locks are declared globally, only one thread holds the lock at the time.