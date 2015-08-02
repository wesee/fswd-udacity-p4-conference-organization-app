# Udacity P4: Conference Organization App

## Table of contents

- [How to run the app locally](#how-to-run-the-app-locally)
- [How to deploy](#how-to-deploy)
- [Note] (#note)

## How to run the app locally  
1. download and install Google App Engine SDK for Python
2. cd fswd-udacity-p4-conference-organization-app
3. dev_appserver.py .
4. visit localhost:8080

## How to deploy 
1. download and install Google App Engine SDK for Python
2. cd fswd-udacity-p4-conference-organization-app
3. appcfg.py update .
4. visit udacity-conference-center.appspot.com

## Task 1: Design choices response
Session entity is implemented as a child of the Conference entity while speaker as a String in Session entity. All the fields in Session entity are of type String, except duration which is of type Integer and sessionDate of type Date.  StartTime is of type String in 24 hour notation (this will ease the order of data) where '0830' means 8:30am.  Duration is modelled as type Integer to represent the number of minutes of the session.  Session entity has an ancestor link to Conference entity.

## Task 3: Additional queries
1. getSessionsInWishlistByType(sessionType) - query for all the sessions that the user is interested in by session type
2. getSessionsByDate(dateString) - given a valid date string, return all sessions on this date

## Task 3: Query problem
This query will have two inequality filters and this will cause the "BadRequestError: Only one inequality filter per query is supported. Encountered both startTime and typeOfSession" error.
One way to solve this is using python code to do the filtering.  I implementing this with python code filtering the property of typeOfSession.  Refer to "getFavoriteSessions" endpoint for implementation.

##Note:

