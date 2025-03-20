You can use a condition variable to say "Do not do anything until somebody signals us to make up"

```
pthread_mutex_t lock = PTHREAD_MUTEX_INITIALIZER; pthread_cond_t cond = PTHREAD_COND_INITIALIZER; Pthread_mutex_lock(&lock); while (ready == 0) Pthread_cond_wait(&cond, &lock); Pthread_mutex_unlock(&lock);
```

This thread will sleep until somebody signals it to wake up

```
Pthread_mutex_lock(&lock); ready = 1; Pthread_cond_signal(&cond); Pthread_mutex_unlock(&lock);
```
If it makes up and the condition is not met. it will go back to sleep.

When it wake sup from slumber it will try and regain its lock back. if someone else has the lock it will freeze until the lock is given back to it. 