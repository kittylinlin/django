## Install django
```
 pip install django
```

## Create a project
```
django-admin startproject mysite
```

## Create polls folder
```
python manage.py startapp polls
```

## Run on [local](http://localhost:8000)
```
python manage.py runserver
```

## Create the migrations (generate the SQL commands)
```
python manage.py makemigrations polls
```

## Run the migrations (execute the SQL commands)
```
python manage.py migrate
```

## Open python shell
```
python manage.py shell
```

## Populate database
```
import django
django.setup()
from polls.models import Question, Choice
from django.utils import timezone

q = Question(question_text="What's your name?", pub_date=timezone.now()) # create an question object
q.save() # insert into database
Question.objects.all() # select all

q = Question.objects.get(pk=1)
q.choice_set.create(choice_text='Bob', votes=0) # create choice
q.save() # insert into database

exit()
```

## Create admin
```
python manage.py createsuperuser
```

## [Admin page](http://localhost:8000/admin)
