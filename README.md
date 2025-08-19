# BCS2720: AI & ML Module project (academic year 2025-2026)

This repository is for collaborative data collection for the BCS2720 (AI & ML module) project of the [Computer Science BSc programme at Maastricht University](https://www.maastrichtuniversity.nl/education/bachelor/programmes/computer-science), academic year 2025-2026. Groups can submit the data they generate to this repo, such that other groups can also benefit from and use the same data, allowing the class as a whole (consisting of many groups) to collaboratively build up a larger dataset.

## How to contribute data

Students are not granted commiting / pushing rights to the [centralised, official version of this repo](https://github.com/DennisSoemers/BCS2720-project-data-collection-2025-2026). Therefore, it is not possible for students to push data directly. Instead, they are expected to created their own [fork of the repo](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo). There should probably be one fork per group of students, but in principle it is possible to have forks for individual students (or even multiple forks for a single student). In your own fork, you can freely commit and push changes (e.g., adding new data). When you have new changes that you think are ready to be used by the larger community, you can [submit a new Pull Request](https://github.com/DennisSoemers/BCS2720-project-data-collection-2025-2026/pulls) for it to be merged into the repo. This will be reviewed by one of the Project Examiners or Coordinators, and merged if everything seems in order. Please make sure to follow these guidelines:

- Only modify the contents of the directory corresponding to your group. For example, this is the [Group 1](/Group%201) directory for Group 1.
- Make sure to include adequate documentation in your uploaded files, describing the format of your data (what do the rows/columns mean, how were they measured/computed).
- Do not ever delete or overwrite data that has already previously been pushed to the central repository. Even if you no longer intend to be using that data, others might. Include some form of versioning scheme in your filenames / folder structure if new files are just new versions of previous files. Write documentation to make it clear what changed / point out if certain older files turned out to be erroneous or are deprecated for other reasons.
- In addition to data, you could include helper code to handle correct loading of your data.

## How to benefit from other groups' data

While you are not supposed to modify files in the directories of other groups, you are free to download and use them. It is recommended to regularly merge the centralised repo back into your own fork, such that you can work with just a single data repo (your fork) on your machine.

## Notes on licensing

Note that this repository has the [Apache License 2.0](/LICENSE) license, meaning that any data you contribute to it will also be governed by this license. This is a highly permissive, open-source license. In principle, students are expected to primarily / only submit data to this repository that was generated using the [Unity ML-Agents framework](https://github.com/Unity-Technologies/ml-agents), which is governed by the [same license](https://github.com/Unity-Technologies/ml-agents/blob/develop/LICENSE.md). Such data should pose no issues in terms of licensing. For any other data sources, make sure that there are no licensing issues before contributing new data.
