# ml-engineer

# Challenge

For the top 10 users (with more checkins) build:
- A basket of recommendation: venues (places)
- A list of likely venues (places) the user will visit based on their friends.
- Where they will go next (with probability scores).

For the top 10 more “social” users (with more friends)
- Draw the path (with map) of a week/month of users checkins.
- List your friends and how close they are in terms of “taste” (based on venues visited and ranked)

# Response

1. Data munging. Observed there are dirty data which require clean up:
- socialgraph table contains user_id not in users table -> removed.
- socialgraph few users only has uni-direction relationship -> removed.
- Noticed there are some entries in checkins and ratings which does not have foreign key registered in users table -> removed.

2. Data exploration. Getting insight on state of the data
- Identify which venues has most checkins, and how many checkins.
- Identify for each venues, how many checkins often happens for same user.
- Identify if rating collection prone to abuse of single user skewing data by giving multiple rating for same venue.
- Load to DataFrame venues ratings for each users. When multiple rating found for same venue for same user, average them.
- For each venues what is global (universal) rating from all users?
- Find top 10 users with more checkins and top 10 users with more friends to answer Challenge

3. Answers
