<div align="center">

# Mobile Shop CRUD Project

**A console-based inventory management system built in Python, demonstrating Create, Read, Update, and Delete (CRUD) operations on in-memory list data.**

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-blue)

</div>

---

## Function Reference

Click any function below to open its dedicated documentation page — covering purpose, logic breakdown, source code, and a sample run.

| Function | Operation | Documentation |
|---|---|---|
| **`add_mobile()`** | Create | [View Details →](docs/functions/add_mobile.md) |
| **`display_mobiles()`** | Read | [View Details →](docs/functions/display_mobiles.md) |
| **`search_mobile()`** | Read / Search | [View Details →](docs/functions/search_mobile.md) |
| **`update_mobile()`** | Update | [View Details →](docs/functions/update_mobile.md) |
| **`delete_mobile()`** | Delete | [View Details →](docs/functions/delete_mobile.md) |
| **`dashboard()`** | Menu Controller | [View Details →](docs/functions/dashboard.md) |

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Data Model](#data-model)
- [CRUD Mapping](#crud-mapping)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Sample Session](#sample-session)
- [Output](#output)
- [Requirements](#requirements)
- [License](#license)

---

## Overview

This project is a simple, menu-driven **Mobile Shop Management System** that runs entirely in the terminal. It allows a user to manage an inventory of mobile phones using only core Python constructs — no external libraries, databases, or frameworks.

**CRUD** stands for:

| Letter | Operation | Meaning |
|---|---|---|
| **C** | Create | Add a new mobile |
| **R** | Read | Display / Search mobiles |
| **U** | Update | Update mobile details |
| **D** | Delete | Delete a mobile |

## Features

1. Add Mobile
2. Display All Mobiles
3. Search Mobile
4. Update Mobile
5. Delete Mobile
6. Exit

## Data Model

All records are stored **in memory**, in a single Python list called `mobiles`. Each mobile is itself a list in the format:

```python
[id, brand, model, price, quantity]
```

**Example:**

```python
[101, "Samsung", "Galaxy A55", 35000, 5]
```

| Index | Field | Example Value |
|---|---|---|
| `0` | Mobile ID | `101` |
| `1` | Brand | `Samsung` |
| `2` | Model | `Galaxy A55` |
| `3` | Price | `35000` |
| `4` | Quantity | `5` |

With multiple records, the structure looks like this:

```python
mobiles = [
    [101, "Samsung", "Galaxy A55", 35000, 5],
    [102, "Apple", "iPhone 15", 65000, 3],
    [103, "OnePlus", "Nord 4", 30000, 7],
]
```

## CRUD Mapping

| Operation | Function | Underlying List Operation |
|---|---|---|
| Create | `add_mobile()` | `append()` |
| Read | `display_mobiles()` | `for` loop |
| Read / Search | `search_mobile()` | `for` loop + condition |
| Update | `update_mobile()` | Modify list elements by index |
| Delete | `delete_mobile()` | `remove()` |

## Project Structure

```
Mobile-Shop-CRUD-Project/
├── Mobile_Shop_CRUD_Project.py     # Main application file
├── README.md                       # Project documentation (this file)
└── docs/
    └── functions/
        ├── add_mobile.md
        ├── display_mobiles.md
        ├── search_mobile.md
        ├── update_mobile.md
        ├── delete_mobile.md
        └── dashboard.md
```

## Getting Started

**Prerequisites:** Python 3.10 or higher (required for `match-case` syntax).

Clone the repository and run the script:

```bash
git clone https://github.com/<your-username>/Mobile-Shop-CRUD-Project.git
cd Mobile-Shop-CRUD-Project
python Mobile_Shop_CRUD_Project.py
```

## Sample Session

```
=============================================
        MOBILE SHOP MANAGEMENT
=============================================
1. Add Mobile
 2. Display All Mobiles
 3. Search Mobile
 4. Update Mobile
 5. Delete Mobile
 6. Exit
==================================================
Enter your choice: 1

***************** ADD MOBILE ******************
Enter Mobile ID: 101
Enter Brand: Samsung
Enter Model: Galaxy A55
Enter Price: 35000
Enter Quantity: 5
Mobile added successfully.
```

## Output

Below are actual terminal runs of the application, covering every menu option end to end.

**1. Adding a Mobile**

![Add Mobile](screenshots/01_add_mobile.png)

A new mobile (`Samsung A 51`) is added successfully, and the menu reappears for the next action.

---

**2. Invalid Menu Choice**

![Invalid Choice](screenshots/02_invalid_choice.png)

Entering an out-of-range value (`13579`) is handled gracefully by the `case _:` branch in `dashboard()`, without crashing the program.

---

**3. Adding Another Mobile**

![Add Mobile Again](screenshots/03_add_mobile_again.png)

A second and third mobile (`Apple 12 pro`, `Vivo M 31`) are added, demonstrating that `add_mobile()` correctly appends multiple records to the `mobiles` list.

---

**4. Displaying All Mobiles**

![Display All Mobiles](screenshots/04_display_mobiles.png)

`display_mobiles()` prints all stored records in a clean, aligned table — confirming all three additions were stored correctly.

---

**5. Updating a Mobile**

![Update Mobile](screenshots/05_update_mobile.png)

`update_mobile()` locates the mobile by ID (`12345`), shows its current details, then overwrites them with the new brand, model, price, and quantity.

---

**6. Deleting a Mobile**

![Delete Mobile](screenshots/06_delete_mobile.png)

`delete_mobile()` locates the mobile by ID, asks for confirmation (`Y/N`), and removes it from the list upon confirmation.

## Requirements

- Python 3.10+
- No external dependencies — built entirely with core Python (lists, loops, conditionals, `match-case`)

## License

This project is released under the MIT License. Feel free to fork, modify, and use it for learning or coursework.
