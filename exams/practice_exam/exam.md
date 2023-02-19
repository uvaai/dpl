# Data Processing and Representations Exam

This is a digital exam. The exam consists of programming exercises that are purely based on input, output, and calculations. You will use these exercises to show that you can write a data processing program from scratch using tools covered in this course.

During the exam, **you are allowed use the internet and the code you have written for the PDP and DPR modules**. You are obviously not allowed to message other students, so make sure any and all messaging applications are closed for the entire duration of the exam. The only allowed tools are an editor with your code, possibly with code from earlier assignments, your terminal and a browser for searching for other coding resources and documentation.

_You will not be graded on design, but only on the correctness of your code_ and whether you met the requirements. You do not have to comment your code, nor do you have to abide by any other styling rules (though this can greatly help you understand your code).

This exam consists of 3 parts. Each of the parts can be made separately and are fully independent of each other.

## Rules

- Finish all exercises in a file named `exam.py` and submit this file
- Define any functions and/or classes you write at the top of the file, and add the provided tests at the bottom of the file in order of the exercises.
- Make sure the provided tests are *all* printed (or shown) when running your program. Separate the prints for each exercise with an extra print like `print("\n=== Exercise 1 ===")`, so it is clear which output belongs to which exercise.
- Not all exercises need to be perfect to pass the exam. If you do not know how to proceed, describe what you want your code to do.
- You are allowed use the internet and the code you have written for the PDP and DPR modules
- You are *not* allowed to contact other students

*Before you leave the exam room, check with us that your submission was correctly submitted!*

# The Exam

## Part 1: OOP

You and your friends start a company with a small loan of a million dollars. To keep track of employees, their salaries, and company funds you will implement two classes: `Employee`, and `Company`. `Employee` is a class that contains all relevant information about an employee. In our case, this is their name, their salary, and their function title. The `Employee` class also has a method which can be used to change the salary and function title of an employee. The class `Company` is a container for the list of employees that are currently employed and the company balance. This class implements three different methods that can be used to add employees, pay the salary of every employee, and to print all employees with a specific function title.

The following UML describes these classes and their relation:

![](umls/company.png)

Implement `Employee` with the following methods:

- `__init__(name, salary, function_title)`: create a new instance with the information provided by the parameters
- `promote(title, salary)`: change the `function_title` and the `salary` of the `Employee` this method was called on.

Implement `Company` with the following methods:

- `__init__(balance)`: create a new instance with the balance provided in the parameters and initializes any other required instance attributes.
- `add_employee(name, salary, function_title)`: create a new employee instance using the parameters. Then add the instance to the list of employees.
- `find_employee(name)`: search the list of employees for an employee with that exact `name`. Return the `Employee` instance if found, and `None` otherwise. You may assume that all employee names are unique.
- `payout_salary()`: determine the total salary payout for one month. Print this total and subtract it from the company balance.
- `print_employees_with_title(function_title)`: print the names of all employees with a specific title (see the example below for the format).

Have a look at this example:

    trump_co = Company(1000000)

    trump_co.add_employee('Fleur Kleur', 12000, 'CEO')
    trump_co.add_employee('Stacy de Wit', 1812, 'Secretary')
    trump_co.add_employee('Bart Zwart', 2147, 'Secretary')
    trump_co.add_employee('Danielle Groen', 3540, 'Manager')
    trump_co.add_employee('Kees de Bruin', 4800, 'Sales executive')
    trump_co.add_employee('Mart van Oranje', 1990, 'Secretary')

    print(f'Started the company with: {trump_co.balance}')
    trump_co.payout_salary()
    print(f'Balance after first salary: {trump_co.balance}')

    print()
    trump_co.print_employees_with_title('Secretary')

    stacy = trump_co.find_employee('Stacy de Wit')
    print()
    print(f'Found {type(stacy)} named {stacy.name} with a salary of {stacy.salary} and with title {stacy.function_title}.')

    stacy.promote('Manager', 2900)
    print()
    print(f'{stacy.name} has been promoted to {stacy.function_title}! Her new salary is {stacy.salary}.')

    print()
    trump_co.print_employees_with_title('Secretary')

