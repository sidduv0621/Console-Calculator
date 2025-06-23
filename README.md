# Console-Calculator
Main loop: The while (cals) loop displays a menu and processes choices, repeating until “Exit” is chosen.

Separation of concerns: Arithmetic is done in individual methods (add, subtract, …). User I/O and control flow remain in main and performOperation.

Input validation:

readDouble ensures numeric input, reprompting on invalid values.

Division checks for zero to prevent exceptions.

Formatted output: The result is shown with four decimal places.

