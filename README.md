# ml-engineer

# Challenge

For the top 10 users (with more checkins) build:
- A basket of recommendation: venues (places)
- A list of likely venues (places) the user will visit based on their friends.
- Where they will go next (with probability scores).

For the top 10 more “social” users (with more friends)
- Draw the path (with map) of a week/month of users checkins.
- List your friends and how close they are in terms of “taste” (based on venues visited and ranked)

# Solution

As there is difficulty where provided data seems skewed. Instead of writing standalone code, Exploratory Data Analysis for these given challenges are presented on this notebook: [ML-Engineer-Notebook.ipynb](ML-Engineer-Notebook.ipynb) Notebook

These are high level Notebook structure:

1. Perform data munging.

    Cleaning up tables from invalid entries to make sure they are not included in the corpus.

    - Table socialgraph contains user_id not in users table -> removed.
    - Table socialgraph has few users with only uni-direction friends -> removed.
    - Some entries in checkins and ratings which does not have foreign key registered in users table -> removed.

2. Load Data

    Load clean data from database which can be useful during analysis and solutioning.

3. Data Exploration and Analysis. Getting insight on state of the data.
    - Identify which venues has most checkins, and how many checkins.
    - Identify for each venues, how many checkins often happens for same user.
    - Identify if rating collection prone to abuse of single user skewing data by giving multiple rating for same venue.
    - Load venues ratings for each users. When multiple rating found for same venue for same user, average them.
    - Load venues ratings which is global rating (universally rated by all users) for each single venues.
    - Find top 10 users with more checkins and top 10 users with more friends to answer Challenge

4. Challenges for top 10 users with more checkins, build:

    4.1. Problem: A basket of venue recommendations

    4.2. Problem: A list of likely venues the user will visit based on their friends

    4.3. Problem: Where they will go next (with probability scores)

5. Challenges for top 10 more "social" users (with more friends):

    5.1. Problem: Draw path (with map) of week/month of users checkins.

    5.2. Problem: List your friends and how close they are in terms of "taste" (based on venues visited and ranked).

[Link to Notebook](ML-Engineer-Notebook.ipynb)

[Link to provided sqlite db](https://mltestpublicdata.s3-ap-southeast-1.amazonaws.com/fsdata.db.zip)