Which should give the following result:

    Started the company with: 1000000
    Salary total: 26289
    Balance after first salary: 973711

    Listing all employees with title Secretary:
    - Stacy de Wit
    - Bart Zwart
    - Mart van Oranje

    Found <class '__main__.Employee'> named Stacy de Wit with a salary of 1812 and with title Secretary.

    Stacy de Wit has been promoted to Manager! Her new salary is 2900.

    Listing all employees with title Secretary:
    - Bart Zwart
    - Mart van Oranje

## Part 2: Pandas

For this assignment you need to use the file [barca.csv](barca.csv). This file contains the results for football matches of F.C. Barcelona (from seasons 11/12 to 13/14). The file contains the following data:

    29/08/11,Villarreal,won,5,0,home
    10/09/11,Sociedad,draw,2,2,away
    17/09/11,Osasuna,won,8,0,home
    ...
    03/05/14,Getafe,draw,2,2,home
    11/05/14,Elche,draw,0,0,away
    17/05/14,Ath Madrid,draw,1,1,home

As you can see, the data fields are separated by a comma and contain the following information:

1. Date of the match
2. The opponent
3. The result: won/lost/draw
4. The number of goals for Barcelona
5. The number of goals for the opponent
6. The location: away/home

#### Exercise 1

Load the data into a `DataFrame` named `df` using `pandas`. Name the columns `'date'`, `'opponent'`, `'result'`, `'goals barca'`, `'goals opponent'`, and `'location'`. Print the dataframe and make sure your result has 114 rows and 6 columns:

             date    opponent result  goals barca  goals opponent location
    0    29/08/11  Villarreal    won            5               0     home
    1    10/09/11    Sociedad   draw            2               2     away
    2    17/09/11     Osasuna    won            8               0     home
    3    21/09/11    Valencia   draw            2               2     away
    4    24/09/11  Ath Madrid    won            5               0     home
    ..        ...         ...    ...          ...             ...      ...
    109  20/04/14  Ath Bilbao    won            2               1     home
    110  27/04/14  Villarreal    won            3               2     away
    111  03/05/14      Getafe   draw            2               2     home
    112  11/05/14       Elche   draw            0               0     away
    113  17/05/14  Ath Madrid   draw            1               1     home

    [114 rows x 6 columns]

> Hint: keep in mind that the default way pandas will load a csv is by interpreting the first row in the file as a header! The csv provided _does not_ have a header.

#### Exercise 2

Now that the `DataFrame` has been loaded, we will do some data transformations.

Create a new `DataFrame` named `goals` that, for every `'opponent'` in the dataset, shows the total number of goals F.C. Barcelona scored as well as the number of goals the opponent scored. Your result should look something like this:

                 goals barca  goals opponent
    opponent
    Almeria                6               1
    Ath Bilbao            13               7
    Ath Madrid            14               4
    Betis                 19               9
    Celta                 11               3
    Elche                  4               0
    Espanol               13               1
    Getafe                21               7
    Granada               14               5
    La Coruna              7               4
    Levante               20               2
    Malaga                19               4
    Mallorca              16               2
    Osasuna               24               5
    Real Madrid           13              11
    Santander              5               0
    Sevilla               14               6
    Sociedad              16              11
    Sp Gijon               4               1
    Valencia              14               9
    Valladolid             9               4
    Vallecano             29               1
    Villarreal            10               3
    Zaragoza              14               2

#### Exercise 3

Create a new column in `df` named `'year'`. This column should contain the year in which the match was played:

             date    opponent result  goals barca  goals opponent location  year
    0    29/08/11  Villarreal    won            5               0     home  2011
    1    10/09/11    Sociedad   draw            2               2     away  2011
    2    17/09/11     Osasuna    won            8               0     home  2011
    3    21/09/11    Valencia   draw            2               2     away  2011
    4    24/09/11  Ath Madrid    won            5               0     home  2011
    ..        ...         ...    ...          ...             ...      ...   ...
    109  20/04/14  Ath Bilbao    won            2               1     home  2014
    110  27/04/14  Villarreal    won            3               2     away  2014
    111  03/05/14      Getafe   draw            2               2     home  2014
    112  11/05/14       Elche   draw            0               0     away  2014
    113  17/05/14  Ath Madrid   draw            1               1     home  2014

    [114 rows x 7 columns]

> Hint: The dates on which these matches were played are all in the 2000's.

#### Exercise 4

Compute the difference between the number of home matches won and the amount of away matches won. Print your answer in the following format:

    Barca won 15 more games at home than away.

## Part 3: Built-in data structures

