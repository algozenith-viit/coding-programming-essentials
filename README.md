# Coding and Programming Essentials

## Code Editor Setup

Before diving into coding, make sure you have the necessary compilers and interpreters set up for your preferred programming languages. Below are links to download and set them up:

### C/C++ Compiler (MinGW)

- Download MinGW for C/C++: [MinGW](https://sourceforge.net/projects/mingw/)
- Follow the instructions to install MinGW and configure your environment variables for compilation in C/C++.

### Python Interpreter

- Download Python (version 3.13.0): [Python 3.13.0](https://www.python.org/ftp/python/3.13.0/python-3.13.0-amd64.exe)
- During installation, make sure to check the box to add Python to your `PATH`.

### Java Development Kit (JDK)

- Download JDK for Java: [Oracle Java](https://www.oracle.com/in/java/technologies/downloads/)
- Follow the setup instructions to install and configure the Java environment.

### Visual Studio Code (VS Code)

We recommend using **Visual Studio Code** as a code editor for all your programming needs:

- Download VS Code: [VS Code Download](https://code.visualstudio.com/)

## Extensions for VS Code

To enhance your development experience, install these extensions in VS Code:

- **[Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)**: Quickly run snippets of code.
- **[Project Dashboard](https://marketplace.visualstudio.com/items?itemName=DanielVarentsoff.vscode-dashboard-window-colors)**: Manage multiple projects seamlessly.
- **[CPH](https://marketplace.visualstudio.com/items?itemName=DivyanshuAgrawal.competitive-programming-helper)**: Automate test case creation and validation (useful for competitive programming).
- **[To Do Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)**
You can explore more helpful extensions for your needs as you grow in coding and problem-solving.

---

## Git and GitHub

Version control is an essential skill for every programmer. To get started with Git and GitHub, follow the steps below:

1. Create a GitHub account: [GitHub Signup](https://github.com/)
2. Download Git: [Git Download](https://git-scm.com/downloads)
3. Set up Git with your email and username:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

4. Follow this [GitHub setup guide](https://docs.github.com/en/get-started/quickstart/set-up-git) to clone, commit, and push your code to repositories.

---

# Top 5 DSA Projects with Ready-to-Use Source Code

Now that we understand the importance of Data Structures and Algorithms (DSA), let’s explore the top 5 DSA projects with ready-to-use source code. These projects cover a range of data structures and algorithms, providing an excellent opportunity to practice and enhance your skills.

## Project 1: Snakes Game (Arrays)

The **Snakes Game** project is a classic implementation of the popular game Snake. It involves using arrays to represent the game’s grid and manipulating the snake’s position based on user input. This project helps you understand the concepts of arrays, loops, and conditional statements. You can further enhance the game by incorporating additional features such as score tracking and power-ups.

### Code Snippet

```c
void setup(void) {
    setlocale(LC_ALL, "");
    initscr(); cbreak(); noecho();
    nonl();
    intrflush(stdscr, FALSE);
    keypad(stdscr, TRUE);
    timeout(0);
    curs_set(0);
    getmaxyx(stdscr, height, width);
    width = (width + 1) / 2;
    snk = new_node(width / 2, 0, NULL);
    len = 1;
    dir = DOWN;
    do {
        food_x = rand() % width;
        food_y = rand() % height;
    } while (snk->x == food_x && snk->y == food_y);
    gameover = false;
    srand(time(0));
}
```

---

## Project 2: Cash Flow Minimizer (Graphs/Multisets/Heaps)

The **Cash Flow Minimizer** project focuses on solving a cash flow optimization problem using graphs, multisets, and heaps. Given a set of transactions among a group of people, the objective is to minimize the total number of transactions required to settle all debts. This project highlights practical applications of graph traversal algorithms such as **Dijkstra’s algorithm** and data structures like heaps and multisets.

### Code Snippet

```cpp
void minCashFlowRec(int amount[]) {
    int mxCredit = getMax(amount), mxDebit = getMin(amount);
    if (amount[mxCredit] == 0 && amount[mxDebit] == 0)
        return;
    int min = minOf2(-amount[mxDebit], amount[mxCredit]);
    amount[mxCredit] -= min;
    amount[mxDebit] += min;
    cout << "Person " << mxDebit << " pays " << min
         << " to " << "Person " << mxCredit << endl;
    minCashFlowRec(amount);
}
```

---

## Project 3: Sudoku Solver (Backtracking)

The **Sudoku Solver** project aims to solve the popular Sudoku puzzle using backtracking. It involves filling in the empty cells of a partially completed Sudoku grid while following specific rules. This project deepens your understanding of the backtracking algorithm, widely used in solving constraint satisfaction problems.

### Code Snippet

```cpp
void print(int arr[N][N]) {
    for (int i = 0; i < N; i++) {
        for (int j = 0; j < N; j++)
            printf("%d ", arr[i][j]);
        printf("\n");
    }
}

int isSafe(int grid[N][N], int row, int col, int num) {
    for (int x = 0; x <= 8; x++)
        if (grid[row][x] == num)
            return 0;
    for (int x = 0; x <= 8; x++)
        if (grid[x][col] == num)
            return 0;
    int startRow = row - row % 3, startCol = col - col % 3;
    for (int i = 0; i < 3; i++)
        for (int j = 0; j < 3; j++)
            if (grid[i + startRow][j + startCol] == num)
                return 0;
    return 1;
}
```

---

## Project 4: File Zipper (Greedy Huffman Encoder)

The **File Zipper** project implements file compression using the **Greedy Huffman Encoding Algorithm**. It compresses large files by replacing frequently occurring patterns with shorter codes. This project provides a practical application of the greedy algorithm and enhances your understanding of file handling, binary trees, and encoding techniques.

### Code Snippet

```c
image = (int**)malloc(height * sizeof(int*));
for (i = 0; i < height; i++) {
    image[i] = (int*)malloc(width * sizeof(int));
}
int numbytes = (bmpsize - bmpdataoff) / 3;
for (i = 0; i < height; i++) {
    for (j = 0; j < width; j++) {
        fread(&temp, 3, 1, image_file);
        temp = temp & 0x0000FF;
        image[i][j] = temp;
    }
}
```

---

## Project 5: Map Navigator (Dijkstra’s Algorithm)

The **Map Navigator** project aims to develop a navigation system using **Dijkstra’s algorithm**. It involves finding the shortest path between two locations on a map, considering factors such as distance and traffic. By working on this project, you will gain insights into graph representation, shortest path algorithms, and data visualization.

### Code Snippet

```cpp
void dijkstra(int graph[V][V], int src) {
    int dist[V];
    bool sptSet[V];
    for (int i = 0; i < V; i++)
        dist[i] = INT_MAX, sptSet[i] = false;
    dist[src] = 0;
    for (int count = 0; count < V - 1; count++) {
        int u = minDistance(dist, sptSet);
        sptSet[u] = true;
        for (int v = 0; v < V; v++)
            if (!sptSet[v] && graph[u][v] && dist[u] != INT_MAX
                && dist[u] + graph[u][v] < dist[v])
                dist[v] = dist[u] + graph[u][v];
    }
    printSolution(dist);
}
```

---

## Useful Links

- C++ and Python Code Editor Setup: [Visual Studio Code](https://code.visualstudio.com/)
- Python Official Documentation: [Python Docs](https://docs.python.org/3/)
- Java Official Documentation: [Oracle Java Docs](https://docs.oracle.com/en/java/)
- GitHub Basics: [GitHub Docs](https://docs.github.com/en)

<div align="center">

---

   *Authored by <a target="_blank" href="https://github.com/gautamankoji">Gautam Ankoji</a>*

</div>
