# CPPND: Capstone Snake Game Example

This is a starter repo for the Capstone project in the [Udacity C++ Nanodegree Program](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213). The code for this repo was inspired by [this](https://codereview.stackexchange.com/questions/212296/snake-game-in-c-with-sdl) excellent StackOverflow post and set of responses.

<img src="snake_game.gif"/>


## Chosen option
Extended the snake game to add some features


## class structure and expected behaviour
- The game class is composed of Snake class, Maze class and Shrinker class
- The Shrinker class aims to create a booster when the snake is large enough (apple booster to user), if the snake eats the booster it shrinks its size.
- The Shrinker booster is placed randomly and will disappear after 3 seconds if the snake didn't catch it
- The Maze class aims to place a tiny borders, if the snake hits these borders it dies.
- There are two Maze borders and they rotate every 3 seconds by 90 degree
- At the start of the game the player is requested to enter his/her name, then the player's name is displayed at the top of the game along with the score
- If the snake hits the border or hit its body a gameover notification is displayed to the user


## Dependencies for Running Locally
* cmake >= 3.7
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* SDL2 >= 2.0
  * All installation instructions can be found [here](https://wiki.libsdl.org/Installation)
  >Note that for Linux, an `apt` or `apt-get` installation is preferred to building from source. 
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)


## Basic Build Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./SnakeGame`.


## Rubric points addressed
1. The project demonstrates an understanding of C++ functions and control structures: for both classes Maze and Shrinker the functions are organised with deployment of variety of control structures.

2. The project reads data from a file and process the data, or the program writes data to a file: The project read data from bmp files used to display the shrinker boostor and gameover notification (Renderer initialiser list)

3. The project accepts user input and processes the input: At start of the game the program request the player name then pass this name to the Renderer class to display the player name at the top of the game (main.cpp line 17 and Renderer.cpp in Renderer::UpdateWindowTitle)

4. The project uses Object Oriented Programming techniques: The project code is organized into classes (Maze and Shrinker) with class attributes to hold the data (first_border and second_border for Maze class, _shrinker_point, shrinkerstart, shrinkerend for Shrinker class) and class methods to perform tasks(Maze::update_borders,Shrinker::shrink)

5. Classes use appropriate access specifiers for class members: All class data members are explicitly specified as public or private.

6. Class constructors utilize member initialization lists: Shrinker::Shrinker() and Maze::Maze(int grid_width, int grid_height)

7. Classes abstract implementation details from their interfaces: All class member functions document their effects both through function names and comments.

8. Classes encapsulate behavior:  _grid_width and _grid_height are only accessed through Maze::update_borders. 

9. Overloaded functions allow the same function to operate on different parameters: Renderer::Render is overloaded three times depending on the signature ( line 15, 16 and 20 in Renderer.h)

10. The project makes use of references in function declarations: Shrinker::shrink() line 21 in Shrinker.cpp use pass-by-reference along with Renderer::Render(std::vector<SDL_Point> const &border1, std::vector<SDL_Point> const &border2, SDL_Point const &shrinkp, int shrinkflag) which is used to render the shrinker booster and the maze ( line 100 in Renderer.cpp)

11. Classes follow an appropriate inheritance hierarchy: class Game is composed of class Maze and class Shrinker




## CC Attribution-ShareAlike 4.0 International


Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg



