# GUI Setup Instructions

⚠️ **Important:**  
Follow these steps **after cloning THIS repository** into CLion.  
Do **NOT** clone `glfw` first.  
Do **NOT** use an external terminal — always use the **CLion built-in terminal**.

---

## Windows Setup

1. Open **CLion’s built-in terminal** (not PowerShell outside of CLion).  
   Run the following command **inside the root folder of this project**:

   ```powershell
   git clone https://github.com/glfw/glfw extern/glfw

This will create the folder: extern/glfw
	2.	In your CMakeLists.txt, replace this line:

set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
add_subdirectory(extern/glfw)

3.	Re-build the project:
	•	Go to menu → Build → Build Project

Mac Setup

Make sure Homebrew is installed.
	1.	Open CLion’s built-in terminal and run:

 brew install glfw

 This step should suffice. If this does not fix the errors, do the following inside the clion terminal :

 2.	Depending on your Mac’s processor:
	•	Apple Silicon (M1/M2/M3):

cmake -S . -B build -DCMAKE_PREFIX_PATH=/opt/homebrew
cmake --build build

•	Intel Mac:
cmake -S . -B build -DCMAKE_PREFIX_PATH=/usr/local
cmake --build build

3.	In your CMakeLists.txt, make sure you have:
find_package(glfw3 3.3 REQUIRED)
target_link_libraries(app PRIVATE glfw)
