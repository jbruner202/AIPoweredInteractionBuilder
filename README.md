# AI-Powered Interaction Builder

## Project Description
This project is an interactive web application that generates a customized greeting for the user based on their name and the current time of day. It demonstrates how to combine HTML, CSS, and JavaScript, specifically using an AI-generated JavaScript function and wiring it up with DOM Event Listeners.

## How to Run It
1. Download or clone this repository to your local machine.
2. Open the `index.html` file in any modern web browser (e.g., Chrome, Firefox, Safari).
3. Enter your name in the first input field.
4. Enter the time of day (e.g., morning, afternoon, evening) in the second input field.
5. Click the "Generate Greeting" button to see your custom greeting!

## JavaScript Logic & Test Cases
The JavaScript code successfully passes all edge cases due to how the function and event listener are structured:

### 1. The AI-Generated Function
```javascript
function generateCustomGreeting(name, time) {
    if (!time) {
        time = "day";
    }
    return `Good ${time}, ${name}! Welcome back to JavaScript class.`;
}
```
* **Handling Standard Inputs:** The function receives the `name` and `time` variables and injects them into a string using template literals (backticks). 
* **Handling Missing Data (Test Cases 3 & 5):** The statement `if (!time)` checks whether the time variable is empty, undefined, or null. If the user leaves the time input blank, it evaluates to `true` (because an empty string is "falsy" in JavaScript), and the code assigns `"day"` to the `time` variable. This ensures the output reads "Good day" instead of "Good undefined".
* **Handling Missing Name (Test Case 4):** Because there is no `if (!name)` fallback built into the prompt requirements, if a user leaves their name blank, it simply injects an empty string. This results in "Good afternoon, !". 

### 2. The Event Listener
```javascript
document.getElementById('greetBtn').addEventListener('click', function() {
    const userName = document.getElementById('userName').value;
    const timeOfDay = document.getElementById('timeOfDay').value;
    const greeting = generateCustomGreeting(userName, timeOfDay);
    document.getElementById('output').textContent = greeting;
});
```
* **Real-time Capture:** By using an Event Listener attached to the `click` event of the button, the variables `userName` and `timeOfDay` are captured at the exact moment the user clicks the button. This allows the inputs to be dynamic and accept infinite test case variations (like "Batman" and "midnight") without needing to hard-code them!

## AI Tools & Prompts Used
This project utilized an AI Coding Assistant to help generate the core logic for the greeting.

**Prompt Used:**
> Act as a JavaScript coding assistant. Write a single JavaScript function named "generateCustomGreeting". 
> It should accept two parameters: "name" and "time". 
> Inside the function, it should return a string that looks like this: 
> "Good [time], [name]! Welcome back to JavaScript class."
> Ensure the function handles missing data: if no time is provided, it should default to "day". 
> Return only the JavaScript function code, no markdown explanations.
