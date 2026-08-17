# Compiled Walkthrough

### Tools Used

- `strings` - Used to extract readable strings from the binary.
- AttackBox terminal - Used to analyze the binary.

### Step-by-Step Methodology

- **Step 1** - Download the binary and run `strings` on it.
- **Step 2** - Notice the interesting strings:
  - `DoYouEven%sCTF`
  - `_init`
  - `__dso_handle`
  - `Correct!` / `Try again!`
- **Step 3** - Understand that the program uses `scanf` with the format `DoYouEven%sCTF`.
- **Step 4** - The middle part (`%s`) must be equal to `_init`.
- **Step 5** - The correct password is therefore: DoYouEven_init
