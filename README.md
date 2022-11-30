# Cyclomatic Complexity Analyzer

Cyclomatic Complexity is a software metric that is used to indicate the complexity of the program.

Through this project, we will gather information through analyzing various public projects on Github,
and identify part of the code that impacts the Cyclomatic Complexity Number the most through Machine Learning.



<img width="766" alt="Screen_Shot_2022-10-20_at_2 56 29_PM" src="https://user-images.githubusercontent.com/97626684/197665715-34e22a16-06f4-40e3-81c0-12e7fc5a079b.png">

# Class Diagram
![CCA_Class_Diagram (1)](https://user-images.githubusercontent.com/112198910/204877913-a3e0fb3a-920f-4786-8e61-adc321f90350.png)

  
  First, the user will encounter the GUI of our program, which prompts them to enter a GitHub URL to a repository that they wish to analyze, then we use the class scraper to “scrape”/clone by using GitHub API the project from GitHub. Then in the main, we read the files in the local repository that we just cloned. Next, we call the lizard API, to help us analyze the code’s cyclomatic complexity number. After that, we will delete the local file and then display the result in GUI. Things that we can expect from the GUI are CCN(cyclomatic complex number) and the number of function calls that a program uses. All statists of the program and its performance in a nice and easy way which calculate in a short amount of time.


# Setup

- Fully working Database is Required to store data. We will be using MariaDB powered by AWS
- There are several Python that will be required to run and build the program successfully.
- Use of Jupyter Notebook is recommended (https://jupyter.org/)
  - Use `pipenv run jupyter notebook` to run Jupyter inside the Pipenv environment.

These are the essential python libraries that will be needed for the program. All of them will automatically be installed
using the build instructions below.
- [Lizard](https://github.com/terryyin/lizard/): Python Library that calculates the Cyclomatic Complexity Number for the Code.
- [Flask](https://github.com/pallets/flask): Python Framework that will be used to build API to connect with the actor and with the analyzer
- ast : Parser that will be used to parse the code
- [Pandas](https://github.com/pandas-dev/pandas) : Python Library that lets you create dataframes to store data
- [pymysql](https://github.com/PyMySQL/PyMySQL) : Python Library that allows you to directly send your pandas dataframe to the database. 

### How to build
- Install `pipenv` using `pip install -U pipenv`.
- Run `pipenv update` in the working directory to synchronize the dependencies in the Pipfile.
- Run `pipenv run pyinstaller -F gui/__init__.py -n gui`. This will create an executable binary file at `dist/gui.exe`

### How to build documentation
- Follow the build instructions above.
- Run `pipenv run pdoc gui`.

# How to contribute
Follow this project board to know the latest status of the project

# Road Map
- Build an API to connect with the Actor [In Progress]
- Build an API to connect between scraper & analyzer [In Progress]
- Create new code statistics 
- Analyze Code and store data into the DB
- Get efficient amount of data for the ML process
