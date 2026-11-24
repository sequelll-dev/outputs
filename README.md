# LabaNa Laundry Management System

LabaNa is a beginner-friendly C++ laundry management program. It helps a small laundry shop keep customer records, create laundry orders, calculate bills, and track order progress.

The project includes two separate versions:

- **Console version** — runs in a terminal.
- **Graphical version** — uses the Raylib library.

## Features

- Add, view, and delete customer records.
- Generate customer and order IDs automatically.
- Create laundry orders linked to a customer.
- Calculate the bill from the selected service rate and laundry weight.
- View orders and display an order receipt.
- Change an order status: **Received**, **Washing**, **Ready for Pick-up**, or **Claimed**.
- Delete a laundry order.
- Edit service rates.
- Validate required fields and numeric input.
- Save customers, orders, and service rates in `laundry_data.txt` so they can be loaded the next time the program starts.

## Requirements

### Console version

- A C++ compiler that supports C++17, such as `g++`.

### Raylib GUI version

- Windows
- Raylib
- A C++17 compiler
- For the included VS Code build configuration, Raylib and w64devkit should be installed at `C:/raylib`.

The VS Code build configuration uses the Raylib library and Windows libraries: `raylib`, `opengl32`, `gdi32`, and `winmm`.

## Build and run

Open the project folder in VS Code:

    C:\Users\MSI\Documents\Codex\2026-11-06\cr

### Run the console version

From the project folder, compile the console source with `g++`:

    g++ -std=c++17 outputs/laundry_management.cpp -o outputs/laundry_management

On Windows, run the resulting executable with:

    .\outputs\laundry_management.exe

If your compiler produces a different executable name or requires a `.exe` extension in the build command, adjust the command for your compiler.

### Run the Raylib GUI in VS Code

1. Open the project folder in VS Code.
2. Select **Run and Debug**.
3. Choose **Run Laundry Raylib GUI**.
4. Press **F5**.

This configuration builds `outputs/laundry_management_gui.cpp` and launches the GUI. It expects Raylib and w64devkit at `C:/raylib`.

## Data storage

The program reads and writes `laundry_data.txt` in its current working directory. The included VS Code GUI configuration sets the working directory to `outputs`, so the GUI data file is normally `outputs/laundry_data.txt`.

Keep that file if you want to retain the saved records. The two versions use the same data filename; close one version before opening the other to avoid overwriting changes made by the other version.

## Project files

    cr/
    ├── .vscode/
    │   ├── launch.json
    │   └── tasks.json
    └── outputs/
        ├── laundry_management.cpp
        ├── laundry_management_gui.cpp
        └── laundry_data.txt

The `outputs` folder may also contain compiled executables and other build files.

## Manual checks

You can check the main features by:

1. Adding a customer and confirming the program assigns an ID.
2. Trying to submit a customer or order with a required field empty.
3. Creating an order and checking the bill against `service rate × weight`.
4. Changing an order status and deleting an order.
5. Closing and reopening the program to confirm saved records load.

## Limitations

- This is a local, single-user program. It does not synchronize data between computers.
- Data is stored in a plain text file, not a database.
- The GUI requires Raylib to build and run.
- The console and GUI are separate programs.
