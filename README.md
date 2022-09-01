# Obsidian snippets

This repo is a collection of useful templates and snippets I have created as part of my Obsidian.md usage

## DailyNoteTemplate

My daily note template. Creates an SVG month/year coloured view at the top for noting how far through the year we are. The shared calendar section uses google calendar integration. To set this up, using the community Templater function and gcalcli CLI tool, create a gcalload user function as follows:

```
/usr/bin/gcalcli  agenda --details all --tsv --nodeclined  "`date '+%Y-%m-%d'`" "`date -d '+14 days'`" 
```

## Incomplete Tasks

Data view list showing all checklist items that aren't completed across the vault

## Recent files 

Data view showing ten most recently modified files

## Tags Distribution

Uses obisidian charts and dataviewjs to create a histogram of tags across the vault

## Tasks Chart

Uses obsidian charts and dataviewjs to create a stacked bar chart of complete/incomplete tasks per file

## Dashboard

Combines the above, a couple of map pages not in this repo, and obsidian columns to create a dashboard

![Dashboard screenshot](dashboard.png?raw=true "Obsidian Dashboard")