# Rivers

Rivers is one of the domains, which is a part of the IndicWiki Project.

## Description

The aim of this domain is to create a large number of articles (about 27000) about Rivers. Hence, we are generating these data-rich articles in telugu for about 27000 Rivers, and uploading them to wikipedia, so that people who can read only in their native language (here, telugu) can benefit from this information.

## Installation and setup

Create virtual environment in the project folder using the following commands.

pip install virtualenv
pip install python3.9 
virtualenv -p python3.9 riverEnv

After the successful creation of virtual environment (venv), clone the repository or download the zip folder of the project and extract it. Run the following commands from the Rivers_wiki (root) directory to activate the virtual environment and install all necessary dependencies.

source riverEnv/bin/activate
pip install -r requirements.txt

requirements.txt comes along with the Project Directory.

## Guide to generate XML dump, articles for different Rivers

    Clone the repository into the local system.
    Enter the 'curDir' folder inside the cloned repo.
    Open the notebook file genXML.ipynb, Configure From_n and To_n variables then Execute the notebook by clicking on "Run all", where From_n and To_n correspond to the row numbers of the first and last desired articles (only serial order is possible). For example From_n = 30 and To_n = 50 would generate xml dump for Rivers in rows 30-50 (inclusive). By default, dump is generated for all Rivers (case where no mdifications are done).
    On executing the above Notebook xml dump is obtained in rivers.xml. If From_n and To_n were modified then the file name would be rivers_{From_n}-{To_n}.xml, names of these files would have the range passed in their filenames (such as rivers_30-50.xml etc).

## Github Structure

    The Rivers_wiki (root) folder contains files as
        requirements.txt → python requirements file
        rivers xml.xml → the xml dump for all rivers
        RiversReport.html → sweetviz report of the final dataset of rivers

The folder curDir contains the entire implementation corresponding to article generation. This directory contains the codebase for the new model, converting knowledge base to intermediate structured article (dataframe of labeled article sentences) which can be modified and updated by users and then converting this data to XML page which can be imported in mediawiki.

It can be found here. All the below explained files and folders are inside this directory.

### data

    Github folder Link: https://github.com/Indicwiki-Rivers/Rivers_wiki/tree/main/curDir/data

    This folder contains various datasets (final and intermediate), and the implementations as to how they were obtained. Different formats of the dataset are present as follows (like csv, excel etc):
        rivers success_csv.csv → This is a csv file containing all the data related to rivers.
        RiversReport.html → HTML sweetviz report of the River dataset.
        Rivers english raw.xlsx → Excel file containing raw data of all the 27000+ rivers including all their attributes values.
        Rivers english cleaned.xlsx → Excel file containing data of all the rivers only in english
        rivers mergedata final.xlsx → Final Dataset of all the rivers including both english and telugu translated values of attributes.
        WIKIriverlinks.xlsx → Excel file that contains all wikiedia links of every river

### code

    Github folder Link: https://github.com/Indicwiki-Rivers/Rivers_wiki/tree/main/curDir/code

    This folder contains code used to scrape the data and clean them. 
    The files in this folder are:
        Data Scraping.ipynb → This file contains code used to scrape the data from DBPedia.
        WikiInfobox.ipynb → This file contains code used to scrape infobox data from wikipedia.
        cleaning.ipynb → This file contains code to clean river name attribute values in the data.
        transliteration.ipynb → This file contains anuvaad code to transliterate river name attribute values.
        wikiinfoboximages.ipynb → This file contains code to extract infobox images from wikipedia.
        wikiinfoboxmap.ipynb → This file contains code to extract infobox maps from wikipedia.


        All the intermediate files are saved in 2 types i.e
            •	CSV
            •	EXCEL	


## Template

    Github folder Link: https://github.com/Indicwiki-Rivers/Rivers_wiki/tree/main/curDir/Template

    This folder .
        rivers.j2 → This file consists of the improved template to generate wikitext provided a river's data, corresponding to latest dataset

### Contributors

    Students : Aravinda Aparna, Yadavalli Varshitha, Annareddy Divya, Sreeshanth Ganduri
    Student Mentors : Jayaprakash Aluri, Bala Bhavana K
