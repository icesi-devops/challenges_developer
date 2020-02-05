# Icesi-DevOps MVP

At Icesi-DevOps we are creating a new MVP, this new platform must be scalable and flexible to
support our continuous growth. We want to implement a micro-service architecture and the first
part of the project is to develop a to do web app with two sets of REST endpoints and the UI to
display the data:

  - USERS CRUD
  - USER's TASK CRUD

The user's model would look like this:
| USERS |
| ------ |
| id |
| Name |

The user tasks model would look like this:

| USER_TASKS |
| ------ |
| id |
| description |
| state (todo, done, in_progress) |
| user_id |

The requirements of this test you would need to implement to complete the technical test are:

### Frontend:
 - It must have a view to list the users.
 - It must have an option to update the users.
 - It must have an option to delete the users.
 - In the user's list, you must be able to select a single user and list its tasks
 - It must have an option to create tasks.
 - It must have an option to update tasks.
 - You may use whatever framework you wish (Angular, React, Vue or etc).

### Backend:
 - The micro-services architecture must be well defined
 - The endpoints should be a REST API
 - You can use whatever framework, the language that you are comfortable with.
 - You can use any DB that you want or use a DBaaS.

### To evaluate the technical test we need:
 - The code in a public repository like GitHub.
 - Live server running.
 - Please add a block diagram to represent the architecture.
 - A Read me file explaining how to run to tests and the servers
