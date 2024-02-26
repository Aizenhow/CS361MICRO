# CS361MICRO
README FOR MTG CARD FILTER VERSION 1.0.0:

Intro:
For the code it is first ran in Python and you will need to run it locally by using at least the card_filter_service.py given initally.However, a filter_cards_client.py 
is also given for you to test out the code without needing you to make your own client that can make the requests. You must start the
card_filter_service.py file first before using any other file to make a request to the software successfully. The card_filter_service.py uses flask and uses requests as its method
of communication. It also uses the scryfall API's database to filter all magic cards, so no json file is required to be installed locally to use this software.


How to correctly run:
You will be given 5 Filter criterias prompts to go through and type out to help find a card you might be looking for. The Filters to 
use is Colors, type_line ("Hyphens such as Creature — Drake can be replaced with - but still needs either to be filtered correctly), rarity (such as uncommon) mana_cost (Such as {2}{W}{U}), and set_name (such as Starter Commander Decks"). Giving all filter values will usually always show the card unless a bug happens. (the one I know of is below)
If not by itself, results that are very minimal and should show your card you wanted to look up for without scrolling far. You can leave filters blank and will still
get results, but certain sections being left out such as color, rarity might lead to an overabundance of results that can lead with not finding the results.
At the end of this README.txt there are some bugs I have found that I will attempt to fix.

----------------------------------------------------------------------------------------------

This is an example output that works for the program when given the 5 filters:

Enter filter criteria for cards. Leave blank to ignore a criterion.
Color: U,W
Type Line: Legendary Creature — Bird Wizard
Rarity: rare
Mana Cost: {2}{W}{U}
Set Name: Invasion
Filter conditions: {'colors': ['U', 'W'], 'type_line': 'Legendary Creature — Bird Wizard', 'rarity': 'rare', 'mana_cost': '{2}{W}{U}', 'set_name': 'Invasion'}

Filtered cards:
Kangee, Aerie Keeper

Note: The one section that I believe you need to be the most specific on is Mana Cost, as you are required to put the {} around the number or type to be counted correctly. Hyphen or Dash needs to be used as well for Type Lines but anything can be typed out without worrying about case sensitivity.
---------------------------------------------------------------------------------------
Bugs:
For the Database being used (Scryfall API to get all the magic data) their are sometimes mis-translations between specifically Set Names. Because its exact their are some translations such as for Hallowed Fountain, "Ravnica: Clue Edition" when in the database its actually labeled as Ravnica Remastered in the set_name database.
Because of this you will not get a result if you put in a filter that is spelt incorrectly (not case sensitive though). If a card is not found probably remove a filter to find it or change the output of the client file to give you the set_name instead of name so you can find what its stated as in the database.  

