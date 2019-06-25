# Mechanical Turk tutorial


## Pratical part

### 1. Set up MTurk account

Follow Steps 1-3 on the following website:

https://docs.aws.amazon.com/AWSMechTurk/latest/AWSMechanicalTurkGettingStartedGuide/SetUp.html

### 2. Install Submiterator

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



