
Intall Python, Git,sqlite3, VS Code

Create 'sqlite' folder in C: drive and paste the downloaded pre compiled binaries in that folder that will include sqlite3.def, sqlite3.dll and sqlite3.exe files.

Add C:\>sqlite in your PATH environment variable and finally go to the command prompt and issue sqlite3 command, which should display the some result. Restart command prompt or vs code if you are using terminal inside it.

Install pip in python.

Try pip command in command prompt, if its unrecognizable then set the path in environment variables of the scripts folder present in python, for example, mine is 'C:\Users\vaibh\AppData\Local\Programs\Python\Python310\Scripts'. Run the pip command after setting the path and restarting the cmd prompt.

Once you have the pip command installed on your system, run the following command to install virtualenv:
	pip install virtualenv

Create Folder 'Router Web App'

Do cd 'Router Web App' in command line and Create the database using following command: 
	sqlite3 bookstore.db

Create app.py in the root folder (which is 'Router Web App').

Run the below command for checking if you have successfully created the database or not:
	.databases
	
Create requirements.txt in the root folder.

Add the following line in the requirements.txt:
flask==1.1.2
pyjwt==2.0.0
datetime
uuid
Flask-SQLAlchemy



Create a new virtual environment with the help of the virtualenv tool, run the following command:
	virtualenv venv
	
Go to venv folder in the command line:
	cd venv

Activate virtual environment by running the following command:
	scripts\activate
	
install the python packages in the virtual env using the following command:
	pip install -r '../requirements.txt'

===================================================================================

--> sshclient.py

The above file is for runnig a command on the remote server using paramiko.
Before running the above sshclient.py, we need to setup or make sure that ssh service is running on the remote server.
For this, I installed ubuntu using WSL on my windows 10 machine.
After that I performed following steps to start ssh service:
	a) Run the command:  sudo ssh-keygen -A
	b) Edit the ssh config using the command: sudo nano /etc/ssh/sshd_config
		i) After running the above command, make sure 'PasswordAuthentication yes' is there in the sshd_config file, or else change it.
		ii)Add the line 'AllowUsers <username>'  to the bottom of the sshd_config file.(Please make sure to replace the <username> with the actual username)
	c) Start the ssh service using the command: sudo service ssh start
	d) If the ssh service is already running then run the command: sudo service ssh --full-restart
	e) Check whether the service is running using the command: service ssh status

Create the file testfile.txt on the remote server to fetch it using SFTP protocol using paramiko

Now, run the sshclient.py file to runn the command on the remote server 