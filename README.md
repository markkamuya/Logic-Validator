# Logical Argument Validity Checker

This Python script evaluates the validity of logical arguments using truth tables. It dynamically generates truth values for premises and checks whether the argument, based on its premises, is valid or invalid. The application is designed to run via the terminal with no user interface.

## Core Logic

- **Variables**: The script uses a list of logical variables representing the premises and conclusion. These variables are dynamically handled to generate all possible combinations of truth values (using binary values).
  
- **Truth Table**: A Pandas DataFrame is created to represent the truth table for the premises and conclusion. The total number of rows is determined by the number of variables (`2^n`).

- **Premise Functions**: Each premise is defined by a logical function:
  - **Premise 1**:  S -> (C ^ T ^ A ^ O ^ L ^ H)
  - **Premise 2**:  C -> M
  - **Premise 3**:  S
  
- **Conclusion**: The conclusion is defined as M.

- **Validity Check**: The argument is considered valid if, for all rows where the premises are true, the conclusion is also true. The script checks all truth table combinations and outputs whether the argument is valid or invalid.

## Usage

1. **Input Variables**: The list `variables` defines the logical variables for the premises. By default, it includes 8 variables (S, C, M, T, A, L, O, H). This list can be customized to handle more or fewer premises.
   
2. **Run the Script**: Execute the script in the terminal by running:
   logic-validator.txt


3. **Output**: The script outputs the validity of the argument and prints the corresponding truth table.

### Example Output

```
The argument is VALID.

    S     C     M     T     A     L     O     H  premise1  premise2  premise3  conclusion
0   True  True  True  True  True  True  True  True    True     True     True       True
1   True  True  True  True  True  True  True  False   True     True     True       False
...
```

## Functions

- **conditional(antecedent, consequent)**: Implements the conditional (implication) logic: ~ P v Q.

- **premise1(S, C, T, A, O, L, H)**: Evaluates the first premise S -> (C ^ T ^ A ^ O ^ L ^ H).

- **premise2(C, M)**: Evaluates the second premise C -> M.

- **premise3(S)**: Evaluates the third premise S.

- **conclusion(M)**: Evaluates the conclusion M.

- **Validity Check**: Loops through the truth table and flags the argument as invalid if any row shows all premises true while the conclusion is false.

## Dependencies

- **pandas**: Required for managing and displaying the truth table as a DataFrame.

## Terminal Execution

This script is intended to be run in a terminal or command-line environment. Ensure you have Python 3.x and `pandas` installed to execute the script.

```bash
pip install pandas

This version provides a very technical and terminal-specific description of your logic checker, focusing on the core details of the algorithm and its operations without a UI.
