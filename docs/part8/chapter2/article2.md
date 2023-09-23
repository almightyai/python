---
layout: default
title: Thread Synchronization Locks, Semaphores, and Conditions
parent: Working with Threads
grand_parent: Concurrency and Parallelism
nav_order: 2
---
# Thread Synchronization: Locks, Semaphores, and Conditions

In concurrent programming, thread synchronization refers to the techniques or mechanisms used to coordinate the execution of multiple threads to achieve a desired outcome without any conflicts. Python provides several synchronization primitives such as locks, semaphores, and conditions, which help ensure thread safety and prevent race conditions.

## Why Thread Synchronization is Important?

Thread synchronization is crucial when dealing with shared resources in a multi-threaded environment. Without synchronization, multiple threads may access and modify shared data simultaneously, leading to unpredictable and incorrect results. Synchronization mechanisms prevent race conditions, which occur when the final outcome depends on the interleaving of thread execution. By synchronizing threads, you can guarantee the correct order of execution and maintain data integrity.

## Locks

A lock, also known as a mutex (short for mutually exclusive), is the simplest form of synchronization mechanism provided by Python's threading module. A lock ensures that only one thread can acquire it at a time, while other threads are blocked until the lock is released.

Here's an example that demonstrates the use of locks:

```python
import threading

counter = 0
lock = threading.Lock()

def increment():
    global counter
    for _ in range(1000000):
        lock.acquire()
        counter += 1
        lock.release()

threads = []
for _ in range(5):
    thread = threading.Thread(target=increment)
    threads.append(thread)
    thread.start()

for thread in threads:
    thread.join()

print(f"Counter value: {counter}")
```

In this example, the `increment` function is called by multiple threads simultaneously to increment the `counter` variable. By acquiring the lock using `lock.acquire()` and releasing it using `lock.release()`, we ensure that only one thread can modify the `counter` at a time. The output of this program will always be `5000000` irrespective of the interleaving of thread execution.

## Semaphores

Semaphores are a more versatile synchronization primitive that allows controlling access to a certain number of resources. A semaphore maintains a counter, which can be decremented or incremented by threads depending on their resource usage. If the counter reaches zero, threads attempting to acquire the semaphore will block until it becomes non-zero.

Let's consider a scenario where you have a limited number of database connections available, and multiple threads need to use them. By using a semaphore, you can restrict the number of threads accessing the database concurrently.

Here's an example demonstrating the use of semaphores:

```python
import threading

database_semaphore = threading.Semaphore(3)  # Allow 3 concurrent connections

def use_database():
    with database_semaphore:
        # Access the database here
        print("Database connection acquired by thread:", threading.current_thread().name)
        # Perform database operations
        print("Database connection released by thread:", threading.current_thread().name)

threads = []
for i in range(5):
    thread = threading.Thread(target=use_database)
    threads.append(thread)
    thread.start()

for thread in threads:
    thread.join()
```

In this example, we create a `database_semaphore` with a maximum value of 3, meaning only three threads can acquire the semaphore simultaneously. The `use_database` function simulates accessing a database, and the `with database_semaphore` block ensures that only three threads can access the database concurrently. By using a semaphore, you can prevent overloading the database with an excessive number of concurrent connections.

## Conditions

Conditions allow threads to wait for a specific condition to become true before proceeding with their execution. A condition consists of two parts: a lock and a wait-set. Threads can wait using the `wait()` method, and they are notified or woken up by other threads using the `notify()` or `notify_all()` methods.

Consider a scenario where one thread produces data, and another thread consumes it. The consumer thread should only start consuming when there is data available and should wait when there is no data. In such cases, conditions can be used to coordinate the threads efficiently.

Here's an example demonstrating the use of conditions:

```python
import threading

data_available = threading.Condition()
data = None

def producer():
    global data
    with data_available:
        # Produce data
        data = "Hello, World!"
        print("Produced data:", data)
        data_available.notify()

def consumer():
    global data
    with data_available:
        while data is None:
            data_available.wait()
        # Consume data
        print("Consumed data:", data)
        data = None

producer_thread = threading.Thread(target=producer)
consumer_thread = threading.Thread(target=consumer)

producer_thread.start()
consumer_thread.start()

producer_thread.join()
consumer_thread.join()
```

In this example, the `producer` function produces data and notifies the consumer thread using `data_available.notify()`. The consumer thread waits for the data to become available using `data_available.wait()` and consumes it once notified. Conditions ensure that the consumer thread doesn't waste CPU cycles continuously checking for data availability.

## Conclusion

Thread synchronization using locks, semaphores, and conditions is essential when dealing with shared resources and coordinating the execution of multiple threads. By understanding and utilizing these synchronization mechanisms, you can write concurrent code that is safe, predictable, and free from race conditions. Practical examples mirroring real-world scenarios help in grasping the concepts and applying them effectively to your own code.