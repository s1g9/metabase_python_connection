

# Metabase API Data Extraction Script

This script retrieves data from Metabase API as a CSV and converts it into a pandas DataFrame.

## Requirements

- Python 3.x
- Libraries: `requests`, `pandas`, `io`

Install dependencies:
```bash
pip install requests pandas
```

## Setup

1. Update the `username` and `password` in the script with your Metabase credentials.
2. Use the `request_data` function with the card ID to fetch data.

## Usage

### Authentication
The script authenticates using:
```http
POST http://metabase.breathewellbeing.in:3000/api/session
```

### Fetch Data
Retrieve data with:
```http
POST http://metabase.breathewellbeing.in:3000/api/card/<question_id>/query/csv
```

Example:
```python
leads_data = request_data('797')  # Fetch data for card 797
```

## Output
Data is returned as a pandas DataFrame for analysis.

## Error Handling
- Script raises an `AssertionError` if API requests fail.

## Notes
- Ensure the Metabase server URL is correct.
- Keep credentials secure.
- Test API endpoints before use.

