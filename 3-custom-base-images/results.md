# Measure the impact!

Commit your data here

App1 original build time: 161.4s
App2 original build time: 6.8sec => 0.6sec even after running docker builder prune
Ran docker builder prune -a => 158.7
Custom base build time: 133sec
Better app 1 built time: 6.6sec after pruning all... is this because the custom image already has everything baked in...?

If we had 5 projects using the custom base image, what would you estimate the impact to be?

(Spoilers)
App2 original number of cached layers: 15