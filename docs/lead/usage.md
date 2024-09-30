# Using Lead
Using Lead is pretty straight forward.
# General Commands
These commands are made public upon being teamless.
- To create a team you can use `/team create`.<br>
- To join a team, use `/team join [id]`.<br>
- To view all teams, use `/team list`.

# Team Commands
These commands are restricted to players that are in a team.
- To leave a team, use `/team leave`.
- To invite another person, use `/team invite [player]`.<br>
- To chat with your team, there are 1 of 2 options:
  - Use `/teammsg [msg]` to quick message. (Aliases: `/tm`, `/tc`)
  - Use `/team chat` to toggle your chat.<br>Allowing future messages to be sent directly to your team.

# Leader Commands
These commands are restricted to players who are leader of a team.
- To kick a player from your team, use `/team kick [player]`.
- To disband your team, use `/team disband`

# Staff Commands
These commands are restricted to players with the permission: `lodestone.lead.commands.*`
> [!WARNING]
> Players with vanilla operator status can bypass these permissions.<br />
> If working with a production environment, consider using [LuckPerms](https://luckperms.net/) for a permission overhaul.

> [!TIP]
> It is essential to know that all commands are based off a team's id.<br />
> Id's are **unique** to each team and can be alpha numeric. Assume `team` as the team id.
- To teleport an entire team to an entity, use `/team teleport [team] [entity]`
- To merge two teams into one, use `/team merge [team_one] [team_two]`
- To force place a player into a team, use `/team place [player] [team]`
- To remove a player from a team, use `/team remove [player]`.
- To delete a team, use `/team delete [team]`.

## Modifying a team's attributes
- To modify a team's unique id, use `/team modify id [team] [new_id]`.
- To modify a team's display name, use `/team modify display_name [team] [new_name]`.
- To modify a team's color, use `/team modify color [team] [hex_color]`.
- To modify a team's friendly fire rule, use `/team modify friendly_fire [team] [value]`.
- To modify a team's collision rule, use `/team modify collidable [team] [value]`.
- To modify a team's nametag visibility rule, use `/team modify nametag [team] [value]`. 