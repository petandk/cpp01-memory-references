*This project has been created as part of the 42 curriculum by rmanzana*

# C++ Module 01 — Memory allocation, pointers to members, references and switch statements

## Description

Second module of the 42 C++ piscine. It focuses on **memory management** in C++ (`new` / `delete`, stack vs heap), the difference between **pointers and references**, file streams, **pointers to member functions**, and the `switch` statement.

All the code follows the **C++98** standard and compiles with `c++ -Wall -Wextra -Werror -std=c++98`.

## Exercises

| Exercise | Program | Description |
|---|---|---|
| `ex00` — BraiiiiiiinnnzzzZ | `zombie` | A `Zombie` class that announces itself. `newZombie()` creates a zombie on the **heap** (it outlives the function), and `randomChump()` creates one on the **stack** (destroyed at the end of the function). Shows when to use each. |
| `ex01` — Moar brainz! | `zombie` | `zombieHorde()` allocates N zombies in a **single allocation** with `new Zombie[N]`, freed with `delete[]`. |
| `ex02` — HI THIS IS BRAIN | `zombie` | A string, a pointer to it and a reference to it: printing their addresses and values shows that a reference is just another name for the same object. |
| `ex03` — Unnecessary violence | `zombie` | `HumanA` always has a weapon, so it stores a **reference** to it; `HumanB` may not have one, so it stores a **pointer**. Changing the weapon's type is reflected in both humans. |
| `ex04` — Sed is for losers | `sed` | Copies a file to `<filename>.replace`, replacing every occurrence of a string with another, using `std::ifstream` / `std::ofstream` and without `std::string::replace`. |
| `ex05` — Harl 2.0 | `harl` | `Harl` complains at four levels (`DEBUG`, `INFO`, `WARNING`, `ERROR`). The right member function is chosen with an **array of pointers to member functions** instead of an `if / else if` chain. |
| `ex06` — Harl filter | `harlFilter` | Given a level, prints that level and all the levels above it, using a `switch` with **fall-through**. |

## Key concepts

- **Stack vs heap:** objects on the stack are destroyed automatically at the end of their scope; objects created with `new` live until `delete` is called.
- **`new[]` / `delete[]`** for arrays of objects.
- **References vs pointers:** a reference must be initialised and can never be null or reseated; a pointer can be null and can change what it points to.
- **File streams:** `std::ifstream`, `std::ofstream`, `std::getline`.
- **Pointers to member functions:** `void (Harl::*f)(void) = &Harl::debug;` called with `(this->*f)()`.
- **`switch` fall-through.**

## Instructions

Each exercise has its own `Makefile`:

```bash
cd ex04
make
./sed input.txt "old" "new"     # creates input.txt.replace
```

```bash
cd ex06
make
./harlFilter WARNING             # prints WARNING and ERROR messages
```

`make clean`, `make fclean` and `make re` are available in every exercise.

## Resources

- [cplusplus.com — `new` and `delete`](https://cplusplus.com/doc/tutorial/dynamic/)
- [LearnCpp.com — References](https://www.learncpp.com/cpp-tutorial/lvalue-references/)
- [isocpp.org FAQ — Pointers to member functions](https://isocpp.org/wiki/faq/pointers-to-members)
- [cplusplus.com — `<fstream>`](https://cplusplus.com/reference/fstream/)
