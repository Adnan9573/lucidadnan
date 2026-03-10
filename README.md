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
