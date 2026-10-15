# Order Rail: Online Food Order Processing System

A static website that processes food orders with a **FIFO queue** (linked-list implementation).
Orders are always prepared in the order they were received.

## Features
- Place orders from a menu (cart, quantities, customer name)
- Waiting orders shown on a "rail" in queue order (front is served first)
- Kitchen panel: start the next order, mark it completed
- Track any order by number (Placed, Preparing, Completed, plus orders ahead)
- Completed orders list with total time taken
- Saves data in the browser (localStorage), light and dark mode, mobile friendly

## Run locally
Open `index.html` in a browser. No build step or dependencies.

## Deploy on GitHub Pages
1. Create a new repository on GitHub (for example `order-rail`).
2. Upload `index.html` and `README.md` to the repository root.
3. Go to **Settings > Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
5. After a minute, the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Queue operations
| Operation | Used for |
|---|---|
| `enqueue(order)` | Placing an order (added at the rear) |
| `dequeue()` | Starting preparation (oldest order leaves the front) |
| `peek()` | Checking the next order |
| `isEmpty()` | Disabling "Start next order" when nothing is waiting |
