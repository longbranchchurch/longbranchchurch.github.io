---
title: "Lazy Dora"
date: "2019-12-05"
categories: 
  - "hot-for-teacher"
tags: 
  - "bobby-boucher"
  - "cataracts"
  - "chicken-little"
  - "frisco"
  - "hamm"
  - "henny-penny"
  - "queequeg"
  - "qwerty"
  - "schlitz"
  - "short-circuit"
  - "slappy"
  - "sooey"
  - "sour-mash"
  - "traffic-cone"
  - "triple-lindy"
  - "two-factor"
  - "wahoo"
---

```
//**********************************
// Includes
//**********************************
#include <iostream.h>
#include <thread.h>

/* 
pull in Recover, OnYourSix, Stretch, Mosey, 
Burpee, BearCrawl, Merkin, PlankJack, CircleUp, 
SideStraddleHops, ImperialWalkers, SirFazioArmCircles,
SealClaps, OverheadClaps, MorrocanNightClubs, 
Plank, PartnerUp, LBCs, SixInchHold, Squats, 
SquatHold, PickleCompleted, OneHundreds, WorldWarIIs,
PicklePounders, AmericanHammers, HaveANiceDay,
CountPAX
*/
#include "Exicon.h"

using namespace std;
using namespace F3;

//**********************************
// Defines
//**********************************
#define I_WORKOUT_TIME_SECS (60 * 45)
#define I_MAX_NUMBER_OF_PAX 50

//**********************************
// Globals
//**********************************
int giOverallWorkoutTimer_secs = 0;
string gsPaxF3Names[I_MAX_NUMBER_OF_PAX];
bool gbFlagFellAndSourMashHadToFixIt = true;
bool gbPartnerCaughtUp = false;

//**********************************
// Function Prototypes
//**********************************
extern void LoadPaxNames(string sPaxNames[I_MAX_NUMBER_OF_PAX]);

void Thread_TrackTotalWorkoutTime();
void CheckForFNGs();
void WarmUpStretches();
void CircleUpExercises();
void LazyDora();
void BearCrawlCatchMeIfYouCan();
void Mary();

//**********************************
// Function Definitions
//**********************************

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  main
Arguments:      None
Return:         None
Description:    This function will hold the structure of 
                the workout and will begin at 5:30 AM.
**********************************/
void main()
{
    // start workout timer
    thread WorkoutTimer(Thread_TrackTotalWorkoutTime);
    WorkoutTimer.detach();
    
    LoadPaxNames(gsPaxF3Names);
    
    if(CheckForFNGs() == true)
    {    cout << "Sorry for Frisco, we are open to " <<
            "all men but we are looking " << 
            "into alternatives" << endl;
    }
    
    cout << "Our mission is to plant, grow and serve" << 
        " small workout groups for men for the " << 
        "invigoration of male community leadership." << endl;
        
    WarmUpStretches();
    Mosey("AroundTheSchool");
    CircleUpExercises();
    Mosey("KellyRoadParkPicnicShelter");
    LazyDora();
    BearCrawlCatchMeIfYouCan();
    Mosey("BackToTheSchool");
    Mary();
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  Thread_TrackTotalWorkoutTime
Arguments:      None
Return:         None
Description:    This function will simply count seconds
                up until we pass total desired workout 
                time then exit.
**********************************/
void Thread_TrackTotalWorkoutTime()
{
    while(giOverallWorkoutTimer_secs < I_WORKOUT_TIME_SECS)
    {
        sleep(1);
        giOverallWorkoutTimer_secs++;
    }
    
    cout << "Have a Nice Day!!" << endl;
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  CheckForFNGs
Arguments:      None
Return:         bool - true if there is a man who 
                    has never attended an F3 workout 
                    before, otherwise return false
Description:    This function will check to see if 
                we have any FNGs
**********************************/
void CheckForFNGs()
{
    bool bFNGPresent = false;
    
    for(int iCount = 0; iCount < CountPAX(); iCount++)
    {
        // if one of the Pax doesn't have an F3 name yet
        if(gsPaxF3Names[iCount] == "")
        {    
            bFNGPresent = true;    
            break;
        }
    }
    
    return bFNGPresent;
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  WarmUpStretches
Arguments:      None
Return:         None
Description:    This function will warm up our legs
**********************************/
void WarmUpStretches()
{
    string asStretches[3] = {"Knee2Chest", "ITBand", "Heel2Butt"};
    
    OnYourSix();
    
    for(int iCount = 0; iCount < 3; iCount++)
    {
        Stretch(asStretches[iCount], "Left", 10);
        Stretch(asStretches[iCount], "Right", 10);
        Stretch(asStretches[iCount], "Left", 10);
        Stretch(asStretches[iCount], "Right", 10);
        
        if(asStretches[iCount] == "ITBandStretch")
        {    Recover();    }
    }
    
    GoodMornings(4);
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  CircleUpExercises
Arguments:      None
Return:         None
Description:    This function will contain the exercises 
                we do while circled up
**********************************/
void CircleUpExercises()
{
    Merkins(15);
    PlankJacks(10);
    Recover();
    
    if(gbFlagFellAndSourMashHadToFixIt == true)
    {    Burpees(10);    }

    Recover();
    SideStraddleHops(10);
    
    // true for double time speed up
    SideStraddleHops(10, true);
    
    ImperialWalkers(10);
    Recover();
    
    // now do some arm work
    SirFazioArmCircles(10, "Forward");
    SealClaps(10);
    SirFazioArmCircles(10, "Reverse");
    // OverheadClaps(10);    // don't forget to uncomment later
    MorrocanNightClubs(10);
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  LazyDora
Arguments:      None
Return:         None
Description:    This function will take us through 
                the Lazy Dora exercises
**********************************/
void LazyDora()
{
    PartnerUp();
    thread PartnerThread(StartPartner, , gPartnerCaughtUp);
    PartnerThread.detach();
    
    // you do 5, your partner does other 5 for all exercises
    for(int iCount = 0; iCount < 5; iCount++)
    {
        Merkins(10);
        while(gbPartnerCaughtUp == false)
        {    Plank();    }
        gbPartnerCaughtUp = false;
    }
    
    for(int iCount = 0; iCount < 5; iCount++)
    {
        LBCs(20);
        while(gbPartnerCaughtUp == false)
        {    SixInchHold();    }
        gbPartnerCaughtUp = false;
    }
    
    for(int iCount = 0; iCount < 5; iCount++)
    {
        Squats(30);
        while(gbPartnerCaughtUp == false)
        {    SquatHold();    }
        gbPartnerCaughtUp = false;
    }
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  BearCrawlCatchMeIfYouCan
Arguments:      None
Return:         None
Description:    Bear crawl around the track while your 
                partner does burpees
**********************************/
void BearCrawlCatchMeIfYouCan()
{
    PartnerUp();
    thread PartnerThread(StartPartner, gPartnerCaughtUp);
    PartnerThread.detach();
    
    while(!PickleCompleted())
    {
        while(gbPartnerCaughtUp == false)
        {    BearCrawl();    }
        Burpees(5);
        gbPartnerCaughtUp = false;
        Mosey("ToPartner");
    }    
}

/**********************************
Author:         Brian Newberry
Date:           December 5, 2019
Function Name:  Mary
Arguments:      None
Return:         None
Description:    Workout our core!
**********************************/
void Mary()
{
    OnYourSix();
    WorldWarIIs(10);
    
    // flag to NOT make them bigger, Wahoo might start measuring
    PicklePounders(10, false);
    
    AmericanHammers(10);
    DyingCockroaches(10);
    OneHundreds();
    
    while(giOverallWorkoutTimer_secs < I_WORKOUT_TIME_SECS)
    {    cout << "Wait for it. . ." << endl;    }

    HaveANiceDay();
}

//**********************************
```

**COT**

\-Announcements: Christmas Party, Krispy Creme, South Wake Frosty, Wendy's discount Frostys

\-Prayers and Praises: Red Ryder's job, Triple Lindy's aunt, Yahoo (not to be confused the Wahoo and his much larger biceps) and his family's adoption of Oleg, Red Ryder's friend doing chemo

\-YHC led us out in prayer. Thanks for a great start to the day gentlemen!
