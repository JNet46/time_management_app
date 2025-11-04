# Entity Relationship Diagram

Reference the Creating an Entity Relationship Diagram final project guide in the course portal for more information about how to complete this deliverable.

## Create the List of Tables

+---------------------------+
                                |          Users            |
                                +---------------------------+
                                | user_id (PK)              |
                                | name                      |
                                | email                     |
                                | password_hash             |
                                | created_at                |
                                +---------------------------+
                                      |
              +-----------------------+-----------------------+-----------------------+
              |                       |                       |                       |
(one user has many)             |          (one user has many)             |
              |                       |                       |                       |
              v                       v                       v                       v
+---------------------------+ +---------------------------+ +---------------------------+ +---------------------------+
|          Goals            | |         Habits            | |           Tasks           | |      FocusSessions        |
+---------------------------+ +---------------------------+ +---------------------------+ +---------------------------+
| goal_id (PK)              | | habit_id (PK)             | | task_id (PK)              | | session_id (PK)           |
| user_id (FK) >------------|---< user_id (FK) >------------|---< user_id (FK) >------------|---< user_id (FK)            |
| title                     | | title                     | | goal_id (FK) (optional) >-|---< task_id (FK)            |
| description               | | description               | | title                     | | start_time                |
| target_date               | | frequency                 | | description               | | end_time                  |
| status                    | | is_active                 | | is_urgent                 | | duration_minutes          |
| created_at                | | created_at                | | is_important              | +---------------------------+
+---------------------------+ +---------------------------+ | due_date                  |
        ^                             |                     | estimated_time_minutes    |
        |                             | (one habit has many)  | status                    |
        |                             |                     | created_at                |
(one goal has many tasks)             v                     +---------------------------+
        |                 +---------------------------+
        +-----------------|         HabitLogs           |
                          +---------------------------+
                          | log_id (PK)               |
                          | habit_id (FK) >-----------|
                          | completion_date           |
                          | notes                     |
                          +---------------------------+

## Add the Entity Relationship Diagram

<img src='./images/Web103-Final-Project-Time-Management-App-Schema.png' title='Entity Relationship Diagram' width='' alt='Entity Relationship Diagram' />
