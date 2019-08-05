# Python Everyday 19: Coroutine

No thread-locks, no thread switching, amazing effective execution efficiency, that's why you feel hard to say don't like the Coroutine. Today, we write a consumer and a producer to get memory usage logs by using coroutine, code as follow:

```
import psutil
import time


def consumer():
    while True:
        memo_per = yield
        now = int(round(time.time() * 1000))
        record_time = time.strftime('%Y-%m-%d %H:%M:%S',
                                    time.localtime(now / 1000))
        print(f"Status: memo_per = {memo_per} | {record_time} ")

        time.sleep(1)


def producer(c):
    # start coroutine
    c.__next__()

    # produce memo
    while True:
        memo_per = psutil.virtual_memory().percent
        c.send(memo_per)

    # close coroutine
    c.close()


if __name__ == '__main__':
    c = consumer()
    producer(c)
    

# Outputs:
'''
Status: memo_per = 63.4 | 2019-08-05 15:15:03 
Status: memo_per = 63.4 | 2019-08-05 15:15:04 
Status: memo_per = 63.4 | 2019-08-05 15:15:05 
Status: memo_per = 63.4 | 2019-08-05 15:15:06 
Status: memo_per = 63.0 | 2019-08-05 15:15:07 
Status: memo_per = 63.0 | 2019-08-05 15:15:08 
Status: memo_per = 62.9 | 2019-08-05 15:15:09 
Status: memo_per = 63.0 | 2019-08-05 15:15:10 
Status: memo_per = 63.0 | 2019-08-05 15:15:11 
Status: memo_per = 63.2 | 2019-08-05 15:15:12 
Status: memo_per = 63.6 | 2019-08-05 15:15:13 
Status: memo_per = 63.6 | 2019-08-05 15:15:14 
Status: memo_per = 63.6 | 2019-08-05 15:15:15 
Status: memo_per = 63.6 | 2019-08-05 15:15:16 
Status: memo_per = 63.6 | 2019-08-05 15:15:17
'''
```