# Order Rail: Online Food Order Processing System

A Data Structures lab project that processes online food orders using a **queue (FIFO)**.
Orders are always prepared in the exact order they were received.

**Live demo:** https://rajvardhandeore04-cpu.github.io/Order-Rail-food-order-queue/

---

## Table of Contents
1. [About the Project](#about-the-project)
2. [Problem Statement](#problem-statement)
3. [Features](#features)
4. [Data Structure Used](#data-structure-used)
5. [Queue Operations](#queue-operations)
6. [How It Works](#how-it-works)
7. [Tech Stack](#tech-stack)
8. [Project Structure](#project-structure)
9. [How to Run](#how-to-run)
10. [Deploy on GitHub Pages](#deploy-on-github-pages)
11. [Screenshots](#screenshots)
12. [Sample Console Output](#sample-console-output)
13. [Future Scope](#future-scope)
14. [Author](#author)

---

## About the Project
Order Rail simulates the order desk of an online restaurant. Customers place orders, the kitchen
prepares them one by one, and finished orders are displayed in a completed list. The website shows
waiting orders hanging on a "rail" in queue order, with the oldest order at the front.

The project comes in two versions that use the same logic:
- a **website** (`index.html`) with a graphical interface
- a **console program** (`food_order_system.py`) in Python

## Problem Statement
Design an Online Food Order Processing System that manages incoming customer orders using a queue
data structure. Orders must be processed in the order they are received. The system should allow
order placement, order preparation status tracking, and order completion display.

## Features
- Place orders from a menu with a cart, quantities and customer name
- Waiting orders shown in queue order, with the front order marked "Next up"
- Kitchen panel to start the next order and mark it completed
- Track any order by its number (Placed, Preparing or Completed, plus how many orders are ahead)
- Completed orders list with the total time each order took
- Live counts of waiting, preparing and completed orders
- Data saved in the browser, light and dark mode, works on mobile

## Data Structure Used
**Queue (First In, First Out)**, implemented as a **linked list** with `front` and `rear` pointers.

A queue is the natural choice here because the first customer to order must be the first to be
served. A stack would serve the newest order first, which is unfair to customers, and an array would
need shifting after every removal.

## Queue Operations

| Operation | Purpose in this project | Time complexity |
|---|---|---|
| `enqueue(order)` | Place an order (added at the rear) | O(1) |
| `dequeue()` | Start preparing the oldest order (removed from the front) | O(1) |
| `peek()` | See which order is next | O(1) |
| `isEmpty()` | Stop "Start next order" when nothing is waiting | O(1) |
| `toArray()` / display | Show all waiting orders from front to rear | O(n) |

## How It Works

```
 Customer places order
          |
          v
   enqueue (at REAR)
          |
   FRONT [ #1 | #2 | #3 | #4 ] REAR        <- waiting queue
          |
   dequeue (from FRONT)
          |
          v
     PREPARING   (one order at a time in the kitchen)
          |
          v
     COMPLETED   (shown in the completed list)
```

Order status moves through three stages: **PLACED, PREPARING, COMPLETED**.
The kitchen must finish the current order before starting the next one, so the order of service is
always first come, first served.

## Tech Stack

| Part | Technology |
|---|---|
| Website | HTML, CSS, JavaScript (single file, no libraries) |
| Console version | Python 3 |
| Hosting | GitHub Pages |

## Project Structure

```
Order-Rail-food-order-queue/
├── index.html              Website (queue, interface and logic)
├── food_order_system.py    Console version of the same system
├── README.md               Project documentation
└── screenshots/            Screenshots used in this README
```

## How to Run

**Website**
1. Download or clone the repository.
2. Open `index.html` in any browser. No installation or build step is needed.

**Console version**
```bash
python food_order_system.py          # interactive menu
python food_order_system.py demo     # automatic demo
```


| Place an order | Waiting queue | Kitchen and tracking |
|---|---|---|
| ![Place order](<img width="889" height="476" alt="Screenshot 2026-10-15 220526" src="https://github.com/user-attachments/assets/51151e5e-fd9c-476e-8d09-7b8c17339fd8" />
.png) | ![Queue](<img width="889" height="490" alt="Screenshot 2026-10-15 221038" src="https://github.com/user-attachments/assets/66dd764d-d60b-44f9-b9d4-fb59f1fc15c7" />
.png) | ![Kitchen](<img width="890" height="493" alt="Screenshot 2026-10-15 221015" src="https://github.com/user-attachments/assets/2a6cbe82-bb68-40ef-babe-4735103bffb5" />
.png) |

## Sample Console Output

```
Order #001 placed for Asha. Position in queue: 1
Order #002 placed for Rohan. Position in queue: 2
Order #003 placed for Meera. Position in queue: 3

--- Pending Orders (front -> rear) ---
Order #001 | Asha       | Margherita Pizza, Coke         | PLACED
Order #002 | Rohan      | Veg Burger, Fries              | PLACED
Order #003 | Meera      | Paneer Wrap                    | PLACED
Order #003: PLACED (2 order(s) ahead)
Preparing Order #001 for Asha.
Order #001 completed.
Preparing Order #002 for Rohan.
```

## Future Scope
- Priority orders using a priority queue
- Several kitchen stations preparing orders in parallel
- Estimated waiting time for each order
- Saving orders in a database so they are shared across devices

## Author
- **Name:** Rajavdhan Deore
- **Roll No.:** 32119
- **Class / Division:** S.E [A]
- **Subject:** Data Structures (DS) Lab
- **College:** DYPCOEI
