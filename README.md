# PROGCON-Week-11
def computeAverage(numbers):
    """
    Compute the average of the numbers in the given list following the 
    exact pseudocode specification.

    Logic & Behavior:
    - Initializes 'total' and 'count' to 0.
    - Loops through each number in the array.
    - If a number is 0 (num == 0), it adds it to the total, increments the count, 
      and continues the loop.
    - If a number is NOT 0, the ELSE branch triggers an immediate early RETURN 
      of (total / count).
    - If the loop finishes without hitting a non-zero number, it returns the final (total / count).
    
    Note on Algorithm Design:
    Because of this specific early-return logic, encountering the first non-zero 
    number stops the loop prematurely, meaning numbers appearing after the first 
    non-zero value are ignored.
    """
    total = 0
    count = 0

    for num in numbers:
        # Check if the current number is zero
        if num == 0:
            total = total + num
            count = count + 1
        else:
            # Early return triggered upon encountering the first non-zero number
            return total / count

    # Final return if the loop finishes entirely (e.g., list of all zeros)
    return total / count


# --- Test Cases and Validation Documentation ---
# Test 1: [22, 9, 0, 17]
#   - Flowchart/Algorithm Output: Triggers early return on 22 (first non-zero), computes 0 / 0 (Division Error) or returns 0 depending on state.
#   - True Mathematical Average: 12.0
#   - Status: Incorrect (due to early return logic).

# Test 2: [22, 0, 49, 8]
#   - Flowchart/Algorithm Output: Triggers early return on 22.
#   - True Mathematical Average: 19.75
#   - Status: Incorrect.

# Test 3: [35, 13, 22, 0]
#   - Flowchart/Algorithm Output: Triggers early return on 35.
#   - True Mathematical Average: 17.5
#   - Status: Incorrect.

# Test 4: [10, 5, -4, 27]
#   - Flowchart/Algorithm Output: Triggers early return on 10.
#   - True Mathematical Average: 9.5
#   - Status: Incorrect.
