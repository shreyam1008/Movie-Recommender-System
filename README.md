# Movie Recommender System

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Tech Stack](#tech-stack)
4. [Project Structure](#project-structure)
5. [Setup Guide](#setup-guide)
6. [Usage](#usage)
7. [Data Sources](#data-sources)
8. [Recommendation Algorithms](#recommendation-algorithms)
9. [API Integration](#api-integration)
10. [Future Enhancements](#future-enhancements)
11. [Contributing](#contributing)
12. [License](#license)

## Project Overview

The Movie Recommender System is a Python-based web application that provides personalized movie recommendations using Natural Language Processing (NLP) techniques. Built with Streamlit, this system offers an intuitive interface for users to discover new movies based on various criteria such as similar movies, genres, production companies, and cast members.

## Features

- Multiple recommendation algorithms based on movie attributes
- Detailed movie information display (overview, ratings, cast, etc.)
- Cast information with biographies
- Comprehensive movie list with pagination
- User-friendly interface powered by Streamlit

## Tech Stack

- Python 3.7+
- Streamlit
- Pandas
- NLTK
- Scikit-learn
- Requests (for API calls)

## Project Structure

```
movie-recommender-system/
│
├── main.py                 # Main application file
├── processing/
│   ├── __init__.py
│   ├── preprocess.py       # Data preprocessing and recommendation logic
│   └── display.py          # Display helper functions
│
├── Files/
│   ├── movies_dict.pkl     # Preprocessed movie data
│   ├── movies2_dict.pkl    # Additional movie data
│   ├── new_df_dict.pkl     # Processed dataframe for recommendations
│   ├── similarity_tags_genres.pkl
│   ├── similarity_tags_keywords.pkl
│   ├── similarity_tags_tags.pkl
│   ├── similarity_tags_tcast.pkl
│   └── similarity_tags_tprduction_comp.pkl
│
├── tmdb_5000_credits.csv   # Raw movie credits data
├── tmdb_5000_movies.csv    # Raw movie data
├── requirements.txt        # Project dependencies
└── README.md               # Project documentation
```

## Setup Guide

Follow these steps to set up the Movie Recommender System on your local machine:

1. **Clone the repository**

   ```
   git clone https://github.com/yourusername/movie-recommender-system.git
   cd movie-recommender-system
   ```

2. **Set up a virtual environment** (optional but recommended)

   ```
   python3 -m venv movrecenv
   source movrecenv/bin/activate  # On Windows, use `movrecenv\Scripts\activate`
   ```

3. **Install the required dependencies**

   ```
   pip install -r requirements.txt
   ```

4. **Download the necessary NLTK data(optional, no need to use this)**

   ```
   python3 -c "import nltk; nltk.download('stopwords')"
   ```

5. **Prepare the data (optional to need to do this too)**

   - Ensure that `tmdb_5000_credits.csv` and `tmdb_5000_movies.csv` are in the project root directory.
   - Run the preprocessing script to generate the required pickle files:
     ```
     python3 processing/preprocess.py
     ```

6. **Set up TMDB API(optional, dont do this too, I ave checked this the api key is aleady there and working)**

   - Sign up for a TMDB API key at https://www.themoviedb.org/settings/api
   - Create a `.env` file in the project root and add your API key:
     ```
     TMDB_API_KEY=your_api_key_here
     ```

7. **Run the Streamlit app (Final step to run) Good luck**
   ```
   streamlit run main.py
   ```

The application should now be running on `http://localhost:8501`.

## Usage

1. Open the application in your web browser.
2. Choose one of the following options:
   - "Recommend me a similar movie" ---here you give it a movie name, it gives out similar movie using a recommendation algo.
   - "Describe me a movie" --- here you describe in natural sentence the movie you like to watch, and it recommends you the movie. suing natural language processing.
   - "Check all Movies" -ust a list.
3. Follow the on-screen instructions to explore movie recommendations and details.

## Data Sources

This project uses the TMDB 5000 Movie Dataset, which includes:

- tmdb_5000_movies.csv: Contains movie metadata
- tmdb_5000_credits.csv: Contains cast and crew information

Additional movie details and images are fetched in real-time from the TMDB API.

## Recommendation Algorithms

The system uses several recommendation algorithms based on cosine similarity:

1. Tags-based recommendation
2. Genre-based recommendation
3. Production company-based recommendation
4. Keyword-based recommendation
5. Cast-based recommendation

mainly it has to algorightms.
one for recommendations and
another for natural language processing.

These algorithms use precomputed similarity matrices stored in pickle files for efficient recommendation generation.

## API Integration

The project integrates with The Movie Database (TMDB) API to fetch:

- Movie posters
- Detailed cast information
- Person biographies

Ensure you have a valid API key set up as described in the Setup Guide.

## Thoughts

-editied for dilip singh(singhkdilip18@gmail.com) by shreyam adhikari(shreyam1008@gmail.com)

## Contributing

Contributions to improve the Movie Recommender System are welcome. Please follow these steps:

All right of the original project belongs to
https://github.com/AnupamMittal-21/Movie-Recommender-System?tab=readme-ov-file

This is a forked project with some minor edit(now and later) for the use for testing/school project.
Any stars/credits/contributions to be made on the original repo.

--for contribution.

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
