---
layout: workshop      # DON'T CHANGE THIS.
# More detailed instructions (including how to fill these variables for an
# online workshop) are available at
# https://carpentries.github.io/workshop-template/customization/index.html
venue: "American Astronomical Society"        # brief name of the institution that hosts the workshop without address (e.g., "Euphoric State University")
address: "online"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria"), videoconferencing URL, or 'online'
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes) for the institution that hosts the workshop
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the
latitude: "0"        # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "0"       # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "January 7-8, 2021"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "11:00 am - 6:00 pm EST"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2022-01-07      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2021-01-08        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Allen Downey", "Azalee Bostroem", "Rodolfo Montez"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Meredith Rawls", "Iva Momcheva"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["downey@allendowney.com","abostroem@gmail.com"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document (e.g., https://pad.carpentries.org/2015-01-01-euphoria)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}


{% comment %}
{% endcomment %}


{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
Check SWC curriculum
{% endcomment %}

{% if site.carpentry == "swc" %}
{% unless site.curriculum == "swc-inflammation" or site.curriculum == "swc-gapminder" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Software Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>swc-inflammation</code>, or <code>swc-gapminder</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<strong>Some adblockers block the registration window. If you do not see the
  registration box below, please check your adblocker settings.</strong>
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
The Astronomy Curriculum Development Committee (ACDC) is excited to announce a community test drive of the pilot Data Carpentry
workshop for Astronomers. The astronomy-tailored curriculum is designed to provide astronomers with essential skills for data-intensive
analysis and visualization. The curriculum focuses on building complex SQL queries using Astroquery, working with the retrieved data
in Astropy Tables and Pandas DataFrames, storing the data locally for future use, and communicating the results with clear and compelling figures using Matplotlib.

This test drive is designed to vet and improve the curriculum before the lessons are prepared for wider distribution. In particular, we seek participation from folks in the Astronomy community at all stages of their education and careers. Participants are expected to have knowledge equivalent to the Software Carpentry Python Curriculum: the ability to write a function in Python, familiarity with Python built-in types such as lists and dictionaries, and the ability to navigate directories using the command line. In addition, we welcome participants who are familiar with the concepts presented and would like to provide comprehensive feedback on the lessons.

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% assign begin_address = page.address | slice: 0, 4 | downcase  %}
{% if page.address == "online" %}
{% assign online = "true_private" %}
{% elsif begin_address contains "http" %}
{% assign online = "true_public" %}
{% else %}
{% assign online = "false" %}
{% endif %}
{% if page.latitude and page.longitude and online == "false" %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% elsif online == "true_public" %}
<p id="where">
  <strong>Where:</strong>
  online at <a href="{{page.address}}">{{page.address}}</a>.
  If you need a password or other information to access the training,
  the instructor will pass it on to you before the workshop.
</p>
{% elsif online == "true_private" %}
<p id="where">
  <strong>Where:</strong> This training will take place online.
  The instructors will provide you with the information you will need to connect to this meeting.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>). Participants are expected to have knowledge equivalent to the Software Carpentry Python Curriculum: the ability to write a function in Python, familiarity with Python built-in types such as lists and dictionaries, and the ability to navigate directories using the command line.
</p>

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong>
{% if online == "false" %}
  We are committed to making this workshop
  accessible to everybody. The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
{% else %}
  We are dedicated to providing a positive and accessible learning environment for all. Please
  notify the instructors in advance of the workshop if you require any accommodations or if there is
  anything we can do to make this workshop more accessible to you.
</p>
{% endif %}

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact:</strong>
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<p id="roles">
  <strong>Roles:</strong>
  To learn more about the roles at the workshop (who will be doing what),
  refer to <a href="https://carpentries.org/workshop_faq/#what-are-the-roles-of-everyone-participating-in-a-workshop">our Workshop FAQ</a>.
</p>

{% comment %}
WHO CAN ATTEND?

If you would like to specify who can attend the workshop,
you can use the section below.

Move the 'endcomment' tag above the beginning of the following
<p> tag to make this section visible.

Edit the text to match who can attend the workshop. For instance:
- This workshop is open to affiliates to ABC university.
- This workshop is open to the public.
- If you are interested in attending this workshop, contact me@example.com
  for more information

<p id="who-can-attend">
    <strong>Who can attend?:</strong>
    This workshop is open to ....
</p>
{% endcomment %}

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
  <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
    <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
  </a>
