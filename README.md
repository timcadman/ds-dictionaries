# Dictionaries used in LifeCycle, Athlete and Longitools
You can add new content and release the dictionaries for all consortia.

## Adding new variables
When you need to add new variables you need to perform 2 steps:
- Adding the new variables to the dictionaries
- Reshaping your data to DataSHIELD backend format

### Adding new dictionaries (data schemes)
When you add new dictionaries you need to place them in ```/dictionaries/x_x```.

For WP1 and 3 these 3 tables are namespaces this way:
- 2_0_core_non_rep.xslx
- 2_0_core_yearly_rep.xslx
- 2_0_core_monthly_rep.xslx
- 2_0_core_trimester_rep.xslx

For WP4, 5 and 6 these tables are created:
- 1_0_outcome_non_rep.xslx
- 1_0_outcome_yearly_rep.xslx
- 1_0_outcome_monthly_rep.xslx
- 1_0_outcome_weekly_rep.xslx

You need to place them into ```R/data/dictionaries/x_x``` as well. 

Finally you need to amend the changelogs, check [amend changelogs](#changelog)

Please use the pull-request flow. For more information check [GIT workflow](https://github.com/lifecycle-project/analysis-tutorials/blob/master/GIT-WORKFLOW.md)

## Dictionary and data versioning in DataSHIELD table names
There are 2 kinds of versioning in the LifeCycle project.

First of all the data dictionary versioning and second the versioning of the data itself. We are using an implementation of semantic versioning ([semantic versioning](https://semver.org)). A better explanation on using semantic versioning in data can be found here: [semantic versioning for data products](https://medium.com/data-architect/semantic-versioning-for-data-products-2b060962093).

## Versioning
We now can distinguish 4 tables for the core variables and 4 tables for the outcome variables. They will be released in 2 sets. One for the core variables and one for the outcome variables.

**Core variables**
* non repeated measures
* monthly repeated measures
* trimester measures
* yearly repeated measures


**Outcome variables**
* non repeated measures
* weekly repeated measures
* monthly repeated measures
* yearly repeated measures


The version-scheme is as follows:

**dictionary-major . dictionary-minor . dictionary-kind . data-major . data-minor . tablename**

*Examples*
* 1_1_dict-kind_1_0_non_rep.xlsx
* 1_1_dict-kind_1_0_weekly_rep.xlsx
* 1_1_dict-kind_1_0_monthly_rep.xlsx
* 1_1_dict-kind_1_0_trimester_rep.xlsx
* 1_1_dict-kind_1_0_yearly_rep.xlsx

*Table names*
* 1_1_dict-kind_1_0_non_rep
* 1_1_dict-kind_1_0_weekly_rep
* 1_1_dict-kind_1_0_monthly_rep
* 1_1_dict-kind_1_0_trimster_rep
* 1_1_dict-kind_1_0_yearly_rep

### Dictionary
We are using semantic versioning in the data dictionary in LifeCycle. The implementation we now use is:

* **Major**
  * Remove columns from the existing tables
* **Minor**
  * Add additional columns to the existing tables
  * Renaming of columns within the exisiting tables (the original column remains in the set)
  * Changing the columntype within the existing tables

### Data
Not only the dictionary has to have a version also the data is versioned within LifeCycle. This is needed because of the reproducability of the research that is going to be performed on the datasets.

The implementation of semantic versioning is as follows.
* **Major**
  * Amending your dataset with new data
* **Minor**
  * Correcting errors in the data (e.g. categories which are encoded the wrong way)

## Changelog
To keep track of all the changed within the different versions of the dictionaries and data releases we need to have changelogs. This way we can trace back what has happened in which release.

### Dictionary releases
* Check: [core dictionary changelog](./changelogs/CORE_DICTIONARY_CHANGELOG.md)
* Check: [outcome dictionary changelog](./changelogs/OUTCOME_DICTIONARY_CHANGELOG.md)


### Data releases
We do not have a cohort specific changelog at the moment.
