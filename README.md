# CPPND: Capstone Snake Game Example

This is a starter repo for the Capstone project in the [Udacity C++ Nanodegree Program](https://www.udacity.com/course/c-plus-plus-nanodegree--nd213). The code for this repo was inspired by [this](https://codereview.stackexchange.com/questions/212296/snake-game-in-c-with-sdl) excellent StackOverflow post and set of responses.

<img src="snake_game.gif"/>

The Capstone Project gives you a chance to integrate what you've learned throughout this program. This project will become an important part of your portfolio to share with current and future colleagues and employers.

In this project, you can build your own C++ application or extend this Snake game, following the principles you have learned throughout this Nanodegree Program. This project will demonstrate that you can independently create applications using a wide range of C++ features.

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


## CC Attribution-ShareAlike 4.0 International


Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

## Rubric criteria

1. The project demonstrates an understanding of C++ functions and control structures.

* This is shown in VectorOccupies from game.cpp. VectorOccupies uses a for each loop to iterate over a copy of a given vector and determine if any points are on the given x & y.

2. The project makes use of references in function declarations.

* In game.cpp PlaceItem on line 77 & RemoveItem on line  92 were created using pass-by-reference. Both take in a reference to a vector of SDL_Points.
By using pass-by-reference these functions are able to modify the actual vector. Pass-by-reference allows these functions to independent to what vector is passed either a food or posion.

3. Classes use appropriate access specifiers for class members.

* A new private member function has been added to snake.h. An enum on like 36 of snake.h replaced the boolean growing. This enum allows the snake to be in three different body_state phases. None is the default state when the snake is moving normally, when food is reached the GrowBody is alled on the snake and it will increase in size. The snake can be set to shrinking body_state when the new public method ShrinkBody is called.

4. Classes abstract implementation details from their interfaces.

* game.cpp functions OpenCell (line 64), VectorOccupies (81), PlaceItem (95) as well as other functions use detailed comments to ensure clear understanding of inputs and expected behavior.

5. The project uses smart pointers instead of raw pointers.

* In game.h on lines 22 & 23 you will see that two vectors are created used to store SDL_Points. Instead of holding the SDL_Points directly a shared_ptr has been used.
