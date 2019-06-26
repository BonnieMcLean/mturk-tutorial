# Mechanical Turk tutorial


## Pratical part

### 1. Set up MTurk account

Follow Steps 1-3 on the following website:

https://docs.aws.amazon.com/AWSMechTurk/latest/AWSMechanicalTurkGettingStartedGuide/SetUp.html

### 2. Install Submiterator

(instructions vary on Windows and may slightly vary on Linux.)

1. Install the boto3 and the xmltodict packages by running the following commands on the console:

    ```
    pip3 install boto3
    pip3 install xmltodict
    ```

2. Clone the [Submiterator repo](https://github.com/sebschu/Submiterator)

    ```
    git clone https://github.com/sebschu/Submiterator
    ```

3. Edit your bash profile file 

    Open the bash profile file:

    ```
    open -e ~/.bash_profile
    ```

    Add the following lines to your bash profile file:

    ```
    export MTURK_ACCESS_KEY=<YOUR MTURK ACCESS KEY>
    export MTURK_SECRET=<YOUR MTURK SECRET>

    PATH=$PATH:~/bin

    ```

4. Create a symbolic link to submiterator

    ```
    cd ~
    mkdir bin
    cd bin
    chmod u+x [PATH_TO_SUBMITERATOR_DIRECTORY]/supersubmiterator.py
    ln -s [PATH_TO_SUBMITERATOR_DIRECTORY]/supersubmiterator.py submiterator
    ```

5. Close and re-open the console

6. Test `submiterator`:

    ```
    submiterator -h
    ```
### 3. Fork this repsitory

Click on the "Fork" button in the top-right corner of this page.

### 4. Activate GitHub pages

1. Go to "Settings". 
2. Scroll down to the section "GitHub Pages".
3. Under "Source" select "master branch".
4. Test the experiment at https://<YOUR_GITHUB_USERNAME>.github.io/mturk-tutorial/experiment/experiment.html .
5. Once you reach the end of the experiment, you should see a grey box at the bottom with your responses.


### 5. Clone the forked repository

```
git clone https://github.com/[YOUR_GITHUB_USERNAME]/mturk-tutorial
```

### 6. Configure the MTurk experiment

1. In your repository, create a directory called `mturk`.

2. In the `mturk` repository, create a file `my_experiment.config`.

3. Copy the contents of the [example config file](https://github.com/sebschu/Submiterator#how-to-use-supersubmiterator-mturk-tools) into your config file.

4. Edit the config file. Make sure that `liveHIT` is set to `"no"`! Together with your neighbor, try to figure out what all the options mean.

### 7. Add the `mturk` directory to `.gitignore`

You don't want to upload the raw data, which contains the MTurk worker IDs, to GitHub.
One way to achieve this is to add the `mturk` directory to `.gitignoe`. 
Entries in `.gitignore` are not tracked as part of the repository.

1. In the console, go to the root directory of your repository

2. Open the `.gitignore` file

    ```
    open -e .gitignore
    ``` 

3. Add `mturk` in a separate line to the file and save and close it.

4. Commit the file.

    ```
    git commit -m 'Update .gitignore'
    ```

### 8. Post the HIT to the MTurk sandbox

From the directory with the `my_experiment.config` file, run:

```
submiterator posthit my_experiment
```

### 9. Test the experiment on MTurk

1. Copy the URL that submiterator outputs and open it in your browser.

2. Complete the experiment.

### 10. Download the results

From the directory with the `my_experiment.config` file, run:

```
submiterator getresults my_experiment
```




