This repository contains the initial stage of a student project to build a clone of the AirBnB website. This stage implements a backend interface, or console, to manage program data. Console commands allow the user to create, update, and destroy objects, as well as manage file storage. Using a system of JSON serialization/deserialization, storage is persistent between sessions.

How To Use
First clone this repository.

Once the repository is cloned locate the "console.py" file and run it as follows:

➜  AirBnB_clone_v2 git:(master) ✗ ./console.py
When this command is run the following prompt should appear:

(hbnb)
This prompt designates that you are in the "HBnB" console. There are a variety of commands available within the console program.

Supported Commands
These are commands that can be executed by the command interpreter. They have the format command [argument]... but you could also use the format Model.command([argument]...), with the exception of the first 3 commands below.

Format	Description
help [command]	Prints helpful information about a command (command). If command is not provided, it prints the help menu.
quit	Closes the command interpreter.
EOF	Closes the command interpreter.
create Model [prop_key=prop_value]...	Creates a new instance of the Model class with the given properties. prop_value can be a double-quoted string with double-quotes escaped and spaces replaced with underscores. prop_value can also be a float or integer.
count Model	Prints the number of instances of the Model class.
show Model id	Prints the string representation of an instance of the Model class with the given id.
destroy Model id	Deletes an instance of the Model class with the given id.
all [Model]	Prints a list containing the string representation of all instances of the Model class. Model is optional and if it isn't provided, all the availble objects are printed.
update Model id attr_name attr_value	Updates an instance of the Model class with the given id by assigning the attribute value attr_value to its attribute named attr_name. Attributes having the names __class__, id, created_at, and updated_at are silently ignored.
update Model id dict_repr	Updates an instance of Model having the given id by storing the key, value pairs in the given dict_repr dictionary as its attributes. The keys __class__, id, created_at, and updated_at are silently ignored.
Supported Models
These are the models that are currently available.

Class	Description
BaseModel	A(n abstract) class that represents the base class for all models (all models are instances of this class).
User	Represents a user account.
State	Represents the geographical state in which a User lives or a City belongs to.
City	Represents an urban area in a State.
Amenity	Represents a useful feature of a Place.
Place	Represents a building containing rooms that can be rented by a User.
Review	Represents a review of a Place.
Environment Variables
HBNB_ENV: The running environment. It can be dev or test.
HBNB_MYSQL_USER: The MySQL server username.
HBNB_MYSQL_PWD: The MySQL server password.
HBNB_MYSQL_HOST: The MySQL server hostname.
HBNB_MYSQL_DB: The MySQL server database name.
HBNB_TYPE_STORAGE: The type of storage used. It can be file (using FileStorage) or db (using DBStorage).
Examples
Primary Command Syntax
Example 0: Create an object
Usage: create <class_name>

(hbnb) create BaseModel
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb)
Example 1: Show an object
Usage: show <class_name> <_id>

(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959),
'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
(hbnb)
Example 2: Destroy an object
Usage: destroy <class_name> <_id>

(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
** no instance found **
(hbnb)
