# pandemic
Opensource privacy orientated outbreak monitoring and alert apps and tools

## User journey

Alice downloads the pandemic app for iOS. Creates a profile, links her profile to facebook, linkedin and keybase. 
She can invite other users, and gives the app background location permissions.

The app keeps track of her location and other people who come close to her. 

**John**, one of Alice's co-workers has done the same. Sadly, he starts feeling ill. 
He talks to his doctor, and as he is considered high risk, does a test that comes out positive.
On the app, he registers that he has taken a test and it was positive.

All the users who have interacted with John, or someone who has interacted with John (in his graph), 
gets a notification, with instructions/recommendations depending on the specific risk factors. 

**Alice** receives a message that she should self quarantine and if possible take a test.
Her graph branches are now at a higher risk level. The result of her test is negative,
her graph branches are green again.

**Markus** doesn't know John nor Alice. But they had an hour commute on the same train as Alice. 
He recieves a warning (maybe, don't want to freak out people) but his graph reflects a slightly higher risk.

Considering posibilites that a user can notify:

- symptoms are present
- someone in their household has symptoms
- someone in their graph or that they know has had a test
- the outcome of the test
- if they have been discharged.
---

**Sara** is an epidemiologist. She is using an app that can model population risk scenarios in realtime
based on anonymous data provided by the app. She knows that the town where Markus lives has had "some" exposure
to keep an eye on. Hopefully policy makers can make better decisions with the data, But no one can reverse engineer
the data to find out who or where John is. 

## The challenge

Anonymity discovery, balancing public usefulness with privacy. Obviously max usefulness is having a record of every interaction between people, and have access to the full graph, including name and address so that you extract them and isolate them immediately in underwater detention and re-education centers.

That's why I believe that an application like this has to be: anonymous, decentralized, opensource, and keep the data from leaving the phone in the first place.

Data that we are tracking:
- Location
- Your aggregate risk score
- 

Data that could be public:
Geo data with risk/contagion levels

## Next steps

After collecting some feedback, I'd like to do a public call for ideas/help. I believe a project of this type can only be possible if it is community driven and in deep collaboration with all stakeholders.  
