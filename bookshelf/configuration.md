### [🡸 Back to Using Lead](lead/usage.md)
<br>

# Configuring Lead
> Warning: Before configuring Lead, it is recommended that you learn what [YAML](https://www.tutorialspoint.com/yaml/yaml_introduction.htm) is. It is a data serialization language. Meaning that one invalid syntax will result in the plugin to fail.

# Reloading Configuration
You are able to update Lead's configurations without a server restart!
Use `/team reload` to reload all configuration variables.
> Hint: To reload teams without a restart (usually to import backups), you can add the `-t` flag after.

## config.yml
This is the default configuration of Lead as of `v1.1.4`.
> Note: If you wish to change command's publicity, change the value from `null` to `lodestone.lead.commands.[name]`. You can use [LuckPerms](https://luckperms.net) for a permission overhaul.
```yaml, yml
#######################################################################
#                       General Configuration                         #
#  DO NOT TOUCH VERSION! YOU MAY BREAK YOUR CONFIGURATION IF YOU DO!  #
#######################################################################
debug: false
version: 3
max_team_size: 5
default: # What the default setting is for whenever someone creates a team.
  friendly_fire: true
  collidable: ALWAYS # Options: ALWAYS, NEVER, FOR_OTHER_TEAMS, FOR_OWN_TEAM
  name_tag_visibility: ALWAYS # Options: ALWAYS, NEVER, FOR_OTHER_TEAMS, FOR_OWN_TEAM

#########################################################################
#                            Donation Key                               #
# To give our supporters perks, if you wish to remove the join message, #
#  you can input your ko-fi email here and if you have a membership of  #
#    vip or above, your members will no longer receive join messages.   #
#########################################################################
donation_key: null

# Command Permission
# Setting the permission to "null" will make the command public.
commands:
  kick: null
  leave: null
  disband: null
  invite: null
  create: null
  join: null
  teleport: "lodestone.lead.command.teleport"
  chat: null
  friendly_fire: "lodestone.lead.commands.friendly_fire"
  nametag: "lodestone.lead.commands.nametag"
  collidable: "lodestone.lead.commands.collidable"
  merge: "lodestone.lead.commands.merge"
  place: "lodestone.lead.commands.place"
  remove: "lodestone.lead.commands.remove"
  delete: "lodestone.lead.commands.delete"
  id: "lodestone.lead.commands.id"
  display_name: "lodestone.lead.commands.display_name"
  color: "lodestone.lead.commands.color"
  list: null
  help: null

```

# random.yml
If you want to change how Lead creates team names by default, you can read and configure here.
### What Lead Support
- Civilization or Battle Royale Teams
- Color Specific Names
- Hardcoded Unicodes 
- Random Names

```yaml, yml
# This file contains the configuration for the random team generator.

# Name Generator
# Choose how Lead generates team names.
# You can choose one of the four options when lead generate teams:
#   NAME
#     A random name dedicated to the team.
#     Team Names are unique and will not be repeated.
#     Team Colors aren't unique and can be repeated.
#     TIP: Lead will generate up to the size of "available_names" teams.
#   COLOR
#     A random name dedicated to the color of the team.
#     Team Colors are unique and will not be repeated.
#     Team Names are unique and will not be repeated.
#     TIP: Lead will generate up to the size of "available_hex_colors" teams.
#   NUMBER
#     If selected, Lead will generate a random number as the team name.
#     Team Numbers are unique and will not be repeated.
#     Team Colors aren't unique and can be repeated.
#     TIP: Lead will generate up to 1,000 unique teams.
#   UNICODE
#     A custom unicode symbol that you can use.
#     Team Unicodes aren't unique and will be repeated.
#     Team Colors aren't unique and can be repeated.
type: NUMBER # NUMBER, NAME, COLOR, UNICODE

# Default Unicode
#   If specified as UNICODE, Lead will use this unicode for team symbols.
unicode: "■"

# Lead uses this as the baseplate default for team prefixes.
#   Placeholders:
#     {display_name} - The team's display name.
#     {id} - The team's ID.
prefix: "[{display_name}]"

# Random Names
#   A list of names that Lead picks to create team names.
#   TIP: Colors aren't unique and may be repeated.
available_names:
  - "Thunder Turtles"
  - "Mystic Monkeys"
  - "Vivid Vipers"
  - "Stellar Stallions"
  - "Regal Ravens"
  - "Daring Dolphins"
  - "Flash Falcons"
  - "Cunning Coyotes"
  - "Cosmic Cheetahs"
  - "Bold Bison"
  - "Fiery Foxes"
  - "Mighty Mantas"
  - "Swift Swans"
  - "Radiant Raptors"
  - "Gallant Griffins"
  - "Whirlwind Wolves"
  - "Noble Narwhals"
  - "Fierce Falcons"
  - "Golden Gorillas"
  - "Majestic Mustangs"
  - "Sly Serpents"
  - "Brave Baboons"
  - "Tenacious Tigers"
  - "Luminous Lions"
  - "Prancing Panthers"
  - "Regal Rhinos"
  - "Wild Wolves"
  - "Spirited Sparrows"
  - "Mighty Moose"
  - "Raging Rams"
  - "Dynamic Dragons"
  - "Courageous Cougars"
  - "Gleaming Gazelles"
  - "Ferocious Ferrets"
  - "Stormy Stallions"
  - "Zealous Zebras"
  - "Bold Bears"
  - "Spirited Stingrays"
  - "Eager Eagles"
  - "Fearless Falcons"
  - "Valiant Vultures"
  - "Glorious Griffins"
  - "Pouncing Pumas"
  - "Thunderous Tigers"
  - "Spirited Scorpions"
  - "Majestic Mallards"
  - "Dashing Deer"
  - "Mystic Mambas"
  - "Radiant Rattlesnakes"
  - "Vibrant Vultures"
  - "Tenacious Turtles"
  - "Regal Raccoons"
  - "Soaring Swallows"
  - "Agile Antelopes"
  - "Majestic Macaws"
  - "Roaring Raccoons"
  - "Galloping Gazelles"
  - "Whirling Wasps"
  - "Swift Sparrows"
  - "Daring Dragons"
  - "Nimble Newts"
  - "Spirited Sparrows"
  - "Prancing Penguins"
  - "Valiant Vipers"
  - "Bold Bobcats"
  - "Spirited Squirrels"
  - "Eager Eagles"
  - "Fierce Foxes"
  - "Majestic Mambas"
  - "Charging Cheetahs"
  - "Daring Dingoes"
  - "Radiant Ravens"
  - "Gallant Giraffes"
  - "Soaring Swans"
  - "Mystic Manatees"
  - "Spirited Seals"
  - "Spirited Starfish"
  - "Glimmering Gulls"
  - "Spirited Stingrays"
  - "Prancing Peacocks"
  - "Whirlwind Weasels"
  - "Pouncing Pumas"
  - "Thunderous Thrushes"
  - "Luminous Lynxes"
  - "Spirited Storks"
  - "Sly Squirrels"
  - "Vivid Vipers"
  - "Soaring Starlings"
  - "Mystic Minks"
  - "Bold Badgers"
  - "Agile Armadillos"
  - "Valiant Voles"
  - "Swift Sparrows"
  - "Radiant Ravens"
  - "Spirited Skunks"
  - "Gallant Goats"
  - "Fierce Falcons"
  - "Whirling Warblers"
  - "Prancing Ponies"
  - "Tenacious Toads"

# Hex Colors
#   A list of colors that Lead picks to create team colors.
#   Add colors by using hex values.
#   Find colors at: https://www.color-hex.com/
available_hex_colors:
  "#C36BFF": "Purple Pandas"
  "#FF2DEA": "Magenta Monkeys"
  "#FF0569": "Pink Panthers"
  "#FF2600": "Red Ravens"
  "#FF9307": "Orange Otters"
  "#FFFF02": "Yellow Yaks"
  "#6EFF07": "Green Goblins"
  "#89FF89": "Mint Mantises"
  "#5BFFEE": "Teal Tigers"
  "#6D68FF": "Indigo Iguanas"
  "#F59EFF": "Lavender Lemurs"
  "#FFBA8C": "Peach Parrots"
  "#FFF9BC": "Lemon Lions"
  "#B7FFC3": "Seafoam Seals"
  "#89D3FF": "Sky Sharks"
  "#D260FF": "Violet Vultures"
  "#FF665B": "Coral Coyotes"
  "#7FFFBB": "Minty Mambas"
  "#32B0FF": "Azure Antelopes"
  "#FFD700": "Gold Giraffes"
  "#00FF7F": "Spring Green Snakes"
  "#FF4500": "Orange-Red Owls"
  "#8A2BE2": "Blue-Violet Bats"
  "#FF69B4": "Hot Pink Hawks"
  "#00FA9A": "Medium Spring Green Monkeys"
  "#FF1493": "Deep Pink Dolphins"
  "#00BFFF": "Deep Sky Blue Dragons"
  "#40E0D0": "Turquoise Turtles"
  "#FFDAB9": "Peach Puff Penguins"
  "#ADFF2F": "Green Yellow Gorillas"
  "#FF7F50": "Coral Crabs"
  "#BA55D3": "Medium Orchid Owls"
  "#7FFF00": "Chartreuse Cheetahs"
  "#FF6347": "Tomato Toucans"
  "#4682B4": "Steel Blue Stallions"
  "#FF8C00": "Dark Orange Dolphins"
  "#7B68EE": "Medium Slate Blue Minks"
  "#32CD32": "Lime Lizards"
  "#DAA520": "Goldenrod Griffins"
  "#FA8072": "Salmon Swans"
  "#EE82EE": "Violet Vipers"
  "#FF00FF": "Fuchsia Falcons"
  "#FFB6C1": "Light Pink Leopards"
  "#800080": "Purple Pumas"
  "#00FF00": "Lime Lynxes"
  "#7CFC00": "Lawn Green Llamas"
  "#6495ED": "Cornflower Blue Crows"
  "#98FB98": "Pale Green Parakeets"
  "#00CED1": "Dark Turquoise Toucans"
  "#DC143C": "Crimson Coyotes"
  "#20B2AA": "Light Sea Green Lynxes"
  "#B22222": "Firebrick Foxes"
  "#FFDEAD": "Navajo White Newts"
  "#6A5ACD": "Slate Blue Swans"
  "#B0E0E6": "Powder Blue Pelicans"
  "#AFEEEE": "Pale Turquoise Turtles"
  "#DA70D6": "Orchid Owls"
  "#CD5C5C": "Indian Red Iguanas"
  "#F08080": "Light Coral Cougars"
  "#E9967A": "Dark Salmon Swans"
  "#8FBC8F": "Dark Sea Green Dolphins"
  "#5F9EA0": "Cadet Blue Cougars"
  "#D2691E": "Chocolate Chameleons"
  "#FFE4B5": "Moccasin Minks"
  "#DDA0DD": "Plum Penguins"
```

### [Continue to Making Backups 🡺](lead/backups.md)