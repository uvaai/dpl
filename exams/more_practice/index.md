###  `pandas`

For more practice in pandas, [download this notebook](/autorit_student.ipynb).

### Watchlist 1

We've got friends that recommend us movies to watch, but too little time to watch it. To keep track of the suggestions, you're going to build a system for this. You're going to implement two classes for keeping track of which movies you've seen and which movies you still need to watch. For this you need to implement two classes: `Watchlist` and `Movie`. `Watchlist` is a container with two lists: `movies_to_watch` and `movies_watched`. If you add movie recommendations to the list, it's going to be added to the `movies_to_watch` list, and once you've watched a move, it will move to the `movies_watched` list. `Movie` is class containing the relevant information of the movie. In our case: the name of the movie, the duration, and the director.

The following UML describes the relation between the classes:

![](umls\movies1.png)

`Watchlist` needs to implement the following methods:
    `__init__()`: set up the relevant instance variables.
    `add_movies(movie_list)`: add a list of movies that you still need to watch.
    `watch_movie(movie_name)`: enter the name of the movie you've watched. If it can be found in the `movies_to_watch` list, it will have to be transfered to `movies_watched`.
    `print_status()`: prints both the list of movies still to watch and movies to watch on two separate lines.

`Movie` only has one method:
    `__init__(name, duration, director)`: create a new object with the information provided by the parameters: name, duration, director.

> Tip: Don't forget the `self` parameter of each method when implementing this.

Have a look a this example:

    watchlist = Watchlist()
    watchlist.add_movies([Movie("Pulp Fiction", 154, "Quentin Tarantino"),
                          Movie("Barry Lyndon", 185, "Stanley Kubrick"),
                          Movie("Luca", 95, "Enrico Casarosa"),
                          Movie("Gone with the Wind", 238, "Victor Fleming")])
    watchlist.add_movies([Movie("Volver", 121, "Pedro Almodóvar"),
                          Movie("The Shining", 115, "Stanley Kubrick")])
    watchlist.print_status()
    print()

    watchlist.watch_movie("Volver")
    watchlist.watch_movie("Luca")
    watchlist.print_status()

This should give the following result:

    Still to watch: Pulp Fiction, Barry Lyndon, Luca, Gone with the Wind, Volver, The Shining
    Already watched:

    Still to watch: Pulp Fiction, Barry Lyndon, Gone with the Wind, The Shining
    Already watched: Volver, Luca

> Note that there is no test for this question

### Watchlist 2

We'd like to extend the code in two ways:

1. It could be nice to know how many hours of movies we've already watched and how many hours of watch time we still have ahead of us. For this we'd like to add the following methods: `total_duration_to_watch()` and `total_duration_watched()`.
2. Sometimes we organize thematic movie evenings in which we watch everything of one director. After such an evening, in stead of marking each movie off individually using `watch_movie`, it'd be convenient to be able mark all movies of a director at once. For this you need to implement the method: `watch_all_movies_of_director(movie_director)`.

You will get the following UML:

![](umls\movies2.png)

With the following testing code, added to what you already had:

    print(f'Total duration all movies still to watch: {watchlist.total_duration_to_watch()}')
    print(f'Total duration of all watched movies: {watchlist.total_duration_watched()}')
    print()

    watchlist.watch_all_movies_of_director("Stanley Kubrick")
    watchlist.print_status()
    print(f'Total duration all movies still to watch: {watchlist.total_duration_to_watch()}')
    print(f'Total duration of all watched movies: {watchlist.total_duration_watched()}')

You should get the following output:

    Total duration all movies still to watch: 692
    Total duration of all watched movies: 216

    Still to watch: Pulp Fiction, Gone with the Wind
    Already watched: Volver, Luca, Barry Lyndon, The Shining
    Total duration all movies still to watch: 392
    Total duration of all watched movies: 516

> Note that there is no test for this question
