# Document your edge case here
- To get marks for this section you will need to explain to your tutor:
1) The edge case you identified

- When creating a student via POST /students, the request body may be missing
the `name` or `course` fields, or they may be empty strings. The spec does
not explicitly define what should happen in this scenario.

2) How you have accounted for this in your implementation

- In the `create_student` route in `app.py`, I added validation to check that
both `name` and `course` are present and non-empty before inserting into the
database. If either is missing or empty, the API returns a 404 status code
with the message "Name and course are required".

- Without this check, the database would receive null or empty values, resulting
in meaningless student records that cannot be identified or used. This keeps
the data clean and consistent.
