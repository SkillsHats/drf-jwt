## Django REST Framework JWT Example


#### Running the Project

First, clone the repository to your local machine:
```
git clone https://github.com/SkillsHat/drf-jwt.git
```

Install the requirements:

```
pip install -r requirements.txt
```

Apply the migrations:
```
python manage.py migrate
```

Finally, run the development server:
```
python manage.py runserver
```

Create Super User

#### Token
Token Endpoint
```
127.0.0.1:8000/api/token/
```

Response should be like:
```
{
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQ1MjI0MjU5LCJqdGkiOiIyYmQ1NjI3MmIzYjI0YjNmOGI1MjJlNThjMzdjMTdlMSIsInVzZXJfaWQiOjF9.D92tTuVi_YcNkJtiLGHtcn6tBcxLCBxz9FKD3qzhUg8",
    "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTU0NTMxMDM1OSwianRpIjoiMjk2ZDc1ZDA3Nzc2NDE0ZjkxYjhiOTY4MzI4NGRmOTUiLCJ1c2VyX2lkIjoxfQ.rA-mnGRg71NEW_ga0sJoaMODS5ABjE5HnxJDb0F8xAo"
}
```

Note: You can use access token for the next five minutes.
The refresh token is valid for the next 24 hours. When it finally expires too, the user will need to perform a full authentication again using their username and password to get a new set of access token + refresh token.

#### Refresh Token
Refresh Token Endpoint
```
127.0.0.1:8000/api/token/refresh/
```

Response should be like:

```
{
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTgwNTUwMjc1LCJqdGkiOiIwMGM0ZWZlZmVjZTk0ZjI4ODJmMzA1YzU4YzdiOGEwOSIsInVzZXJfaWQiOjF9.FqCse1vgWjq-wMJk_4qgxoTxvyaZwxZ2tbYgdxHFi-Y"
}
```

