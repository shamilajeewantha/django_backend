pip install djangorestframework
pip install djangorestframework-simplejwt
python -m pip install Django

<!-- del db.sqlite3 -->

python manage.py migrate

python manage.py runserver

Testing the Register Endpoint (POST /api/accounts/register/)

1. Open Postman
   Set Method to POST

Enter the URL:

http://127.0.0.1:8000/api/accounts/register/
Go to the Body tab → Select raw → Change type to JSON

Enter the following JSON:

{
"username": "testuser",
"email": "test@example.com",
"password": "testpassword123"
}

Click Send

Expected Response (201 Created):

{
"message": "User registered successfully"
}

Testing the Login Endpoint (POST /api/accounts/login/)

1. Open Postman
   Set Method to POST

Enter the URL:

http://127.0.0.1:8000/api/accounts/login/
Go to Body → Select raw → Change type to JSON

Enter:

{
"username": "testuser",
"password": "testpassword123"
}

Click Send

Expected Response (200 OK):

{
'message': 'Login successful',
"refresh": "your_refresh_token_here",
"access": "your_access_token_here"
}
