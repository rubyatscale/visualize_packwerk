# visualize_packwerk

This gem contains rake tasks to help visualize relationships between packwerk packs.

# Usage
## Building a package graph for a selection of packages
```ruby
# Select the packs you want to include
selected_packs = ParsePackwerk.all
selected_packs = ParsePackwerk.all.select{|p| ['packs/my_pack_1', 'packs/my_pack_2'].include?(p.name) }
selected_packs = ParsePackwerk.all.select{|p| ['Team 1', 'Team 2'].include?(CodeOwnership.for_package(p)&.name) }
VisualizePackwerk.package_graph!(selected_packs)
```

# Building a team graph for specific teams
```
# Select the teams you want to include
selected_teams = CodeTeams.all
selected_teams = CodeTeams.all.select{ ... }
VisualizePackwerk.team_graph!(selected_teams)
```

## bin/packs
For simpler use, use `bin/packs` in `use_packwerk` (https://github.com/rubyatscale/use_packwerk)

# Want to change something or add a feature?
Submit a PR or post an issue!
