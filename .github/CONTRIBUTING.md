# Contributing to Jobsort

## Adding New Companies

Thank you for considering adding a new company to the list of companies that Jobsort indexes.
This is done in the `companies.csv` file.

The format of the file is as follows, `url,name,hq,size,stage,funding`:

*   `url`: This is the homepage of ther startup without the `www.` prefix.
*   `name`: Prefer the official name of the company in its correct casing.
*   `hq` represents headquarters: Prefer city, county/state, country but without the continent. For example: San Francisco, California, United States.
*   `size`: One value from `sizes.txt`.
*   `stage`: One value from `stages.txt`.
*   `funding`: The value and its currency without spaces. For example: 1000000USD.

If it's unclear what size or stage a company is in, please look up the company on [Crunchbase](https://www.crunchbase.com).

And also, please make sure there are no spaces around commas.
