# Password-Checker

This repository contains a Python script that interacts with the "Have I Been Pwned" API to check if a password has been compromised in a data breach. The script hashes the password and queries the API to determine if it has been previously exposed in any known breaches.

## Script Overview

The `password_checker.py` script provides the following functionalities:

- **`request_api_data(query_char)`**: This function sends a GET request to the "Have I Been Pwned" API to retrieve hashes of leaked passwords based on the first five characters of the input hash.

- **`get_password_leaks_count(hashes, hash_to_check)`**: This function parses the response from the API to determine if the hashed password (after the first five characters) matches any known hashes. It returns the count of occurrences of that hash if found; otherwise, it returns 0.

- **`pwned_api_check(password)`**: This function takes a password as input, hashes it, and checks if it has been leaked using the "Have I Been Pwned" API.

- **`main(args)`**: The main function of the script, which takes a password as an argument, checks if it has been compromised, and prints a message indicating the result.

## How to Use

To use the password breach checker:

1. Clone this repository to your local machine.

2. Ensure you have Python installed (version 3.6 or higher).

3. Install the required dependencies by running:
pip install requests

4. Run the script by executing the following command:
python password_checker.py

5. Follow the prompts to input a password. Type "break" to exit the program.

## Example Usage

$ python password_checker.py

type "break" to exit

password: mypassword

mypassword was found 65510 times! You should consider changing your password.

password: break

## Note

This script does not send the actual password to the API; instead, it sends a hashed version of the password. This ensures that the password remains secure during the checking process.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
