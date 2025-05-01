# CODE_DHELHI_INTERNSHIP
Welcome to CodeBook – Your Data Science Internship Begins!
Introduction
Congratulations! You have just been hired as a Data Scientist Intern at CodeBook – The Social Media for Coders. This Delhi-based company is offering you a ₹10 LPA job if you successfully complete this 1-month internship. But before you get there, you must prove your skills using only Python—no pandas, NumPy, or fancy libraries!

Your manager Puneet Kumar has assigned you your first task: analyzing a data dump of CodeBook users using pure Python. Your job is to load and explore the data to understand its structure.

Task 1: Load the User Data
Your manager has given you a dataset containing information about CodeBook users, their connections (friends), and the pages they have liked.

This is how the data will look (in JSON format):

{
    "users": [
        {"id": 1, "name": "Amit", "friends": [2, 3], "liked_pages": [101]},
        {"id": 2, "name": "Priya", "friends": [1, 4], "liked_pages": [102]},
        {"id": 3, "name": "Rahul", "friends": [1], "liked_pages": [101, 103]},
        {"id": 4, "name": "Sara", "friends": [2], "liked_pages": [104]}
    ],
    "pages": [
        {"id": 101, "name": "Python Developers"},
        {"id": 102, "name": "Data Science Enthusiasts"},
        {"id": 103, "name": "AI & ML Community"},
        {"id": 104, "name": "Web Dev Hub"}
    ]
}

We have to read this data and understand its structure. The data contains three main components:

Users: Each user has an ID, name, a list of friends (by their IDs), and a list of liked pages (by their IDs).
Pages: Each page has an ID and a name.
Connections: Users can have multiple friends and can like multiple pages.
Task 2: Read and Display the Data using Python
Your goal is to load this data and print it in a structured way. Use Python's built-in modules to accomplish this.

Steps:
Save the JSON data in a file (codebook_data.json).
Read the JSON file using Python.
Print user details and their connections.
Print available pages.


We have to read this data and understand its structure. The data contains three main components:

Users: Each user has an ID, name, a list of friends (by their IDs), and a list of liked pages (by their IDs).
Pages: Each page has an ID and a name.
Connections: Users can have multiple friends and can like multiple pages.
Task 2: Read and Display the Data using Python
Your goal is to load this data and print it in a structured way. Use Python's built-in modules to accomplish this.

Steps:
Save the JSON data in a file (codebook_data.json).
Read the JSON file using Python.
Print user details and their connections.
Print available pages.


Finding "People You May Know"
Now that our data is cleaned and structured, your manager assigns you a new task: Build a 'People You May Know' feature!

In social networks, this feature helps users connect with others by suggesting friends based on mutual connections. Your job is to analyze mutual friends and recommend potential connections.

Task 1: Understand the Logic
How 'People You May Know' Works:
If User A and User B are not friends but have mutual friends, we suggest User B to User A and vice versa.
More mutual friends = higher priority recommendation.
Example:

Amit (ID: 1) is friends with Priya (ID: 2) and Rahul (ID: 3).
Priya (ID: 2) is friends with Sara (ID: 4).
Amit is not directly friends with Sara, but they share Priya as a mutual friend.
Suggest Sara to Amit as "People You May Know".
But there are cases where we will have more than one "People You May Know". In those cases, greater the number of mutual friends, higher the probability that the user might know the person we are recommending.

Task 2: Implement the Algorithm
We'll create a function that:

Finds all friends of a given user.
Identifies mutual friends between non-friends.
Ranks recommendations by the number of mutual friends.
