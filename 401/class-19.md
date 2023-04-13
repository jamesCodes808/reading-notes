# Automation

## How can you use regular expressions in Python to search for specific patterns in a string, and what is the primary library to work with them?

Regular expressions are like special codes that can help us find certain patterns in a sentence or word. They are very helpful in programming because we can use them to search through lots of text and find the parts that we want. 

In Python, we use a library called "re" to work with regular expressions. Here's how you can use regular expressions in Python:

1. First, you import the "re" library at the top of your code.
2. Next, you create a regular expression pattern that describes the pattern you want to find.
3. Then, you use the "search" function from the "re" library to look for the pattern in a string.
4. If the pattern is found, the "search" function will return the location of the first occurrence of the pattern. If not, it will return "None".
5. Finally, you can do whatever you want with the information you've found!

For example, if you wanted to find all the words in a sentence that started with the letter "s", you could use the regular expression pattern "\bs\w+" and the "search" function to find them. This would help you quickly identify all the words that start with "s" in the sentence.

## What is the purpose of the shutil library in Python, and provide an example of a common use case for file or directory management with this library?

The shutil library in Python helps us move, copy, and delete files and directories. Here's a an example of how to use shutil:

What we need:

- A computer with Python installed
- Some files and folders you want to manage
- Source and destination directories of files

Instructions:

- Import the shutil library 

```python
import shutil

```


- Specify the source and destination directories: source = '/path/to/source' and destination = '/path/to/destination'


- Use the shutil.move() method to move the files: shutil.move(source + '/filename', destination + '/filename')

- Repeat step 3 for all the files that need to be moved.

```python
import shutil

# Specify the source and destination directories
source = '/path/to/source'
destination = '/path/to/destination'

# Move the files from the source directory to the destination directory
shutil.move(source + '/file1.txt', destination + '/file1.txt')
shutil.move(source + '/file2.txt', destination + '/file2.txt')

```

## Explain one automation idea from the assigned material and describe how it can be implemented using Python’s regular expressions and shutil libraries.

One automation idea, and the first one that I saw as being useful in a real world scenario is automatically moving files. 

It can be implemented using Watchdog.observer, and Watchdog.events, regex for the identification of files and shutil for the movement of the files

In this example from 
[Super quick Python automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s) 

we can implement regex and shutil

```python
from watchdog.observer import observer
from watchdog.events import FileSystemEventHandler
# pip install watchdog 

import os
import json
import time
# regex and shutil implementation 
import re
import shutil

class MyHandler(FileSystemEventHandler):
    i=1
    def on_modified(self,event):
        new_name = 'new_file_' + str(self.i) + '.txt'
        for filename in os.listdir(folder_to_track):
            # use regex to check if filename matches pattern
            if re.match(r'file_\d+\.text', filename):
                file_exists = os.path.isfile(os.path.join(folder_destination, new_name))
                while file_exists:
                    self.i += 1
                    new_name = 'new_file_' + str(self.i) + '.txt'
                    file_exists = os.path.isfile(os.path.join(folder_destination, new_name))
                
                src = os.path.join(folder_to_track, filename)
                new_destination = os.path.join(folder_destination, new_name)
                # uses shutil to move the file
                shutil.move(src, new_destination)
                self.i += 1

folder_to_track = '/test/source_folder'
folder_destination = '/test/destination_folder'
event_handler = MyHandler()
observer = Observer()
observer.schedule(event_handler, folder_to_track, recursive = True)
observer.start()

try:
    while True:
        time.sleep(1)
except KeyboardInterrupt:
    observer.stop()
observer.join()
```

## Things I want to know more about

- I definitely want to take a deeper dive into automation using tools like watchdog, regex and shutil because as of right now, this is the path I kind of want to take with programming


>References
>
>[Python Regular Expressions Tutorial](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)
>
>[shutil](https://pymotw.com/3/shutil/)
>
>[Watchdog](https://pythonhosted.org/watchdog/)
>
>[Automation Ideas](https://www.youtube.com/watch?v=qbW6FRbaSl0&t=69s)