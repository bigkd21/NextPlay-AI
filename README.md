# NextPlay: The Smart Backlog Manager

Final project for the Building AI course

## Summary
NextPlay is an AI-driven recommendation system designed to cure "gamer's decision paralysis." It analyzes a user's existing library of unplayed games (the backlog) and recommends the perfect game to play next based on the user's current available time, mood, and past gaming history.

## Background
Gamers today face a common problem: "The Backlog." Due to digital sales (like on Steam or PSN) and subscription services (Game Pass), players often own hundreds of games but spend more time scrolling through menus deciding what to play than actually playing.

* **The Problem:** Decision paralysis caused by an overwhelming number of choices.
* **Frequency:** This happens almost daily for avid gamers.
* **Personal Motivation:** I have over 200 games in my library, yet I often default to playing the same multiplayer game because choosing a new single-player adventure feels like too much work.
* **Importance:** This solves a time-management issue and ensures users get value out of the products they have already purchased.

## Data and AI techniques
The project relies on two main data sources:
1.  **User Data:** The user's game library (e.g., via Steam API), including playtime on previous games and user-assigned ratings.
2.  **Global Game Metadata:** Data from sources like *HowLongToBeat* (for game length) and *IGDB* (for genre tags, mechanics, and mood).

**AI Techniques used:**
* **Nearest Neighbor (k-NN):** To find unplayed games in the library that are mathematically similar to games the user has recently rated highly.
* **Content-Based Filtering:** To match game attributes (e.g., "Roguelike," "High Difficulty," "Short Duration") with the user's current input.
* **Linear Regression:** To predict how likely a user is to finish a game based on their history with that specific genre.

## How is it used?
The solution is a web or mobile application acting as a "Gaming Companion."

1.  **Sync:** The user logs in and syncs their library (e.g., Steam/Xbox).
2.  **Input:** The user answers two simple prompts:
    * *Time:* "How much time do you have?" (e.g., 30 mins, 2 hours, all weekend).
    * *Energy:* "How are you feeling?" (e.g., Tired/Relaxed, Energetic/Competitive).
3.  **Process:** The AI filters the backlog. If the user is tired and has 30 minutes, it filters out high-intensity competitive games or 100-hour RPGs.
4.  **Output:** The system presents 3 "Smart Picks" from the user's *own* library.

**Target Audience:** Adult gamers with disposable income to buy games but limited free time to play them.

## Challenges
* **Subjectivity of "Mood":** Defining what makes a game "Relaxing" vs. "Boring" is subjective. The AI might misinterpret a game's vibe without Natural Language Processing (NLP) analysis of reviews.
* **Cold Start Problem:** If a user has a new account with no play history, the AI cannot make personalized recommendations based on past behavior.
* **Data Privacy:** Users may be hesitant to grant access to their full library data and play history.

## What next?
To expand this project, I would like to implement:
* **Natural Language Processing (NLP):** Analyzing user reviews to tag games with "vibe" keywords (e.g., "Cozy," "Stressful") automatically.
* **Co-op Matching:** An algorithm that scans the libraries of *multiple* friends to find a game that everyone owns and everyone is in the mood to play.
* **Calendar Integration:** Automatically suggesting short games during work weeks and long RPGs during holidays.

## Acknowledgments
* Inspiration comes from the "Steam Backlog" community discussions.
* Game length data concepts referenced from [HowLongToBeat](https://howlongtobeat.com/).
* General AI concepts based on the Elements of AI and Building AI courses by Reaktor and the University of Helsinki.
