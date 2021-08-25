# CS 70 Website

## How to build the website locally

You can build the website locally, if you would like to preview changes before deploying them.

1. Install jekyll (see [here](https://jekyllrb.com/docs/installation/) for platform-specific instructions)
    a. After installing all the necessary prerequisites, initialize the Gemfile. The sequence may look something like this (on Linux):
    ```bash
    # install Ruby/prerequisites
    sudo apt-get install ruby-full build-essential zlib1g-dev
    # set correct PATH variables
    echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
    source ~/.bashrc
    # install Jekyll and Bundler
    gem install jekyll bundler
    # navigate to the project directory and initialize a Gemfile
    bundle init
    # add Jekyll to the Gemfile
    bundle add jekyll
    # you should now be good to go!
    ```
    
2. Run `bundle exec jekyll serve` to serve the local site on `localhost:4000`. Ctrl-C to stop the server from building.

## How to upload lecture slides

Relevant directories:
- `/assets/lec` - the directory for the lecture PDFs
- `/_data/materials` - the directory for data about course materials.

1. Upload the straight PDFs into `/assets/lec`, so that the website can serve them
2. Now we need to tell the website to display the materials on the front page.

    Find the `/_data/materials/lectures_n.yml` file, where `n` is the current week of the semester. It probably looks something like this:

    ```yml
    - type: lec
      date: '9/9'
      week: 3
      title: 'Fast Fourier Transform II'
      reading_text: ['2.6']
      webcast: https://www.youtube.com/watch?v=6M5bzFQTFew
      resources:
        - name: 'slides'
          url: '/assets/lec/lec-5.pdf'
    - type: lec
      date: '9/11'
      week: 3
      title: 'Fast Fourier Transform III, Graphs I'
      reading_text: ['2.6', '3.1']
      webcast: https://www.youtube.com/watch?v=22ttvG717oM
      resources:
        - name: 'slides'
          url: '/assets/lec/lec-6.pdf'
        - name: '6up'
          url: '/assets/lec/lec-6-6up.pdf'
        - name: 'handout'
          url: '/assets/lec/lec-6-handout.pdf'
    - type: lec
      date: '9/13'
      week: 3
      title: 'DFS, DAG, Linearization'
      reading_text: ['3']
    ```

    Let's say we're uploading to the lecture on `9/13`. Then add a `resources` key to the lecture, and add all the relevant materials. For example, if we wanted to add slides, 6up, and handout, we would transform the file to this:

    ```yml
    - type: lec
      date: '9/9'
      week: 3
      title: 'Fast Fourier Transform II'
      reading_text: ['2.6']
      webcast: https://www.youtube.com/watch?v=6M5bzFQTFew
      resources:
        - name: 'slides'
          url: '/assets/lec/lec-5.pdf'
    - type: lec
      date: '9/11'
      week: 3
      title: 'Fast Fourier Transform III, Graphs I'
      reading_text: ['2.6', '3.1']
      webcast: https://www.youtube.com/watch?v=22ttvG717oM
      resources:
        - name: 'slides'
          url: '/assets/lec/lec-6.pdf'
        - name: '6up'
          url: '/assets/lec/lec-6-6up.pdf'
        - name: 'handout'
          url: '/assets/lec/lec-6-handout.pdf'
    - type: lec
      date: '9/13'
      week: 3
      title: 'DFS, DAG, Linearization'
      reading_text: ['3']
      resources:
        - name: 'slides'
          url: '/assets/lec/lec-7.pdf'
        - name: '6up'
          url: '/assets/lec/lec-7-6up.pdf'
        - name: 'handout'
          url: '/assets/lec/lec-7-handout.pdf'
    ```

    See [6ab7ab73](https://github.com/Berkeley-CS170/Website/commit/6a7ab7301b359b632adb326ce113f42cd9d16e12) for an example of a diff uploading lecture resources.

## How to upload homeworks/discussions and solutions

Relevant directories:
- `/assets/pdf` - the directory for the homework/discussion PDFs
- `/_data/materials` - the directory for data about course materials.

1. Upload the straight PDFs into `/assets/lec`, so that the website can serve them
2. Now we need to tell the website to display the materials on the front page.

    For homework, find the `/_data/materials/hw.yml`. For discussions, find `/_data/materials/dis.yml`.
    It probably looks something like this:

    ```yml
    - type: dis
      num: 4
      name: '04'
      posted: true
      solutions: true
      weeks: [4]
    - type: dis
      num: 5
      name: '05'
      posted: false
      solutions: false
      weeks: [5]
    - type: dis
      num: 6
      name: '06'
      posted: false
      solutions: false
      weeks: [6]
    ```

    Let's say we're uploading discussion 5. Then add a file called `dis05.pdf` to `/assets/pdf`, and mark the `posted` key as true. For example, for discussion 5 we changed the key to:

    ```yml
    - type: dis
      num: 4
      name: '04'
      posted: true
      solutions: true
      weeks: [4]
    - type: dis
      num: 5
      name: '05'
      posted: true
      solutions: false
      weeks: [5]
    - type: dis
      num: 6
      name: '06'
      posted: false
      solutions: false
      weeks: [6]
    ```

    Similarly, if you are uploading solutions, add a file called `dis05-sol.pdf` to `/assets/pdf`, and mark `solutions` as true:

    ```yml
    - type: dis
      num: 4
      name: '04'
      posted: true
      solutions: true
      weeks: [4]
    - type: dis
      num: 5
      name: '05'
      posted: true
      solutions: true
      weeks: [5]
    - type: dis
      num: 6
      name: '06'
      posted: false
      solutions: false
      weeks: [6]
    ```

    The homework file looks almost exactly the same, and the process is the same.

## How to change the calendar
Relevant files: 
- `_layouts/calendar-layout.html` - the file generating CSS/calendar formatting
- `pages/calendar.html` - a short config file for what the calendar should display

1. Generate a Google Calendar API key.
2. Create your calendar and make it viewable to everyone (not just @berkeley.edu users).
3. In `_layouts/calendar-layout.html`, change the link at the top to the link to your calendar (and change the semester if needed). Change the `googleCalendarApiKey: [key]` to your generated API key.
4. In `pages/calendar.html`, change `calendar_id` to the one shown in the settings in your created calendar. Also, change `range_start` and `range_end` to the start and end dates of your semester.

