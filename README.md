# WikipediaTopicScraper
This project is a Python script designed to automate the process of searching for information related to a specific theme on Wikipedia. The script does this by leveraging the Wikipedia API to search for relevant pages, fetches the content of these pages, and then stores the content in a text file. The user can then analyse or utilise this information as required.

## Installation

Before running the script, you need to have Python installed on your machine. If you don't have it installed, you can download it from [here](https://www.python.org/downloads/).

You may also want to create a virtual environment to run this in, which can be done by running the following commands in a terminal:

```bash
cd into-your-directory
python3 -m venv venv # create the virtual environment
source venv/bin/activate # init venv
```

To run the script, you also need to install the packages in ```requirements.txt```. You can do so by running the following commands in your terminal:

```bash
pip install -r requirements.txt
```

## Running the script
The script is an .ipynb file, and is composed of two main steps:

### Searching Wikipedia for relevant page URLs
The script uses a list of search terms related to a theme. It then makes a request to the Wikipedia API for each search term and retrieves a list of relevant page URLs. Each URL is confirmed by the user to be useful before it is added to the final list of URLs.


### Fetching the page content
For each confirmed URL, the script sends a GET request to fetch the page's HTML content. It then uses BeautifulSoup to parse the HTML and extract the title and main body text. The text is cleaned to remove any tags or empty sections and then saved in a markdown file.

### To execute the script:

```bash
python get_wikipedia_pages.ipynb
```

## Configuration

You can customize the script by modifying the terms specified in ```search_terms``` to contain the terms you are interested in.

You will need to provide the directory path where the output files will be stored. This can be done by setting the ```OUTPUT_FILE_DIR``` environment variable in a ```.env``` file. Create a ```.env``` file in the same directory as the script and set the ```OUTPUT_FILE_DIR``` variable

## Troubleshooting

If you get the message <b>Something has gone wrong</b>, this likely means that an error occurred while attempting to parse a page's HTML content or write the output file. Check your ```OUTPUT_FILE_DIR``` variable to ensure that the path is correct and that you have write permissions to that directory.

## Limitations

This script is dependent on the structure of the Wikipedia pages. If Wikipedia changes the way they structure their pages, the script may fail to correctly parse the HTML content.

The script is designed to find information related to a specific theme on English Wikipedia pages. It does not currently support other languages.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License.

## Disclaimer
The author of this script is not responsible for the use of the script beyond its intended purpose. The user is expected to use the script responsibly and ethically, respecting Wikipedia's Terms of Use.

## Support
If you encounter any issues or have any questions about this script, feel free to open an issue on the project's GitHub page.

# Acknowledgments
The author would like to acknowledge the following:

- Wikipedia for their open API that makes this script possible.
- The Python community for the open-source libraries utilized in this script.