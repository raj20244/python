# python

-> First, you need to install pyrebase on your system. You can do this by typing `pip install pyrebase` or `pip3 install pyrebase` in the terminal, depending on your Python version. This will install the pyrebase library and its dependencies.
-> Second, you need to create a Firebase project and get the configuration details. You can do this by following the instructions in [this guide]. You will get a JSON object with the keys apiKey, authDomain, databaseURL, storageBucket, and messagingSenderId. You will need these values to initialize the pyrebase module in your code.
-> Third, you need to import pyrebase in your Python file and create a pyrebase object with the configuration details. You can do this by typing `import pyrebase` or `from pyrebase import pyrebase` at the top of your file, and then typing something like this:

python
config = {
  "apiKey": "your_api_key",
  "authDomain": "your_auth_domain",
  "databaseURL": "your_database_url",
  "storageBucket": "your_storage_bucket",
  "messagingSenderId": "your_messaging_sender_id"
}

firebase = pyrebase.initialize_app(config)
```

-> Fourth, you need to create an auth object from the pyrebase object. This will allow you to use the Firebase authentication methods in your code. You can do this by typing `auth = firebase.auth()` after initializing the pyrebase object.
- >Fifth, you need to write the functions for login and signup. The login function will take the email and password as input and try to sign in the user with the auth object. The signup function will take the email and password as input and try to create a new user with the auth object. You can use the `sign_in_with_email_and_password` and `create_user_with_email_and_password` methods from the auth object for this purpose. You can also use the `try` and `except` statements to handle any errors that might occur. For example, you can write something like this:

python
def login():
  email = input("Enter email: ")
  password = input("Enter password: ")
  try:
    user = auth.sign_in_with_email_and_password(email, password)
    print("Login successful")
  except:
    print("Invalid email or password")

def signup():
  print("Sign up...")
  email = input("Enter email: ")
  password = input("Enter password: ")
  try:
    user = auth.create_user_with_email_and_password(email, password)
    print("User created")
  except:
    print("Email already exists")


- >Sixth, you need to write the main logic of your program. You can ask the user if they are a new user or an existing user, and then call the appropriate function based on their answer. You can use a while loop to keep the program running until the user wants to exit. You can also use the `input` function to get the user's choice and the `lower` method to convert it to lowercase. For example, you can write something like this:

python
while True:
  ans = input("Are you a new user? [y / n / e] ").lower()
  if ans == "y":
    signup()
  elif ans == "n":
    login()
  elif ans == "e":
    print("Exiting...")
    break
  else:
    print("Invalid choice")


-> Finally, you need to save and run your Python file. You can do this by typing `python your_file_name.py` or `python3 your_file_name.py` in the terminal, depending on your Python version. You will see the output of your program in the terminal. You can also check the Firebase console to see the users that are created or signed in by your program.
