java c
EEME31000
Formal report: Embedded Computing Systems: (Deadline: Thursday, 21 November 2024 13:00) 
Please note that all examples and laboratory exercises conducted during the laboratory sessions are formative and not assessed.The primary objective of this coursework is to develop a comprehensive understanding of embedded systems,  particularly  in  the  areas   of  real-time  DSP  processing,  FIR  filtering,   inter-processor communication, and peripheral control. The seven tasks covered in this coursework span a variety of embedded computing techniques, from microcontroller programming to real-time signal processing and data transfer using DMA. The following report outlines the approach taken to complete each task, the challenges encountered, and the solutions implemented.You are required to perform. the following seven tasks to meet the assessment requirements of the unit. The maximum  marks possible for this coursework  is  100.  Some of the answers should  be included in the report (Task 6).
Task 1: Implement a printf (total 10 marks) 
Write a C program that performs the following tasks (provide the whole project):
1.   Multiply two 16-bit signed integers and print the result as a 64-bit integer. 2 marks 
2.   Multiply two 16-bit unsigned integers and print the result as a 64-bit unsigned integer. 2 
marks 
3.   Multiply two 32-bit floating-point numbers and print the result. 6 marks Make sure to display the results on the CCS console. Take into consideration that printf() in Code   Composer Studio might not handle floating-point numbers properly, so provide a method to ensure the floating-point result is displayed correctly as shownFigure 1. 

Figure 1 Console output example.
Task 2. FIR implementation (non-real-time) (15 marks) Project name: FIR_Timer_NR 
In this coursework, you are tasked with analysing and completing the provided FIR filter implementation. The code contains the setup for generating an input signal, applying a FIR filter, and handling CPU timers on the TMS320F28379D microcontroller.
Your primary task is to complete the FIR filter function to process an input signal and produce the filtered output. Below are the detailed steps and points to guide you:
Objective: 
Implement a digital FIR filter using floating-point precision to process a generated input signal (a combination of sine waves). Your task is to analyse the given code and complete the filter1() 
function. The expected output should resemble Figure 3 (mentioned in the instructions), showing both the input signal and the filtered output.
Steps: 
1. Code Analysis:
•     Carefully read through the code provided.
•     Understand the purpose of the FIR filter in the context of signal processing.
•     Familiarise yourself with the variables and buffers used in the code, especially the
FIR coefficients (firCoeffs[]) and the circular buffer (filtbuff1[]).
2. Timer ISR (Interrupt Service Routine):
o  The cpuTimer0ISR() function is invoked periodically based on the timer configuration.
o  In each ISR call, the next sample of the input signal is processed using the filter1()
function.
o  Analyse how the input signal (signal[]) is passed to the filter1() function for filtering,
and how the result is stored in buffer1[].
3. Signal Generation:
•   The function generateSignal() generates a signal consisting of two sin代 写EEME31000 Formal report: Embedded Computing SystemsR
代做程序编程语言e waves with frequencies 1000 Hz and 2000 Hz.
•   The signal is sampledata rate of 44 kHz and stored in the signal[] buffer.
4. Filter Implementation:
•   The FIR filter function filter1() takes an input sample and applies the filter using the coefficients defined in firCoeffs[].
•   You need to implement the logic to perform. the convolution of the input signal with the filter coefficients.
•   The filter is designed as a low-pass filter, but you can tweak the coefficients if needed.
5. Output:
•   Ensure the filtered output is stored correctly in buffer1[] and matches the expected output.
•  Pay attention to indexing when accessing the filtbuff1[] circular buffer and ensure it's updated correctly after each new sample is processed.
6. Debugging:
•   Use the CCS console to check intermediate results and verify if the FIR filter is working as expected.
•  You can print variables, such as Input_Data and Output_Data1, to help in debugging.
7. Results:
•  The filtered signal should have certain frequencies removed based on the FIR filter design.
•  Compare the generated and filtered signals to ensure the filter is functioning properly.
Deliverables: 
1. Completed FIR filter function: Implement the filter1() function to apply the FIR filter to the
input signal. 10 marks. 
2. Analysis: Write a brief explanation of how the FIR filter works and why the filtering is done in
the filter1() function. (report: 3 marks) 
3. Testing: Ensure that the program runs correctly and that the filtered signal matches the expected result as shown inFigure 2, plot your results. (report 2 marks). 

Figure 2 CCS output for comparison.
Task 3 Goertzel algorithm Implementation: (15 marks) 
File name: GTZ.docx 
The main function in the C code provided serves as the core loop for generating and processing
DTMF (Dual-Tone Multi-Frequency) signals, which are used in telephone systems to represent key presses. The function continuously prompts the user to input a key (such as '0'-'9', 'A'-'D', '*', or '#'). Once a key is pressed, it generates the corresponding DTMF tones (two frequencies combined) for that key using the Generate_tones function.
After generating the tones, it processes the generated signal using the goertzel_multi function, which applies the Goertzel algorithm to detect the presence of specific frequencies in the signal. This allows  the system to identify the DTMF tones generated and then determine which key was pressed. The
Frequency_detection function analyses the results of the Goertzel algorithm and prints out the


detected key, completing the input-processing cycle. The process repeats, allowing continuous detection of keypresses.
Analyse the C code provided code that implements the Goertzel algorithm, which is used to detect the strength or magnitude of specific target frequencies within a signal. For each target frequency, the
algorithm iterates through the input signal samples and calculates filter values (q0, q1, and q2) to
extract the frequency component of interest. After processing all samples for each frequency, the
magnitude is calculated based on the final filter values and stored in an array, representing the energy at each target frequency. This technique is often used in tone detection and frequency analysis tasks.





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