#### Exercise 1

Your friends tasked you with doing the groceries for a high tea at your new company. They have provided you with the ingredients that they require for their recipes. The ingredients for each of the recipes are stored in a dictionary with the format `{ingredient_name: (amount, units)}`; the key is the name of the ingredient, and the values are tuples containing both the amount required and the units the amount was measured in.

    recipe_banana_bread = {'banana': (3, 'pcs'), 'butter': (80, 'g'), 'baking soda': (0.5, 'tsp'), 'sugar': (150, 'g'), 'egg': (1, 'pcs'), 'flour': (200, 'g')}
    recipe_brownies = {'butter': (225, 'g'), 'sugar': (450, 'g'), 'egg': (5, 'pcs'), 'flour': (110, 'g'), 'chocolate': (140, 'g'), 'cocoa powder': (55, 'g')}
    recipe_scones = {'flour': (350, 'g'), 'baking powder': (1, 'tsp'), 'sugar': (3, 'tbsp'), 'milk': (175, 'ml'), 'vanilla extract': (1, 'tsp'), 'egg': (1, 'pcs')}
    recipe_cake = {'butter': (200, 'g'), 'flour': (200, 'g'), 'sugar': (200, 'g'), 'vanilla extract': (3, 'tsp'), 'egg': (4, 'pcs')}
    recipe_muffins = {'flour': (300, 'g'), 'baking powder': (8, 'g'), 'sugar': (150, 'g'), 'butter': (75, 'g'), 'egg': (2, 'pcs'), 'milk': (250, 'ml'), 'vanilla extract': (1, 'tsp')}

    menu = [recipe_banana_bread, recipe_brownies, recipe_scones, recipe_cake, recipe_muffins]

In order to know how much to buy of each ingredient, you are going to write a program that can combine the ingredients of a list of recipes. Write the function `combine_recipes(menu)` that takes a list of dictionaries with ingredients and combines all these dictionaries to a single dictionary with all the required ingredients (i.e. the shopping list).. The output of the function should be a combined dictionary with the format `{(ingredient_name, units): amount}`; the key is a tuple with the name of the ingredient and the unit it was measured in, and the value is the amount of the ingredient required. If the recipes have an overlap of ingredients, the quantities should, of course, be added to each other.

> Note that the keys and values of the input dictionaries are formatted differently from the output format!

Test the code by running:

    menu_total = combine_recipes(menu)

    print(menu_total)

Which should print:

    {('banana', 'pcs'): 3, ('butter', 'g'): 580, ('baking soda', 'tsp'): 0.5, ('sugar', 'g'): 950, ('egg', 'pcs'): 13, ('flour', 'g'): 1160, ('chocolate', 'g'): 140, ('cocoa powder', 'g'): 55, ('baking powder', 'tsp'): 1, ('sugar', 'tbsp'): 3, ('milk', 'ml'): 425, ('vanilla extract', 'tsp'): 5, ('baking powder', 'g'): 8}

#### Exercise 2

To prevent waste of company funds you check the pantry and find some leftover ingredients from previous high teas. Ingredients that are available in sufficient quantity do not have to be added to your shopping list.

    pantry = {('chocolate', 'g'): 140, ('banana', 'pcs'): 6, ('butter', 'g'): 500, ('sugar', 'cube'): 10, ('cocoa powder', 'g'): 200, ('strawberries', 'g'): 432, ('egg', 'pcs'): 10, ('milk', 'ml'): 1500, ('flour', 'g'): 2000}

Implement the function `check_pantry(pantry, menu_total)` that takes a dictionary containing all ingredients available in the pantry and another dictionary that contains all ingredients that are required. The function should return a new dictionary with only the ingredients, units, and amounts that should still be bought.

    shopping_list = check_pantry(pantry, menu_total)
    print(shopping_list)

Which should print:

    {('butter', 'g'): 80, ('baking soda', 'tsp'): 0.5, ('sugar', 'g'): 950, ('egg', 'pcs'): 3, ('baking powder', 'tsp'): 1, ('sugar', 'tbsp'): 3, ('vanilla extract', 'tsp'): 5, ('baking powder', 'g'): 8}

> Hint: First check whether an ingredient is present in your pantry at all. If it is in the pantry, compute how much of the ingredient you still have to purchase. If it is not in the pantry, you would need to purchase the full amount of this ingredient.
