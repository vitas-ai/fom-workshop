# fom-workshop
![vitas-logo](logo.png)
VITAS repo for the workshop with fom students, 29.11.2021

**Contact**: [VITAS.ai](www.vitas.ai)

**Christine Neusinger** [cn@vitas.ai](mailto:cn@vitas.ai)

**Alex Gaus** [ag@vitas.ai](mailto:ag@vitas.ai)

## dDta
The information about VITAS-Calls is available in 3 formats:
* **json** (`data/json`) can be opened in Jupyter Notebooks, more information below
* **csv** (`data/csv`) comma seperated values can be viewed with programs such as MS Excel or web applications such as Google Spreadsheet 
* **sqlite-db** (`data/db`)
sqlite files can be opened with online tools such as [sqliteonline](https://sqliteonline.com/) or with programs such as [sqlitebrowser](https://sqliteonline.com/)

## data tables
There are 2 tables:
### calls
Entry for every call:
* **sender_id**: UID for every call
* **timestamp**: datetime for the beginning of the call
* **duration**: in seconds
* **call_steps**: one step = one utterance per user
* **call_type**: what type of call was it (possible options: CALL, DIRECT_ORDER, DTMF_ORDER, EARLY_ABORT, FORWARD)
* **reason**: reason why the call was forwarded (possible options: BLOCKED, FALLBACK, NO_NUMBER, NUMBER_CHANGE, USER)
* **user**: is this user/caller known? (True/False)
* **existing_order**: is ther an existing order for this user in the system (True, False)
* **order**: was an order placed (True/False)
* **repeat_location**: did the user have to repeat the location (True, False)
* **cancel**: did the user ask to cancel his/her order (True, False)
* **name**: did the user give her/his name (True, False)
* **poi**: did the user give point of interest (True, False)
* **street**: did the user give a street (True, False)
* **city**: did the user give city (True, False)
* **name**: did the user give her/his name (True, False)
* **datetime**: for what time did the user order the taxi (can be empty, '*sofort*', or datetime)

### utterances
Found intents for every utterence in a call,
1 to n relationship, one call can have 0, 1 or n utterances
* **sender_id** matches sender_id from calls
* **utterance_id** UID for every utterance
* **timestamp** dateime of the utterance
* **intent** which intent was detected in this utterance?
* **confidence** confidence value, between 0-1

## Jupyter Notebook
There is already one Jupyter notebook example file [data.ipynb].
### Installing requirements
```zsh
pip install -r requirements.txt
```
### Starting Jupyter Notebook
```zsh
jupyter notebook
```
jupyter notbook will open in browser window, please select file data.ipynb