</p>
<hr/>


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

https://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.

Note we also have a CodiMD (the open-source version of HackMD)
available at https://codimd.carpentries.org
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{ page.collaborative_notes }}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}


{% comment %}
SURVEYS - DO NOT EDIT SURVEY LINKS
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p>For question 3 "Which of the following workshops are you attending?" please choose
  "I don't know".</p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if site.carpentry == "swc" %}
{% include swc/schedule.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

{% if online != "false" %}
{% include install_instructions/videoconferencing.html %}
{% endif %}

### Jupyter Notebook

For this workshop, we encourage you to work in a Jupyter notebook.
If you are not familiar with Jupyter, you can [run a tutorial by clicking here](https://jupyter.org/try).
Then select "Try Classic Notebook".  It will open a notebook with instructions for getting started.

You will need to install Python, Jupyter, and some additional libraries.
If you don't already have Jupyter, we recommend installing Anaconda, which is a Python distribution that 
contains everything you need to run the workshop code.  It is easy to install on Windows, Mac, and Linux, 
and because it does a user-level install, it will not interfere with other Python installations.

[Information about installing Anaconda is here](https://www.anaconda.com/distribution/).

If you have the choice of Python 2 or 3, choose Python 3.

There are two ways to get the libraries you need:
* You can install them in an existing Conda environment.
* You can create a new Conda environment.

Installing libraries in an existing environment is simpler, but if you use the same environment for many projects, it will get big, complicated, and prone to package conflicts.


#### Install libraries in an existing Conda environment

Most of the libraries we need can be installed using Conda, by running the following commands in a Terminal.

If you are on a Mac or Linux machine, you should be able to use any Terminal.  If you are on Windows, you might have to use the Anaconda Prompt, which you can find under the Start menu.

```
conda install jupyter numpy scipy pandas matplotlib seaborn libopenblas
conda install -c conda-forge astropy astroquery astro-gala python-wget
```

In addition, there's one library we can't install with Conda, so we have to use `pip`:

```
pip install pyia
```

#### Create a new Conda environment

To create a new Conda environment, you'll need to download an environment file from our repository.  On Mac or Linux, you can download it using `wget` on the command line: 

```
wget https://raw.githubusercontent.com/AllenDowney/AstronomicalData/main/environment.yml
```

Or you can [download it using this link](https://raw.githubusercontent.com/AllenDowney/AstronomicalData/main/environment.yml).

In a Terminal or Jupyter Prompt, make sure you are in folder where `environment.yml` is stores, and run:

```
conda env create -f environment.yml
```

Then, to activate the environment you just created, run:

```
conda activate AstronomicalData
```

#### Run Jupyter

Before you launch Jupyter, [download this notebook](https://raw.githubusercontent.com/AllenDowney/AstronomicalData/main/test_setup.ipynb), which contains code to test your environment.

Or you can use `wget` to download it on the command line, like this:

```
wget https://raw.githubusercontent.com/AllenDowney/AstronomicalData/main/test_setup.ipynb
```

To start Jupyter, run:

```
jupyter notebook
```

Jupyter should launch your default browser or open a tab in an existing browser window.
If not, the Jupyter server should print a URL you can use.  For example, when I launch Jupyter, I get

```
$ jupyter notebook
[I 10:03:20.115 NotebookApp] Serving notebooks from local directory: /home/username
[I 10:03:20.115 NotebookApp] 0 active kernels
[I 10:03:20.115 NotebookApp] The Jupyter Notebook is running at: http://localhost:8888/
[I 10:03:20.115 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
```

In this case, the URL is [http://localhost:8888](http://localhost:8888).  
When you start your server, you might get a different URL.
Whatever it is, if you paste it into a browser, you should should see a home page with a list of directories.

Now open the notebook you downloaded and run the cells that contain `import` statements.
If they work and you get no error messages, **you are all set**.

If you get error messages about missing packages, you can install the packages you need using Conda or `pip`.

At the end of the notebook, you'll be asked to copy and paste a line of code from [our Slack workspace](https://app.slack.com/client/T01DJHEP8Q1/C01D2TZA8SH)
to the Jupyter notebook and run it.
The reason for this test is that some environments convert "straight" quotation marks to "smart" quotation
marks, which has the effect of breaking Python code.
If you encounter this problem, you might have to check your system settings to turn off this "feature".


If you run into problems with these instructions, let us know and we will make corrections.  Good luck!
