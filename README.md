# CSE-303-Lab-0
##problem##
Write a Python script that does the followings.

1. Generate a list of random numbers of length 100.
2. Define three functions that calculates mean, variance and standard deviation.
    The function name should be lilke - mymean_<yourname>, myvariance_<yourname>, mystddev_<yourname>
3. Execute these functions by passing the randomly generate lists and print the result.
    The result should be printed in the following format.
     Name: <yourname>
     Mean: <mean-value>
     Variance: <variance-value>
     Standard Deviation: <stddev-value>
4. Create a visualization that shows the data points in your dataset and also show a horizontal line representing the mean value.

Do these things in a Colab Notebook and submit the link of the notebook in the private comment box.


##solution##
import random
import matplotlib.pyplot as plt

random_list=[]
#list for x-axis 
x=[]

def Farhad():
  randon_list=[]
  for i in range(100):
    #generate random number 1 to 100
    a=random.randint(1,100)
    #here we append in the list
    random_list.append(a)
  print(f'Farhad: {random_list}')

def mymean_Farhad():
  total1=0
  #doing the sum of the random_list by using a for loop
  for i in range(100):
    total1=total1+random_list[i]
    #print(total1)
    #Taking a global variable so I can access it from another function 
  global mean
  mean=total1/100
  print(f'Mean: {mean}')
  #return mean

def myvariance_Farhad(mean):
  #print(mean)
  #print(random_list)
  total2=0
  #implement the variance formula 
  for i in range(100):
    total2=total2+((mean-random_list[i])**2)
    #print(total2)
    global variance
    variance=total2/99
  print(f"Variance: {variance}")

def mystddev_Farhad(variance):
  print(f'Standard Deviation: {variance**.5}')

def implement_graph():
  #taking horizontal line which start from 0 to len of random_list
  for i in range(len(random_list)):
    x.append(i+1)
  print(x)
  #plot the value of x and random_list, 'go' means g for green o for o sape 
  plt.plot(x,random_list,'go')
  #here I draw a horizontal line of mean which strat from 1 to 100 
  plt.hlines(mean,1,100)
  plt.show


Farhad()
mymean_Farhad()
myvariance_Farhad(mean)
mystddev_Farhad(variance)
implement_graph()
