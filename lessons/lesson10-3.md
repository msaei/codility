## Lesson 10: Prime and composite numbers
## Flags
link to question: (https://app.codility.com/programmers/lessons/10-prime_and_composite_numbers/flags/)
for solving this problem I assume that I am a hicker and I plan to walk through the mountains. I dont know how many mountains are there and I dont know how much distance is betwean peaks and I wnat to do this in one try ( I dont wnat to go all path again since I am lazy so I should be smart and come up with a solution). the only thing I know is the length of the routh (len(A)). 
so I am gonna get my pack back my sandwich and water probably couple beers also and I will get flags in different colors and signs. since I know the length of the routh I can calculate the best distribution of the peaks to can use maximum flag for example for length of 20 I would get five flags with number 5 in it and also 4 flag with sign 4 and so on.
and I will start my hike at the morning and enjoy beauty of mountains. but I also have a misson so every time I got in a peak I would put a flag that is allowed for example if I put a flag signed 5 I have to wait 5 miles to put another one. I could put more than one flag on each peak thogh, for example in the first peak I would put one of each flags that I packed at the beginig.
when I finished my hike I will check my back pack and I will check my flag sets from more valuble one, in this case 5 signed flags, if I am out of them then that is the answer to the question, otherwise I will go to the next valuable flag set and so on.
so the solution would be like this
def solution(A):
  #create a flag set list containing number of each kind of flags
  #create a flag position list which will keep track of position of last flag
  for a in A:
    #check if a is a peak:
      #set proper flag and update flagsets and flagpos list
  #loop through flagsets backward to find most valuable flags which is used during hike
  #and return that as answer
