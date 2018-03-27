# install django
> pip install django

# create a project
> django-admin startproject mysite

# create polls folder
> python manage.py startapp polls

# run on http://localhost:8000
> python manage.py runserver

# create the migrations (generate the SQL commands)
> python manage.py makemigrations polls

# run the migrations (execute the SQL commands)
> python manage.py migrate

# open python shell
> python manage.py shell

# populate database
> import django
> django.setup()
> from polls.models import Question, Choice
> from django.utils import timezone

> q = Question(question_text="What's your name?", pub_date=timezone.now()) # create an question object
> q.save() # insert into database
> Question.objects.all() # select all

> q = Question.objects.get(pk=1)
> q.choice_set.create(choice_text='Bob', votes=0) # create choice
> q.save() # insert into database

> exit()

# create admin
> python manage.py createsuperuser

# link of admin page: http://localhost:8000/admin
