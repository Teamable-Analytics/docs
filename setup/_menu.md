# Setup

Before you start, you will need to have Python 3.7, Pycharm (community version is fine), and Docker installed on your system. Once you have these, you proceed with the steps below to setup the project.

1. Go to https://repo.code.ubc.ca/
You should see an option for "team_formation". 
Select it.

2. Resolve warning by adding your SSH key.
On a Mac: You can check if there's an existing key and just add that. If not, generate one and then add it.

3. Clone the repo onto your machine locally.
On a Mac: Use "Clone with SSH" option, open a terminal and type:
% git clone git@repo.code.ubc.ca:lt/team_formation.git
On Windows: You might need to use "Clone with HTTPS" instead

4. Open the project with Pycharm, TRUST the project, and set the python interpreter to version 3.7 (to match what's on your local)
It will autorun: 
% pip install -r requirements.txt
Resolve issues if needed.
Pycharm should have an interpreter (bottom right-hand corner) that shows a virtual environment for this project (e.g., "Python 3.7 (team_formation)").

5. Get the .env file (from someone on the project already or get it from the project discord's server under "Notes/Resource") 
Put in your project's root directory.

6. Start docker.

7. Run the project.
On a Mac: In a terminal, run:
% docker -compose up -d --build
This builds all the containers. To run the project, type:
% docker -compose up 
If this works, docker should have the project running.

8. Pycharm's terminal should show the localhost address for the site.
Click that address and run the project locally on your browser.

9. In the repo, look up the file quick_start.md and read it.
Follow the instructions there to create a super user with username=123 and password=password, and leave email blank.
Follow instructions to create a course with id=31084 and name=sandboxcourse for reference later.
Create an instructor user but use this command instead:
% docker exec -it team_formation_app_1 python manage.py update_user 123
Follow the instructions to give the instructor=123 permissions to the course 31084.
Follow the instructions to set the access token for user=123 to whatever it needs to be your Canvas. You can find this by logging onto Canvas, then click Settings. If you can't see one, you can generate a new access token. You may want to write this down somewhere private and keep a record of it.

10. Go to localhost and log in as user=123 to log into the sandbox course.
Use the interface to import course data.
This should work as long as you are added to the sandbox course 31084.

# Optional Steps
1. [Additional PyCharm Setup](pycharm-setup.md)
2. [Checking Docker Logs](logs.md)
