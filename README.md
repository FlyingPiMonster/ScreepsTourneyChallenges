# Screeps Tourney Challenges

This repository contains the files for each challenge, including an overview, a rules page, and a machine-readable file.

## Directory Structure

Each challenge has its own directory. Inside that directory are three files.

- **index.md**
Contains an overview of the challenge. Intended to grab people's attention and make them want to participate
- **rules.md** Contains a detailed description of the rules of the challenge
- **info.json** A JSON file describing the challenge
    - **name** _required_ The display name of the challenge
    - **interface** _forbidden_ The URL of the web interface, to be added by the processor
    - **apikey** _forbidden_ The API key to the web interface, to be added by the processor
    - **times** _required_ Deadlines in UTC seconds
        - **submission** _required_ The time the submission period begins
        - **processing** _required_ The time the processing period begins
    - **mods** _optional_ An array of links to GitHub repositories containing the mods that will be used to enforce the game rules. Players may install these mods to test their code; this mod list does not contain the mod responsible for communicating with the web interface. The mod must have `index.js` as its entry point
    - **rules** _required_ A list of rules for the tournament
        - **terrain** _required_ The terrain of the room, in compressed format (a 2500 char string, where 0 means plain, 1 means wall, 2 means swamp)
        - **objects** _required_ An array of the objects in the room.
        - **allowChooseMineral** _default false_ Whether competitors may choose which mineral will be in their room
        - **disallowChooseSpawn** _defailt false_ If true, competitors will not be able to choose the coordinates of their initial spawn.
        - **cpu** _default 30_ How much CPU each player is allowed
        - **constants** _default {}_ A list of constants to be replaced on the server. The server will use `_.extend()` to add these properties to the default constants.
        - **market** _default {}_ An object containing the prices of each resource to buy or sell. If a resource is not present as a key, it will not be bought or sold. If it is present, market orders will be kept filled with 1M of that resource each at the given cost to both buy and sell.

In addition, there is an **index.json** file at the top of the directory structure. This JSON file is an array of the directory names of all challenges, sorted from most to least recent.

Remember to put titles at the tops of all Markdown documents, like this: `(!--title Test Challenge!--)`
