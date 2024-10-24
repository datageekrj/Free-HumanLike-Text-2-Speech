
# 🗣️ Text-to-Speech Automation Script

This repository contains a Jupyter Notebook that generates a shell script to automate text processing using a Text-to-Speech (TTS) model. The script allows you to convert text into speech with customizable parameters, such as speaker ID and chunk size, then consolidates the generated audio files into a single output.

🎥 **Demo:** [Watch here](https://youtu.be/pEgqffQKGUI)

## 📑 Table of Contents
1. [💻 Installation](#installation)
2. [📖 Usage](#usage)
3. [⚙️ Arguments](#arguments)
4. [🔊 Available Speakers](#available-speakers)
5. [📂 Output](#output)
6. [📜 License](#license)

---

## 💻 Installation

Before running the notebook, ensure the required dependencies are installed.

1. Install the `TTS` package:

    ```bash
    !pip install TTS
    ```

2. Install the `sox` utility to concatenate the generated audio files:

    ```bash
    !sudo apt-get install sox libsox-fmt-all
    ```

3. Ensure you have a text file (`.txt`) containing the content to be converted into speech. Update the `txt_file` variable in the notebook to point to the correct file.

---

## 📖 Usage

1. Clone the repository and open the notebook in a Jupyter environment.

2. Modify the following parameters inside the notebook:
   - `txt_file`: The name of your text file.
   - `speaker_id`: The ID of the speaker's voice.
   - `words_to_process_once`: Number of words to process at a time (default is 10).

3. Run the notebook to:
   - Generate a shell script (`run_tts.sh`).
   - Convert text chunks into speech using the chosen TTS model.
   - Concatenate the generated audio files into a single output file.

4. Run the generated script with:

    ```bash
    !chmod +x run_tts.sh
    !./run_tts.sh
    ```

This produces a series of `.wav` files for each text chunk, which are then concatenated into a single file named `consolidated_output.wav`.

---

## ⚙️ Arguments

The shell script accepts the following arguments:

1. `txt_file_name` (str):  
   **Description**: Name of the text file containing the input text.  
   **Example**: `sample1.txt`.

2. `speaker_id` (str, optional):  
   **Description**: The speaker ID for voice generation.  
   **Default**: `"Viktor Eka"`.

3. `words_to_process_once` (int, optional):  
   **Description**: Number of words to process per audio chunk.  
   **Default**: `10`.  
   **Example**: `60` to process 60 words at a time.

---

## 🔊 Available Speakers

Below is a list of available speakers for the TTS model. Specify the `speaker_id` when generating the shell script:

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

## 📂 Output

- Each chunk of text generates an individual `.wav` file (e.g., `out_chunk_0.wav`, `out_chunk_1.wav`, etc.).
- After processing all text chunks, the script uses `sox` to combine the `.wav` files into a single output file named `consolidated_output.wav`.

---

## 📜 License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
