# password-management-system
ALX Portfolio project
he task involves building a mini password manager app that keeps records of your password information from different platforms. The project is broken into 4 different phase which involves:

### UI SETUP

Firstly, I created the window and the canvas UI, and placed a password image using the `canvas.create_image` attribute, then padded the image on the x and y coordinate by 20mm each using the `window.config` method.

### Adding labels to the UI

Next step is to add the `Website`, `Email`, and `Password` label. This would be achieved with the `Label` method, and the `grid` geometry system to arrange the label. The code is shown below:



### Adding Entries to UI

We are going to add the box spaces for each label using the `Entry` method on `tkinter` , the code is shown below:


### Adding `Add` and `Generate Password` Buttons

We are going to add buttons on the UI of our password manager, that enables us to easily use the functionality of generating password and adding our password information to a file. The `Buttton` method and the `grid` packing system would be used.



## Adding the `Save Password` functionality

to add the save password functionality, I wrote a function `save` which collects data about the `website` , `email`, and `password` from the user and puts it in a dictionary called `new_data`, as shown in the code block below:



then I decided to save this data into a json format using the `json` library on python. Firstly I used an if statement to check if any content was put into the field by the user, if no content was put into the field, an error message pops up revealing to the user to make sure he puts in a content in the field, and an else statement to open to read a file called `data.json` to be sure the content is saved in the file, the reason why an `exception` was used in the code was to ensure that if the file `data.json` doesnt exist (since it doesnt exist and we are trying to read the file, the progran would give a `FileNotFoundError` ), so I used the exception to catch the error and ensure that if that line of code fails, the program moves to the `except` code block and writes a json file using the `dump` method in the json library, it dumps the content `new_data` into the `data.json` file, then the code goes to the `finally` code block ,which runs no matter what happens, and delete the content in the entries. The code is written below:


## Adding the password generator functionality

a function called `generate_password` was written to achieve this part of the password management system, as shown in the code below:


## Search functionality

the function `find_password` was used to achieve this, we used the `website` as a pivot to our searching for the details, we used the try and except statement to catch the `FileNotFoundError` incase the file `data.json` doesnt exist. then if the file exists, the code runs to the else statement and search if the website is in the opened file, if it exists, the programs pops out the email and password on the screen. and another nested else statement is used to pop up an error message if the website is not available in the  opened json file.


```

The search button is also added to the functionality and the function `find_password` is attached to the search button putting the name of the function in the argument `command`.

```
search_button = Button(text="Search", width=10, command=find_password)
search_button.grid(row=1, column=2)
```



## Code Output

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b7d948c8-2831-4779-a2fc-485596ff23f5/Untitled.png)

## Data (JSON) File.
