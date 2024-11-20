Metabase API Data Extraction Script
This script connects to the Metabase API to retrieve data in CSV format for a specific card (question) and process it into a pandas DataFrame for further analysis.

Requirements
Python 3.x
Libraries:
requests
pandas
io
You can install the required libraries using pip:

bash
Copy code
pip install requests pandas
Purpose
The script is designed to:

Authenticate with the Metabase API.
Request data for a specific question/card in CSV format.
Load the data into a pandas DataFrame for analysis.
Usage
Update the script with your Metabase credentials:

Replace the username and password in the res = requests.post() call with valid credentials.
Call the request_data function with the desired question/card number to fetch data.

Example
python
Copy code
# Fetch data for card number 797
leads_data = request_data('797')
Output
The request_data function returns the requested data as a pandas DataFrame. For example, if questionnumber is '797', the output will be stored in leads_data.

Key Functions
Authentication
The script authenticates with the Metabase server using the following endpoint:

python
Copy code
POST http://metabase.breathewellbeing.in:3000/api/session
Upon successful authentication, a session token is obtained, which is used for subsequent requests.

Data Request
The request_data function queries a specific card/question by ID and retrieves the data in CSV format:

python
Copy code
POST http://metabase.breathewellbeing.in:3000/api/card/<questionnumber>/query/csv
The data is decoded and loaded into a pandas DataFrame for ease of manipulation.

Error Handling
The script includes basic error handling:

If authentication or data retrieval fails, an AssertionError will be raised.
Example Run
bash
Copy code
$ python script.py
{'id': 'your-session-id'}
# The data for the specified card is now stored in the pandas DataFrame.
Notes
Ensure that the Metabase server URL is correct.
Keep your credentials secure and avoid hardcoding sensitive information in the script.
Test API endpoints to confirm their availability.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Let me know if you'd like additional customization or explanations!
