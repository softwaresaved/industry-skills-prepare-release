## Description

This Python tool contains a small analysis pipeline for a [NASA dataset on Extravehicular Activity (EVA)](https://data.nasa.gov/Raw-Data/Extra-vehicular-Activity-EVA-US-and-Russia/9kcy-zwvn/data_preview).

The core script `eva_data_analysis.py` reads the JSON dataset, cleans it,
computes `duration_hours` and `crew_size`, exports a CSV,
and renders a cumulative EVA-time plot to `results/`.

## Pre-requisites

- Python 3.8+ (virtual environment recommended)
- Pandas 2.3
- Matplotlib 3.10
- Pytest 9 and Pytest-cov 7 (to run unit tests)

Install project dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

## Usage

Run the analysis with defaults (uses `data/eva-data.json` and writes to `results/`):

```bash
python eva_data_analysis.py
```

Or supply input and output paths:

```bash
python eva_data_analysis.py data/eva-data.json results/eva-data.csv
```

Generated files include `results/eva-data.csv` and `results/cumulative_eva_graph.png`.

## Running Tests

Unit tests are provided in the `tests/` folder and cover basic helpers such as `text_to_duration` and `calculate_crew_size`.

Run tests with:

```bash
pytest tests/
```

Run tests with coverage (requires `pytest-cov`):

```bash
pytest --cov=eva_data_analysis tests/
```

## Maintainers

S.Omebody <s.omebody@someemailaddress.com>

## Licence

This code is licensed under the MIT licence, which can be found in the [LICENSE](LICENSE) file.

## Authors

The original authors of this fabricated example software project are:

- [Sarah Jaffa](https://github.com/SJaffa)
- [Kamilla Kopec-Harding](https://github.com/kkh451)
- [Aleks Nenadic](https://github.com/anenadic/)
- [Colin Sauze](https://github.com/colinsauze)

## Acknowledgements

### Original Source Code

The original repository that this is based on can be found at https://github.com/carpentries-incubator/bbrs-software-project.

### Data

The data used on in this project is open data provided by NASA and obtained as follows.

Data source: https://data.nasa.gov/Raw-Data/Extra-vehicular-Activity-EVA-US-and-Russia/9kcy-zwvn/about_data.

Either export data from the above page using the `Export` button or download in JSON format from command line as: 

`curl https://data.nasa.gov/resource/eva.json --output eva-data.json`

**Note: the original data has been modified for the purposes of this tutorial by inserting a semicolon separator after each name in the `crew` field.**
