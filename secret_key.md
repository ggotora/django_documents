## Django SECRET 

To secure django project settings.py SECRET_KEY

In  ``` settings.py  ```
``` 
import os 
from dotenv import load_dotenv
from pathlib import Path

load_dotenv()

SECRET_KEY = os.getenv('SECRET_KEY')

```
Create .env file in same folders as ``` setting.py ```