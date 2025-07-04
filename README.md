# Music Trends Analysis (1921–2020)

## Introduction  
This project explores the evolution of music trends over the past century (1921–2020) using a dataset of 160,000 Spotify tracks. By analyzing shifts in genres, audio features, and popularity, we aim to uncover cultural and technological influences on music. This analysis can help artists, labels, and streaming platforms understand historical trends and anticipate future shifts.

## Problem Statement  
Music reflects cultural and technological changes, but quantifying these shifts remains challenging. This project investigates:  
- How genres have risen or declined in popularity.  
- How key audio features (e.g., loudness, danceability) have evolved.  
- Which features correlate most with a track’s popularity.  
- Whether these trends can inform predictions about future music trends.  

## Objectives  
1. **Genre Trends**: Analyze changes in genre representation over time.  
2. **Audio Feature Trends**: Track shifts in danceability, energy, loudness, and other features.  
3. **Popularity Correlations**: Identify which audio features most influence track popularity.  
4. **Song Duration**: Examine how track lengths have changed across decades.  

## Target Audience  
- **Artists & Producers**: Understand trends to inform creative decisions.  
- **Music Labels**: Identify market opportunities based on genre popularity.  
- **Streaming Platforms**: Optimize recommendations and playlists.  
- **Festival Organizers**: Book artists aligned with current trends.  

## Dataset  
**Source**: [160k Spotify Songs (1921–2020)](https://www.kaggle.com/datasets/fcpercival/160k-spotify-songs-sorted)  

### Columns & Data Types  
| Column | Data Type | Description |  
|--------|-----------|-------------|  
| `id` | `string` | Unique track identifier |  
| `name` | `string` | Track title |  
| `artists` | `string` | Artist(s) |  
| `duration_ms` | `int` | Track length in milliseconds |  
| `year` | `int` | Release year |  
| `acousticness` | `float` | Confidence measure (0.0–1.0) of acoustic quality |  
| `danceability` | `float` | Suitability for dancing (0.0–1.0) |  
| `energy` | `float` | Perceptual intensity (0.0–1.0) |  
| `instrumentalness` | `float` | Likelihood of no vocals (0.0–1.0) |  
| `loudness` | `float` | Overall loudness (dB, typically negative) |  
| `speechiness` | `float` | Presence of spoken words (0.0–1.0) |  
| `tempo` | `float` | Estimated BPM |  
| `popularity` | `int` | Spotify’s popularity score (0–100) |  
| `broad_genre` | `string` | General artist genre |  
| `subgenre` | `string` | Specific artist subgenre |  

## Data Handling  
1. **Null Values**: Identified and handled missing data.  
2. **Column Removal**: Eliminated irrelevant columns.  
3. **Data Type Validation**: Ensured correct typing (e.g., `year` as integer).  
4. **Text Cleaning**: Removed special characters from artist names.  
5. **Duplicates**: Dropped duplicate tracks.  
6. **Outliers**: Removed implausible loudness values (>0 dB).  
7. **Feature Engineering**:  
   - Added `decade` and `track_length` (short/medium/long) categories.  
   - Mapped subgenres to broad genres using Spotify API; supplemented with GPT-3.5 Turbo for missing entries.  

## Analysis and Findings  
### Genre Trends by Era  
- **1921–1959 (Pre-Digital)**: Classical (23.4%), Folk (20.5%), Jazz (13.3%).  
- **1960–1999 (Rock & Roll)**: Rock (30.3%), Pop (10.5%), Jazz (7.6%).  
- **2000–2010**: Rock (21.3%), Hip Hop (15%), Pop (14.1%).  
- **2011–2020 (Streaming Era)**: Hip Hop (24.1%), Pop (21.3%), Rock (8.4%).  

### Audio Feature Trends  
- **Loudness**: Consistently increased over time.  
- **Danceability**: Declined mid-century, then rose sharply post-2000.  
- **Tempo & Energy**: Steady increase over decades.  
- **Acousticness & Instrumentalness**: Significant decline.  

### Popularity Correlations  
- **Positive**: Energy (+), Loudness (+).  
- **Negative**: Acousticness (–), Instrumentalness (–).  

### Track Duration  
- Average duration peaked in the 1990s–2000s, then dropped sharply after 2015 (likely due to streaming-driven shorter formats).  

## Recommendations  
1. **Genre Flexibility**: Artists should consider blending Hip Hop or Pop elements, as these dominate modern trends.  
2. **Production Priorities**: Focus on higher energy, louder tracks with vocals.  
3. **Track Length**: Aim for <3 minutes to align with current listener preferences.  
4. **Data Expansion**:  
   - Collaborate with platforms (e.g., Anghami) to include regional data.  
   - Address genre limitations (current tags are artist-based, not track-based).  

## Limitations and Assumptions  
- **Biases**: Spotify’s popularity metric favors recent tracks.  
- **Audio Features**: Algorithmically generated; potential inaccuracies.  
- **Representation**: Assumes the dataset reflects broader music trends.  
- **Geographic Gaps**: No regional breakdowns for localized trends.  

---  
*Note: This analysis focuses on aggregate trends; individual exceptions may exist.*  