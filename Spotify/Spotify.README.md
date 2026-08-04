# Spotify Data Analytics Project

## Project Overview

This project analyzes Spotify track data to explore artist representation, song popularity, danceability, tempo, and other audio characteristics. The goal is to understand which artists and tracks perform strongly and to identify musical features associated with upbeat and highly danceable songs.

## Business Objective

The objective of this analysis is to transform raw music-streaming data into useful insights that could support playlist development, audience targeting, music discovery, and promotional decisions.

## Business Problem

Music-streaming platforms manage large catalogues containing artists and tracks with very different levels of popularity and musical characteristics. Playlist and marketing teams need a reliable way to decide which tracks to feature, which artists to promote, and which songs are suitable for upbeat listening experiences.

Popularity alone does not provide the full picture. An artist may have one highly popular track but limited overall representation, while another may perform consistently across several tracks. Similarly, danceability or tempo considered separately may not accurately identify music that feels energetic. This project addresses the need to evaluate artist performance and audio characteristics together so that content decisions are more focused and data-driven.

## Dataset Overview

The dataset contains information about Spotify artists and tracks, including:

- Artist and track names
- Track popularity
- Danceability and energy
- Tempo and loudness
- Acousticness and instrumentalness
- Speechiness and liveness
- Musical valence, key, and mode
- Track duration and time signature

The data was imported from a CSV file and organized in a SQLite database for analysis.

## Analysis Performed

### Artist and Track Overview

- Reviewed the overall structure and contents of the dataset
- Counted the number of tracks associated with each artist
- Determined the total number of artists represented
- Ranked tracks according to their popularity

### Artist Popularity Analysis

- Evaluated average track popularity for each artist
- Identified artists whose average popularity reached the top-artist benchmark
- Compared the ten artists with the highest average popularity
- Considered both popularity and the number of represented tracks when evaluating artist performance

### Danceability and Tempo Analysis

- Examined danceability and tempo across artists and tracks
- Identified artists associated with highly danceable music
- Explored tracks that combine strong danceability with a faster tempo
- Evaluated the most danceable track represented in the dataset

## Key Analytical Focus

The project is designed to answer questions such as:

- Which artists have the greatest number of tracks in the dataset?
- Which artists achieve the strongest average popularity?
- Which individual tracks rank highest in popularity?
- Which songs are most suitable for upbeat or dance-focused playlists?
- How can danceability and tempo be used together to classify energetic music?

## Skills Demonstrated

- Data preparation and database creation
- CSV data import and validation
- Relational database analysis
- Data filtering, grouping, and ranking
- Aggregate analysis of artist and track performance
- Music-feature comparison
- Translating analytical results into business-focused insights

## Business Value

This analysis can help music and streaming teams:

- Discover popular artists and tracks
- Identify candidates for curated playlists
- Segment tracks according to musical characteristics
- Support promotional campaigns with data-driven artist selection
- Better understand how audio features relate to different listening experiences

## Recommendations

- Prioritize artists with consistently strong average popularity across multiple tracks rather than relying on a single successful release.
- Use highly popular tracks as anchor content in major playlists and promotional campaigns to attract listeners.
- Combine danceability and tempo when selecting songs for workout, party, and upbeat playlists, as either measure alone may not fully represent the listening experience.
- Test highly danceable but less popular tracks in discovery playlists to give emerging artists exposure and measure audience response.
- Create separate playlist segments for popular hits, high-energy music, dance-focused tracks, and emerging discoveries instead of applying one ranking to every use case.
- Use relative benchmarks, such as top-performing groups within the current catalogue, so classifications remain useful when the dataset changes.
- Expand future analysis to include energy, valence, listening completion, saves, skips, and repeat plays before making major promotional decisions.
- Refresh the analysis regularly and track changes in artist and song performance over time.

## Tools Used

- SQLite
- SQLiteStudio
- CSV dataset

## Conclusion

This project demonstrates how Spotify track data can be used to evaluate artist representation, track popularity, and audio characteristics. By considering popularity, catalogue presence, danceability, and tempo together, the analysis provides a stronger foundation for playlist curation, music discovery, audience-focused recommendations, and data-informed promotional planning.
