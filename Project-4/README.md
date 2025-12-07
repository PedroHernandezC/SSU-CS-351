[julia.ppm](julia.ppm)
phcarranza@vm50e3b08ddde69:~/Project-4$ ./runTrials.sh ./iota.gpu
|Vector<br>Length|Wall Clock<br>Time|User Time|System Time|
|:--:|--:|--:|--:|
|10| 0.18| 0.03| 0.13|
|100| 0.11| 0.01| 0.09|
|1000| 0.11| 0.00| 0.09|
|10000| 0.11| 0.00| 0.09|
|100000| 0.10| 0.00| 0.09|
|1000000| 0.12| 0.01| 0.10|
|5000000| 0.14| 0.02| 0.11|
|100000000| 0.70| 0.16| 0.53|
|500000000| 3.34| 0.97| 2.37|
|1000000000| 5.88| 1.26| 4.60|
|5000000000|52.17| 8.44|43.71|

Are the results what you expected? Speculate as to why it looks like CUDA isn’t a great solution for this problem.
I think this is what i expected (given I have never done something like this). Its Interesting to see the larger number of elements took a lot more time then the others. I think maybe its too many values for it to load at a given time so it looses time in the data transfer.