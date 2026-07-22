# Ternion's Localization

This repository allows the community to create and maintain localizations for the video game **Ternion** in languages that are not currently supported.

## Warning

* These files obviously contain spoilers, including content from parts of the game that have not yet been released. So if you're here just to download, make sure not to peek into these text files!
* The English and Italian localizations cannot be modified, as they are hardcoded into the game's source code. They should be used as a reference for both the file structure and the original text.
* My Goody Unsafe Boar takes no responsibility for the contents of community-made localizations. Every localization included in the game will be reviewed before release, but political, vulgar, or otherwise controversial content that may not be recognized as inappropriate due to cultural differences could still be present in community versions. Everything is checked before being imported into the game, but if you import these files manually, you do so at your own risk.

# Creating or Editing a Localization

To create a new localization:

* Create a new ".json" file (global game terms localization) and a ".png" image (flag icon) with the same name inside the "Dictionary" folder.
* Create a new directory in the repository's root folder named after the localization (*localizationName*). This directory will contain the per-scene localization files.

Ternion uses two types of localization files: **Global** localization and **per-scene** localization.

The **global** localization is stored in the "Dictionary" folder. It is a JSON file where each key is the original English term and each value is its translation. For example:

```json
"Counterpoison": "Antidoto"
```

The first string is the key (the English term), while the second is the translated term (Italian in this example).
Some keys do not follow the "English term" rule because they are internal codes. For example, "&idesc_potion" is the key used to retrieve the description of the *Potion* item.
If the game encounters a term or code that is missing from the current localization, it will generate both an error log and a JSON file containing the missing entries in the following location: *\Ternion_Data\Locale\Dictionary\localizationName_untranslated.json*

You can use this file to easily identify untranslated terms. Since it is already in JSON format, you can simply add the translations and merge the entries into the global localization file.

The **per-scene** localization is stored in the directory named *localizationName*. It consists of plain text (".fnt") files named after the corresponding Unity scenes. These files contain dialogue lines and a few additional text entries (such as mission messages).
Make sure that every file contains **exactly the same number of lines** as the corresponding file in the "English" folder, since dialogues are matched by line number.
Many languages (including Italian) have grammatical gender, meaning words may need different forms depending on who is speaking. Because of this, it can sometimes be difficult to determine the correct translation without additional context.
To help with this, the repository includes several **Helper** CSV files. These files are for reference only and do not need to be modified. They provide useful information about each line, such as the speaker and the corresponding line number. If this information is still not enough to determine the correct translation, the only reliable solution is to find the dialogue in-game.

# Branch Management

You are free to work directly on the "**develop**" branch or create a dedicated branch for your language and merge it into "develop" once your work is complete.
The "**master**" branch contains the localizations that will be officially included in the next game update. It will only contain localizations that have been reviewed and verified by native speakers of that language.
It is unlikely that new localizations will be officially included before the game leaves Early Access, since the English localization is still evolving with new scenes and dictionary entries being added over time. Community localizations would therefore require continuous updates to remain complete.
However, any player can manually use the localizations available in the "develop" branch at their own risk, following the instructions provided in the next section.

# How to import a community-made localization into the game

Well, well, well! To import a community-made localization into the game you have to download this Git Repository (press Code > Download ZIP) or to clone this in your PC (if you have the Git application installed). Then, if, for example, you wanted to install the Chinese localization, all you need to do is to copy the "Chinese" folder and the "Dictionary/Chinese.json" and "Dictionary/Chinese.png" files **into the "\Ternion_Data\Locale" folder into the Ternion's game installation folder**. If the "Locale" folder or its "Dictionary" subfolder does not exist you should create them.
Then open the game. By default the game loads the language you select in game properties, but you can override that setting by going into Options on the main menu and Change language. 
