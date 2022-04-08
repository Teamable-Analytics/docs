# Setup

## Dependencies

Before you start, you will need to have:

- [Python (>= 3.7)](https://www.python.org/downloads/)
- [Pycharm (community version is fine)](https://www.jetbrains.com/pycharm/download/)
- [Docker (>= 3.5.1)](https://www.docker.com/products/docker-desktop/)
- [Cisco MyVPN](https://it.ubc.ca/services/email-voice-internet/myvpn/setup-documents)

Once you have these, you proceed with the steps below to set up the project.

## Instructions

1. Go to https://repo.code.ubc.ca/. You should see an option for "team_formation". Select this.
   > You should already have access to this repository.

2. A warning should display at the top of your window, resolve this by creating and adding your SSH key to your Gitlab
   account.
   > You can check if there's an existing key and just add that.\
   > If not, generate one and then add it.
   > [Here is a helpful guide for how to do that](https://spectralops.io/blog/guide-to-ssh-keys-in-gitlab/)

3. Clone the repo onto your local machine. You will need to be connected to the UBCO vpn for this and future git
   commands to work.
   > MacOS: Use the "Clone with SSH" option.\
   > Windows: You might need to use "Clone with HTTPS" instead.
   >
   > Regardless of the approach, open your terminal and type:\
   > `git clone <REPO_LINK>` where `<REPO_LINK>` is the link given by either cloning option.

4. Open the project with PyCharm.
    1. You may be prompted to "trust" the project, core features in PyCharm will be locked until you trust the project.
    2. Pycharm should configure an interpreter (bottom right-hand corner) that shows a virtual environment for this
       project (e.g., 'Python 3.7 (team_formation)').
       > If this is not done automatically (i.e., there is no `/venv/` directory in the project), [create a new virtual environment for this project](https://www.jetbrains.com/help/pycharm/creating-virtual-environment.html).
    3. PyCharm should run `pip install -r requirements.txt` automatically, but run this manually in your terminal if you
       notice errors about uninstalled packages.
    4. Resolve any issues. *


5. Get the `.env` file from someone on the project already (or from the project discord's server under "Notes/Resource")
   .
    1. Place this in your project's root directory.


6. Start docker on your machine. It *must* be running in the background for further steps to be completed.


7. Run the project.
    1. In a terminal, run `docker-compose up -d --build`. This builds all the containers.
    2. To run the project, run `docker-compose up`. If this works, docker should have the project running.
    3. You may need to manually run migrations with `docker exec -it team_formation_app_1 python manage.py migrate`


8. PyCharm's terminal should show the localhost address for the site. Click that address and run the project locally on
   your browser.


9. In the repo, look up the file `quick_start.md` and read it.
    1. Follow the instructions there to create a super user with `username=123` and `password=password`, and leave email
       blank (just hint enter when it prompts for email).
       > It will consider `'password'` a weak password, so type `y` when it prompts to override the password validation process.
    2. Follow instructions to create a course with `CANVAS_COURSE_ID=31084` and `name=sandboxcourse` for reference
       later.
    3. Create an instructor by running:\
       `docker exec -it team_formation_app_1 python manage.py update_user 123`
       > Note that `123` here is a reference to the username of the superuser you created earlier.
    4. Follow the instructions to give `CANVAS_USER_ID=123` permissions to `CANVAS_COURSE_ID=31084`.
    5. Follow the instructions to set the access token for `CANVAS_USER_ID=123` to the access token you retrieve.
       > You can create a new Canvas access token by logging onto Canvas, then click 'Settings'.
       >
       > Generate a new access token. You may want to write this down somewhere private and keep a record of it.


10. Navigate to `localhost:8000` in your browser and log in with the following credentials:
    > Username: `123` \
    Password: `password`


11. Navigate to `localhost:8000/courses/31084/sections` and use the interface to import course data.

> This should work as long as you are added with the correct user permissions to the sandbox course (`id=31084`), and your Canvas access token has been set up correctly.

## Optional Steps

1. [Additional PyCharm Setup](pycharm-setup.md)
2. [Checking Docker Logs](logs.md)
