# todoti
### short and sweet
This is a small program in python with simple GUI using Python's built-in tkinter module. 
It displays a To-Do List where the user can make a planning for general tasks. 
Click on Start for a task to start a stopwatch timer for the task and add Job and Client. At the end an output excel worksheet is created for the work day.
### For extra details
Todoti is initially made in Python 3.10 (64-bit).
We use the time module to calculate the elapsed time for each task using a while loop.
We initialize the start_time variable with the current time using the time.time() function, and then we use a while loop to keep looping until the duration of the task is reached.

Inside the while loop, we calculate the elapsed time by subtracting the start_time from the current time using the time.time() function. 
We wait for 1 second using the time.sleep(1) function before starting the next iteration of the loop.
We also format the elapsed time as hours, minutes and seconds using the int() function and the modulo operator %. 
We print the elapsed time, user input for Client and Job.

Once the user interrupts the stopwatch with the <Return> key, we print a message indicating that the task is complete. 
The task data, such as task, name, duration, Client and Job input are saved or appended in an output file per day.
When todoti is run multiple times a day, the same output file for the day keeps being appended with the new data.

This code creates a GUI with tkinter. The Toplevel class is used to create a new window for each task. 
  Note that you do not need to install any additional libraries to run this code, as tkinter is included with Python by default.

  
To export the print output to an Excel sheet, we use the openpyxl library. You can install it via pip using the command pip install openpyxl.
Then you can create a new Excel workbook, create a worksheet for the task output data, and write the data to the worksheet every time the stopwatch is stopped.
Todoti will create an Excel file named task_output_DDMMMYYYY.xlsx (if it doesn't exist) and append a new row to the worksheet for each stopped stopwatch, including the task name, duration, and the data entered by the user.
  The output file name includes the current date in the format DDMMMYYYY (e.g., task_output_16May2023.xlsx).
  The code checks if a file with that name exists in the current directory for the current date. If it exists, the existing workbook is loaded. Otherwise, a new workbook is created. 
  The data will be appended to the existing worksheet within the workbook, preserving the data from previous runs in the same day.

  A dictionary task_inputs holds the StringVar variables for each task's name input field. 
  Inside the loop, a frame is created to hold the task label, task name field, and start button. The task label and input field are packed side by side within the frame.
