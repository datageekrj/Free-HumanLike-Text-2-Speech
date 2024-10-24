# Text-to-Speech Automation Script

This repository contains a Jupyter Notebook that generates a shell script to process a text file using a Text-to-Speech (TTS) model. The script allows you to convert text into speech using customizable parameters, such as speaker ID and chunk size, and then combines the generated audio files into one consolidated output file.

## Table of Contents
1. [Installation](#installation)
2. [Usage](#usage)
3. [Arguments](#arguments)
4. [Available Speakers](#available-speakers)
5. [Output](#output)
6. [License](#license)

---

## Installation

Before running the notebook, you need to install the required dependencies.

1. Install the `TTS` package:

    ```bash
    !pip install TTS
    ```

2. Install the `sox` utility to concatenate the generated audio files:

    ```bash
    !sudo apt-get install sox libsox-fmt-all
    ```

3. Ensure that you have a text file (`.txt`) with the content you want to convert into speech. Update the `txt_file` variable in the notebook to point to the correct file.

---

## Usage

1. Clone the repository and open the notebook in a Jupyter environment.

2. Modify the following parameters inside the notebook:
   - `txt_file`: The name of your text file.
   - `speaker_id`: The ID of the speaker's voice to be used.
   - `words_to_process_once`: The number of words to process at a time (default is 10).

3. After updating the parameters, run the notebook cells to:
   - Generate a shell script named `run_tts.sh`.
   - Convert text chunks into speech files using the selected TTS model.
   - Concatenate the generated audio files into one final output file.

4. Once the script is generated, it can be run with:

    ```bash
    !chmod +x run_tts.sh
    !./run_tts.sh
    ```

This will produce a series of `.wav` files for each chunk of text and concatenate them into a single file called `consolidated_output.wav`.

---

## Arguments

The notebook generates a shell script that accepts the following arguments:

1. `txt_file_name` (str):  
   **Description**: Name of the text file containing the input text to be converted into speech.  
   **Example**: `sample1.txt`.

2. `speaker_id` (str, optional):  
   **Description**: The speaker ID to be used for voice generation. A list of available speakers is provided in the next section.  
   **Default**: `"Viktor Eka"`.

3. `words_to_process_once` (int, optional):  
   **Description**: Number of words to process at a time for each audio chunk.  
   **Default**: `10`.  
   **Example**: `60` to process 60 words at a time.

---

## Available Speakers

The following speakers are available for use with the TTS model. You can specify the speaker ID in the `speaker_id` argument when generating the shell script:

```
['Claribel Dervla', 'Daisy Studious', 'Gracie Wise', 'Tammie Ema', 'Alison Dietlinde',
 'Ana Florence', 'Annmarie Nele', 'Asya Anara', 'Brenda Stern', 'Gitta Nikolina', 
 'Henriette Usha', 'Sofia Hellen', 'Tammy Grit', 'Tanja Adelina', 'Vjollca Johnnie', 
 'Andrew Chipper', 'Badr Odhiambo', 'Dionisio Schuyler', 'Royston Min', 'Viktor Eka', 
 'Abrahan Mack', 'Adde Michal', 'Baldur Sanjin', 'Craig Gutsy', 'Damien Black', 
 'Gilberto Mathias', 'Ilkin Urbano', 'Kazuhiko Atallah', 'Ludvig Milivoj', 'Suad Qasim',
 'Torcull Diarmuid', 'Viktor Menelaos', 'Zacharie Aimilios', 'Nova Hogarth', 'Maja Ruoho',
 'Uta Obando', 'Lidiya Szekeres', 'Chandra MacFarland', 'Szofi Granger', 'Camilla Holmström',
 'Lilya Stainthorpe', 'Zofija Kendrick', 'Narelle Moon', 'Barbora MacLean', 'Alexandra Hisakawa',
 'Alma María', 'Rosemary Okafor', 'Ige Behringer', 'Filip Traverse', 'Damjan Chapman', 
 'Wulf Carlevaro', 'Aaron Dreschner', 'Kumar Dahl', 'Eugenio Mataracı', 'Ferran Simen', 
 'Xavier Hayasaka', 'Luis Moray', 'Marcos Rudaski']
```

---

## Output

- For each chunk of text, an individual `.wav` file is generated, such as `out_chunk_0.wav`, `out_chunk_1.wav`, and so on.
- After processing all text chunks, the script uses `sox` to concatenate all generated `.wav` files into a single output file named `consolidated_output.wav`.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
