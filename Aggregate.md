# Aggregate

#### model 
```
from cmath import pi
from django.db import models

class City(models.Model):
    name = models.CharField(max_length=100)
    population = models.IntegerField()

    def __str__(self):
        return self.name 
        
 ```
 ### Aggregate

```
from django.db.models import Sum, Min, Max, Avg

City.objects.aggregate(Sum('population'))
City.objects.aggregate(Avg('population'))
pop = City.objects.aggregate(average_pop=Sum('population')) # assign name
City.objects.aggregate(Sum('population'), Min('population'))


