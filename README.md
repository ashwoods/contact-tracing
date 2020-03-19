# pandemic

Open-source privacy orientated outbreak monitoring and alert apps and tools

## User journey

Alice downloads the pandemic app for iOS. Creates a profile, links her profile to social networks:
facebook / linkedin / twitter / keybase / instagram /etc...
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
He receives a warning (maybe, don't want to freak out people) but his graph reflects a slightly higher risk.

Considering possibilities that a user can notify:

- symptoms are present
- someone in their household has symptoms
- someone in their graph or that they know has had a test
- the outcome of the test
- if they have been discharged.
- maybe commute extras? like taking a specific plane, bus, or train?

---

**Sara** is an epidemiologist. She is using an app that can model population risk scenarios in realtime
based on anonymous data provided by the app. She knows that the town where Markus lives has had "some" exposure
to keep an eye on. Hopefully policy makers can make better decisions with the data, But no one can reverse engineer
the data to find out who or where John is.

## The challenge

Anonymity discovery, balancing public usefulness with privacy. Obviously max usefulness is having a record of every interaction between people, and have access to the full graph, including name and address so that you extract them and isolate them immediately in underwater detention and re-education centers. Having people notify people they know that they should quarantine is a good start,
but being able to also track with whom you have had contact outside of your graph would be amazingly useful.

That's why I believe that an application like this has to be: anonymous, decentralized, open-source, and keep the data from leaving the phone in the first place.

Data that we are tracking:

- Location
- aggregate risk score
- checkins
- social graph

Data that could be public:
Geo data with risk/contagion levels

First attempt at architecture:

- public AND anonymous ledger of location checkins? every unique checkin is known only to the user.
- only that user can add labels to those checkins
- only other users who have also been there (radius) can read those labels and update their own.
- people in the graph also get updated.

Asymptomatic super-spreader candidates could get notified that they should test.

- How do we avoid bots that are everywhere?

## Design

The application has two graphs

- the social graph, thats the easy classical part, similar to the trustcommunity example
- geo/time graph. your application leaves cryptographically signed breadcrumbs with your location. nothing links those breadcrumbs to you, or in between themselves.

When you do a checkin, say, I am sick, you app creates a tag along your geo/time graph whenever it encounters another node. T
The tag encrypted with the pub keys of all the nodes in that area.

You app checks your own breadcrumbs in the past X days, and if one of your nodes have been tagged along someone else, you can read it.

would want to have a PoC in a weeks time. 23.03.2019.

## Next steps

After collecting some feedback, I'd like to do a public call for ideas/help. I believe a project of this type can only be possible if it is community driven and in deep collaboration with all stakeholders.  

## Links

https://github.com/BDI-pathogens/covid-19_instant_tracing
