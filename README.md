# IFLS-for-dummies
Hopefully a friendly guidance to use IFLS that is easy to understand even by people who are not familiar with research activities.  

I'm writing this to get over my fear of using IFLS and start my own research. Idk whether I will actually use this data though, because I haven't seen the ✨ _hilal_ ✨ of an innovative inspiration *_sad cat noises_. Nevertheless, I hope it helps you as much as I hope this helped me <3 

I'm using Stata but I suppose you can use these dta files in R, which is free. This guidance will be using syntaxes from Stata, but i think once you get the gist (like simply how to recognize individual ID, household ID, connecting between waves/questionnaires per waves), you can use whatever you want. 

## What is IFLS and how to access it? 
IFLS stands for Indonesian Family Life Survey. Basically panel data of Indonesian households and its members. Available waves: 1993, 1997, 2000, 2007, 2014. You can read more here: [IFLS](https://www.rand.org/well-being/social-and-behavioral-policy/data/FLS/IFLS.html) I suppose if you're reading this page then you know enough about IFLS and wanting a hands-on guidance to clean the dataset and start your own analysis.

Everyone can get this data, really. You don't have to be currently affiliated with any university/research institute. They will ask about your affiliation but you can fill it with whatever institute you want, like probably the place where you got your bachelor degree, or your high school, etc. I used my yahoo mail address for it and it went perfectly fine. I received the link to download the data not long after registering and immediately got access to all the available waves.

## How tf do i start??
I suggest to download the latest waves because it's easier to study. Once you do, you'll get soooo many folders and files. Yes, it immediately frightened me (and frankly I still am). Let's see if i can calm the shit out of you.

Say we work with IFLS5. You'll see IFLS5_HH and IFLS5_CF. CF is for community facilities (i think). Mostly people work with the HH (household) files and that's what we'll do. The 2 folders we'll use the most: **Questionnaires_IFLS5_HH_PQX_Public_Eng** and **hh14_all_dta**. The former is questionnaires forms, which consists of the questions asked during the survey, and the latter is the responses stored in dta files (dta is files for use in Stata). You'd basically have to navigate between the questionnaires and the dta files constantly to understand what's going on.   

## Unique identifier
I'm not an experienced researcher so take my words with a grain of salt, k? But so far my biggest concern whenever I'm faced with a new dataset is figuring out the unique identifier of each observation. I guess it's easier if the  survey is based on individual observation, like European Social Survey (ESS), so you need to figure out only personal ID, then you're really good to go. But when a survey consists of household and individual, then be careful because you need to know also the household ID and the members of that household. Also, it's often the case that individual survey is done only for household members above a certain age, like 15 years old or over. So you might see a household with 6 members, but when you search for people from that household in the individual survey, there are only 4 individuals appear. That's probably because 1 member is 2 years old, the other is 8 years old. 

Could be even more challenging (at least for me, as of now) when it's panel survey. Panel is great because you can follow observations across waves. But to do so, you need to know how to trace the observations. My biggest fear is not knowing how to properly clean the data and not being able to connect observations across waves :") 

From my understanding, unique PERSON identifier PER WAVE is the variable called **pidlink** so, use this to merge information from the various questionnaires in each wave.   
