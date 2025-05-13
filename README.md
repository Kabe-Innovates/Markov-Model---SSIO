# Single server with infinite capacity (M/M/1):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 12 seconds, serivice time of lathe machine follows exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](1.png)

This is a queuing model in which the arrival is Marcovian and departure distribution is also Marcovian,number of server is one and size of the queue is also Marcovian,no.of server is one and size of the queue is infinite and service discipline is 1st come 1st serve(FCFS) and the calling source is also finite.

## Procedure :

![imAGE](2.png)



## Experiment:


 
## Program
```python
# Getting Inputs
ArrivalTime = int(input("Enter the mean inter arrival time of objects from feeder (in secs) : "))
ServiceTime = int(input("Enter the mean inter service time of the Lathe Machine (in secs) : "))
TimeByRobot = int(input("Enter the time taken by the Robot (in secs) : "))

# Calculating Lambda and Mu
Lambda = 1 / ArrivalTime
Mu = 1 / ServiceTime

print(f"Value of Lambda λ : {Lambda:.3f}")
print(f"Value of Mu μ : {Mu:.3f}")

# Single Server with Infinite Capacity - (M/M/1):(∞/FIFO)
if Lambda < Mu:
    Ls = Lambda / (Mu - Lambda)
    Lq = Ls - (Lambda / Mu)
    Ws = Ls / Lambda
    Wq = Lq / Lambda
    print("Average number of objects in the system : %0.2f " % Ls)
    print("Average number of objects in the conveyor :  %0.2f " % Lq)
    print("Average waiting time of an object in the system : %0.2f secs" % Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs" % Wq)
    print("Probability that the system is busy : %0.2f " % (Lambda / Mu))
    print("Probability that the system is empty : %0.2f " % (1 - Lambda / Mu))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
```
## Output :
```
Enter the mean inter arrival time of objects from feeder (in secs) : 12
Enter the mean inter service time of the Lathe Machine (in secs) : 1
Enter the time taken by the Robot (in secs) : 5
Value of Lambda λ : 0.083
Value of Mu μ : 1.000
Average number of objects in the system : 0.09 
Average number of objects in the conveyor :  0.01 
Average waiting time of an object in the system : 1.09 secs
Average waiting time of an object in the conveyor : 0.09 secs
Probability that the system is busy : 0.08 
Probability that the system is empty : 0.92 
```
## Result :
Thsu the python program is implemented and executed successfully

