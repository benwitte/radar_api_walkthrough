# Radar Geocoding API Guide for the Perplexed


### A gentle guide to using Radar's API for those unfamiliar with python


## What is Radar?

[Radar](https://radar.io/documentation/overview) is "location data infrastructure." In other words, it's a location data tool with multiple features, including geocoding. It can be used similarly to Google's geocoding API.

## Why use Radar over Google?

So if it's similar to Google's API, why use it? Well, it has a much larger free usage limit! With Radar, **we can make up to 100,000 API calls per month, for free.** More info [here](https://radar.io/pricing).

## Why use Radar over NYC Developer Portal's Geoclient API?

[Geoclient API](https://developer.cityofnewyork.us/api/geoclient-api) is a fantastic tool, and unlike Radar is completely free. However, it's a little more difficult to use, and can't easily return information if you have a place name rather than an address. For example, the [Hart Island Burial Records dataset](https://data.cityofnewyork.us/City-Government/DOC-Hart-Island-Burial-Records/c39u-es35) often lists place of death as a specific hospital, rather than an address. This can be an issue for Geoclient API, but it isn't an issue for Radar.

## Radar Setup

1. Go to [Radar's website](https://radar.io/) and click **sign up** in the upper right corner.

2. Sign up however you'd like!

3. **You're literally done.** You should see a live and test secret server. Keep that tab open.


## Python Setup

### I'm such a Python expert that I'm a literal snake charmer. Just link me the docs and leave me alone.

[Here you go.](https://radar-python.readthedocs.io/en/latest/index.html)

### I'm more comfortable around actual pythons than I am using Python. Help??

No problem. Let's break it down into easy steps.


### Anaconda Setup



1. If you don't have Anaconda, [download Anaconda](https://www.python.org/downloads/). This should download Python as well.

2. Create a new environment! [Follow the steps here]() to do this.

3. Install **pandas, numpy, janitor and radar-python**. Pandas and numpy have conda versions, while janitor and radar don't. So you'll need to run `conda install pandas` for pandas but `pip install radar-python` for radar-python.

4. Once this is done, go back to Anaconda Navigator, and **Launch JupyterLab**

5. On your screen, you should see a tab called **Launcher.** In Launcher, you should see the option to **Open a Python 3 Notebook.** Do it! You should now be looking at a blank Notebook.

5. In this repo, open the file called **radar_test.ipynb** and copy all of the code into your Notebook.


### The Actual Coding

If you're really, really, really new to Python, this is where it might take a little bit longer, but won't necessarily be that bad. As you can see, a test file has already been added, and my code comments should make pretty clear what each step is doing. **If you're unfamiliar with Python, I recommend doing all of the cleaning in R and then importing the data.**

Chances are, if your data is clean, you can ignore the code section with comment that says: `# add new york on the end, if it's not there already - this may be uneccessary for your code
`

The only things you need to change are marked in the document, but I'll highlight them here:

`#add data, clean nanmes
data = (
    pd.read_csv("hi_burial_sample.csv") #replace with your document and path!
    .clean_names()
       )`
       
and

`  lat = radar.geocode.forward(query=data['place_of_death'][i])[0].latitude # remember to replace column name!
    lon = radar.geocode.forward(query=data['place_of_death'][i])[0].longitude # remember to replace column name!`


and lastly

`data.to_csv("sample_geo.csv")  #remember to replace this with your preferred file name!`

And you're done :)