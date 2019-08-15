# Session4

# Aim:
Write your Assignment 3 again such that:
Finally after 4 code iterations achieve:
99.4% accuracy
Less than 15k Parameters
Have started from a Vanilla network (no BN, DropOut, LR, larger batch size, change in Optimizer, etc)

# Solution
What I have achieved? - with ~10k params, reached 99.4% val acc in 10 epochs! :)
How'd I achieve it? - Kindly go through the following flow of attempts at building a network.

# First Attempt - Vanilla Network
10k params (keeping less params so that I can add more if reqd-flexible)

10 epochs

Removed relu from last layer

tried 2 max pool layers

have 1x1 kernel

train acc: 0.9905 & val_acc: 0.9892 at 10th epoch

Diff in val acc and train acc in 10th epoch is 13. Will try different architecture to see if it has more scope to learn than the present network.

# 1.5th Attempt - different architecture of network
-Tried a different architecture, ~13k params

-Tried adding seperable convolution (in order to keep low param... although it has not been introduced in class)

-Only one max pool layer and ended the network when left with 7x7 and directly added a 7x7 filter at the end.

-Train acc: 0.9936 & val_acc: 0.9869 at last epoch

Difference in val acc and train acc in 10th epoch is 67. Which is more than our prev architecture. Hence, I'll proceed with the prev architecture.


# Second Attempt
Change made to our first architecture model = Added Batch Normalisation after every layer
except befor max pool and before prediction layer

Slight increase in number of params. (10.9k params)

Val acc went to 99.27 in 10th epoch. Diff between train and val acc is also very less, which says this has more scope to learn and perform better.

# Third Attempt
Change made= employed lr scheduler.
The val acc decreased and the diff between the val acc and train acc also increased a bit. 

But this is safer since we can reach the minima in the further epochs. Without the scheduler, we got a higher val acc before since it co incidently jumped closer to the minima, but if we continued with that then there will be high variations (oscillations) in val acc.

# Attempt Four
Change made- Increased batch size to 100 (multiple of 10 because 10 classes in mnist)

Introduced Dropout and trained network for 20 epochs

Reached 99.42 in 10th epoch. 

It increased to 99.45 in 19th epoch.

-----------------------------------------------------------------------------
