volatile
thread local cache
atomic integers
monitors

double checked locking - most important


In practice ExecutorService is usually used to process many independent requests (aka transaction) concurrently, and fork-join when you want to accelerate one coherent job. +1 Fork-Join solves a specific type of problem. If you don't have this type of problem, use ExecutorService as this is what Fork-Join uses anyway.


does each java app have a separate jvm, each app is a process, does each process have separate jvm? check
