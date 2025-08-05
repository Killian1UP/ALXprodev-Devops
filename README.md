# Pokémon Bash Automation Project

This project contains a series of Bash scripts that interact with the [PokéAPI](https://pokeapi.co/), showcasing API consumption, text processing, error handling, and parallel execution in shell scripting.

## Tasks and Scripts

### 0. API Request Automation

**File:** `apiAutomation-0x00`  
**Objective:** Automate the process of making an API request to the PokéAPI and saving the result.

- Fetch data for **Pikachu**
- Save the response to `data.json`
- If the request fails, log the error to `errors.txt`

### 1. Extract Pokémon Data

**File:** `data_extraction_automation-0x01`  
**Objective:** Extract and format Pokémon data using `jq`, `awk`, and `sed`.

- Extract name, height, weight, and type from `data.json`
- Output: `Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.`

### 2. Batch Pokémon Data Retrieval

**File:** `batchProcessing-0x02`  
**Objective:** Fetch data for a batch of Pokémon and store each response in a separate file.

- Pokémon list: Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon
- Each Pokémon's data saved as `<name>.json`
- Delay added between requests to avoid rate limits

### 3. Summarize Pokémon Data

**File:** `summaryData-0x03`  
**Objective:** Generate a CSV summary and compute averages.

- Reads JSON files from Task 2
- Generates `pokemon_report.csv` with name, height (m), and weight (kg)
- Uses `awk` to calculate average height and weight
- Uses `sed` to clean up formatting

### 4. Error Handling and Retry Logic

**File:** `batchProcessing-0x02` (enhanced)  
**Objective:** Add retry mechanism to API fetch script.

- Retries failed requests up to 3 times
- Logs failed fetches in `errors.txt`
- Deletes any partially downloaded JSON files

### 5. Parallel Data Fetching

**File:** `batchProcessing-0x04`  
**Objective:** Fetch Pokémon data in parallel using background processes.

- Uses `&` to run fetches in parallel
- Tracks and waits for PIDs
- Demonstrates `kill` command for process management
- Logs failures and ensures script waits for all to finish

---

## How to Run

Ensure the following tools are installed on your system:

- `bash`
- `curl`
- `jq`
- `awk`
- `sed`

Then make the scripts executable and run them:

```bash
chmod +x script_name
./script_name
```

---

## License

This project is for learning purposes and interacts with the public [PokéAPI](https://pokeapi.co/). Be kind to their servers!
