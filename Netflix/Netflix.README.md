# Netflix Catalogue and Content Metadata Analysis

## Project Overview

This project analyzes Netflix title and people data to understand the movie catalogue, examine its release-year range, review recent content additions, and connect individual titles with their directors. The analysis demonstrates how structured catalogue information can support content planning and improve discoverability.

## Business Objective

The objective is to help a streaming platform understand the composition of its movie library and organize creator information more effectively. The project focuses on two practical business questions related to catalogue management and content discovery.

## Business Problem

A streaming platform must manage a large and continuously changing catalogue. Content teams need to know how many movies are available, whether the library offers an appropriate balance of older and newer titles, and when content was most recently added. At the same time, accurate director information is important for search, recommendations, promotional collections, and internal catalogue management.

Without a clear view of both title history and creator information, the platform may overlook gaps in its catalogue or miss opportunities to help viewers discover related content.

## Dataset Overview

The analysis uses two connected datasets:

- A title-information dataset containing title type, title name, release year, and date added
- A people dataset containing director information associated with each title

A common title identifier connects the two datasets and makes it possible to combine catalogue and creator information.

## Business Questions

### 1. How can Netflix evaluate the size and age range of its movie catalogue?

The analysis reviews the number of movies available, identifies the earliest movie release represented, determines the most recent catalogue addition, and organizes titles for easier review. These measures help content teams understand the catalogue’s scale, historical depth, and freshness.

### 2. How can director information improve content organization and discovery?

The analysis connects title records with their corresponding director information. This creates a more complete content profile and can support creator-based search, director collections, recommendations, and promotional campaigns.

## Analysis Performed

- Reviewed the structure of the title and people datasets
- Counted the movies represented in the catalogue
- Determined the most recent date on which content was added
- Organized titles alphabetically for easier catalogue review
- Connected a selected title with its director
- Identified the earliest released movie represented in the dataset

## Recommendations

- Monitor movie count, release-year range, and addition dates together to maintain a balanced catalogue containing both fresh releases and valuable older titles.
- Keep director information complete and accurately connected to every title so viewers can discover content through creator-based searches, collections, and recommendations.
- Create a simple catalogue dashboard that tracks movie volume, oldest and newest releases, recent additions, and missing director details to guide content-acquisition and metadata-quality decisions.

## Skills Demonstrated

- Relational database analysis
- Catalogue and content segmentation
- Date and release-year analysis
- Connecting information across related datasets
- Content metadata validation
- Translating business questions into practical recommendations

## Business Value

This analysis can help content and catalogue teams maintain a more relevant movie library, identify potential content gaps, improve metadata quality, and create better discovery experiences for viewers.

## Tools Used

- SQLite
- Relational database
- Netflix title and people datasets

## Conclusion

This project shows how catalogue and creator data can be combined to support content planning and discovery. Evaluating movie volume, release history, addition dates, and director information gives streaming teams a clearer foundation for managing content and improving the viewer experience.
