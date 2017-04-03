# Screeps Tourney Challenges

This repository contains the files for each challenge, including an overview, a rules page, and a machine-readable file.

## Directory Structure

Each challenge has its own directory. Inside that directory are three files.

- **index.md**
Contains an overview of the challenge. Intended to grab people's attention and make them want to participate
- **rules.md** Contains a detailed description of the rules of the challenge
- **info.json** A JSON file describing the challenge
    - **name** _required_ The name of the challenge
    - **times** _required_ Deadlines in UTC seconds
        - **submission** _required_ The time the submission period begins
        - **processing** _required_ The time the processing period begins
    - **mod** _optional_ A link to a GitHub repository containing the mod that will be used to enforce the game rules. This can be used for testing

In addition, there is an **index.json** file at the top of the directory structure. This JSON file is an array of the directory names of all challenges, sorted from most to least recent.
