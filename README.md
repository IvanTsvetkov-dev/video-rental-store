# Video Rental Store

## Database design practice

_Task: Build an ERD in accordance with the requirements. Use Oracle Date Modeler_

_Requirements: Subject area Video Rental Store_

I’m the owner of a small video rental store. We have over 3000 movies that we need to keep track of. Each of our movies has a DVD or VHS tape number. For each movie, we need to know it’s title and category (e.g. comedy, suspense, drama, action, war or sci-fi).

 Yes, we do have multiple copies of many of our movies. We give each movie a specific ID, and then track which DVD or VHS contains the movie. A movie can be either DVD or VHS format.

 We always have at least one DVD or VHS tape for each movie we track, and each DVD or VHS is always a copy of a single, specific movie.

 Our DVDs and VHS tapes are very long - we don’t have any movies that require multiple DVDs or VHS tapes.

 We are frequently asked for movies starring specific actors. Mel Gibson and Julia Roberts are always popular. So we’d like to keep track of the star actors appearing in each movie. Not all of our movies have star actors. Customers like to know each actors “real” birth name and date of birth. We only track actors who appear in the movies in our inventory.

 We have lots of customers. We rent videos only to people who have joined our “video club”. For each club member, we’d like to keep their first and last name, current phone number, and current address, And of course, each club member has a membership number.

 Also, we need to keep track of what media each customer currently has checked out. A customer may check out multiple DVDs or tapes at any given time. We really need to keep a history of all our rentals. Each time a customer rents a DVD and/or tape, we would like to keep the rental date/time and keep the return date/time. All our rentals are due back the next day, so we don’t need to keep a due date.

 Keeping this rental history will allow us to analyse the patterns of our rentals. We will be able to determine how many DVD/tapes each customer rents and how many times a customer have returned a DVD or VHS late. We will also know how many times a particular DVD or tape has been used and will then know when to retire each one. We will also be able to analyse our customers overall movie preference. 

 ## My Solution:
**The points that I drew attention to in the wording:** 

1. “a small video rental store.” We are talking about a small video rental store in one city, one country. 
2. “For each film, we need to know its title and category (for example, comedy, suspense, drama, action, military or sci-fi). The category of films is fixed. This means that when creating an accessory, it is necessary to remove restrictions on this value. 
3. “Each of our films has a number on a DVD or VHS cassette.” The media type can only be DVD or VHS. This means that when creating an accessory, you must take into account the restrictions on this value.
4. “we do have several copies of many of our films.”Only one of them can be on a diverse basis. 
5. “Therefore, we would like to keep track of the star actors appearing in each film.” There can be several star actors in one film, and star actors can star in several films, therefore we are talking about a "many to many" relationship. 
6. “In addition, we need to keep track of which media each customer was currently viewing.” **IMPORTANT!!!**. Periodically, two member groups CANNOT take responsibility for pumping the same model, for which it is necessary to associate it with the need to overcome the limitations within uniqueness on the Movie_Copy key. 

_I have identified 5 categories_: Movie, Star Actor, Movie Copy, Rental, Club Member. 
**Relationships between entities:** 
1. Movie “Many to Many” Actor. 
2. Movie “One to Many” Movie Copy 
3. Movie Copy “One to Many” Rental 
4. Club Member “One to Many” Rental
## ERD
Bachman-Notation:
![Bachman_notation](https://github.com/user-attachments/assets/f67e0e83-5572-41bf-86b2-438db9351d78)

Barker-Notation:


![Barker_notation](https://github.com/user-attachments/assets/ff6eb6b8-a946-41d2-9ad1-eba7c9548f85)

## Relation-Model:

![Relational](https://github.com/user-attachments/assets/40827ee6-cdd5-4c8d-bd8d-3f84ca078cec)
