# lucid adnan
for the firtst problem given 
Approach 1: Hash Set (Best if Memory is Sufficient)
Idea

Use a hash table (set) to track emails that have already been seen.
While reading the file:
If email not in set → add it
If email already in set → it is a duplicate

Step-by-Step Explanation1. Initialize Data Structures:
    - seen_emails: A Hash Set to store unique emails encountered so far.
    - duplicate_emails: A Hash Set to store duplicate emails found.

2. Process Each Email:
    - For each email in the file:
        - Check if the email is already in seen_emails.
        - If yes, it's a duplicate, so add it to duplicate_emails.
        - If no, add it to seen_emails.

3. Output Duplicates:
    - After processing all emails, duplicate_emails contains the list of duplicate emails.

Example WalkthroughEmails file contains: email1@example.com, email2@example.com, email1@example.com, email3@example.com, email2@example.com

1. seen_emails = {}
2. duplicate_emails = {}

Processing emails:
- email1@example.com: Not in seen_emails, so add to seen_emails → {email1@example.com}
- email2@example.com: Not in seen_emails, so add to seen_emails → {email1@example.com, email2@example.com}
- email1@example.com: Already in seen_emails, so add to duplicate_emails → {email1@example.com}
- email3@example.com: Not in seen_emails, so add to seen_emails → {email1@example.com, email2@example.com, email3@example.com}
- email2@example.com: Already in seen_emails, so add to duplicate_emails → {email1@example.com, email2@example.com}

Output: email1@example.com, email2@example.com (these are the duplicates)

Time Complexity- Lookup and insertion in Hash Set: O(1) average case
- Processing n emails: O(n)
- Overall time complexity: O(n)

This approach efficiently handles large email datasets with minimal memory overhead.


******************************************************************************************************************************

2nd solution approach

Approach

Read the file line by line using getline() to handle large files efficiently.

Use an unordered_map<string,int> to count how many times each word appears.

Each word read from the file increments its count in the map.

2. Finding Top 10 Words

Use a min-heap (priority_queue) of size 10.

Insert each (frequency, word) pair into the heap.

If the heap size becomes greater than 10, remove the smallest element.

This ensures the heap always keeps the 10 most frequent words.

3. Output

Move heap elements into a vector.

Sort them in descending order of frequency.

Print output as: word frequency
Data Structures Used

unordered_map → for fast frequency counting (O(1) average lookup)

priority_queue → to maintain top 10 frequent words efficiently

5. Time Complexity

Reading file and counting words: O(N)

Heap operations: O(U log K)

Since K = 10, overall complexity ≈ O(N)

****************************************************************************

3rd solution approach

Approach

Read the log file line-by-line using getline() to handle large files efficiently.

Parse each line into timestamp, user, and action using stringstream.

2. Data Aggregation

Use unordered_map<string,int> to count:

User actions (userCount)

Action frequency (actionCount)

3. Tracking Maximum

While updating counts, track:

User with highest action count

Most frequent action

4. Output

Print the most active user and most common action

''''Key Features

- Single Pass: Processes logs in one pass, reducing I/O overhead.
- Efficient Hash Maps: Uses hash sets for fast lookup and insertion (O(1) average case).
- Scalable: Handles large log files with minimal memory overhead.
- Simple and Readable: Easy-to-understand code with clear logic.
.''''

