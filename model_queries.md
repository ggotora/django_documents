## Model Queries

#### One to Many models
``` from django.db import models

class Language(models.Model):
    name = models.CharField(max_length=30)

    def __str__(self):
        return self.name

class Framework(models.Model):
    name = models.CharField(max_length=30)
    language = models.ForeignKey(Language, on_delete=models.CASCADE)
    def __str__(self):
        return self.name
```
#### Queries 

```
        
all_languages = Language.objects.all()
python_frameworks = Framework.objects.filter(language__name="Python")
python_frameworks_starts = Framework.objects.filter(language__name__startswith="Py") # like 

# reverse lookup parent from child
languages = Language.objects.filter(framework__name="Django") # returns queryset
django = Language.objects.filter(framework__name="Django").get() # gets one and gives error if not found
```

#### Many to Many
 ```
 class Movie(models.Model):
    name = models.CharField(max_length=50)

    def __str__(self):
        return self.name 

class Character(models.Model):
    name = models.CharField(max_length=30)
    movies = models.ManyToManyField(Movie)

    def __str__(self):
        return self.name 
   
  ```
  #### Quries 
  ```
  
  ```
  avengers = Movie(name="Avengers")
  avengers.save()
  captain_america = Character(name="Captain America")
  captain_america.save()
  captaine_america,
  captain_america.save()
  captain_america.movies.add(avengers)
  gilbert = Character(name="Gilbert")
  gilbert.save()
  gilbert.movies.add(avengers)
 
  # update 
   gilbert.name = "Captain Gile"
   gilbert.save()
   alice = Character(name="Alice")
   alice.movies.create(name="Alice in Wonderland")
  ```
  
