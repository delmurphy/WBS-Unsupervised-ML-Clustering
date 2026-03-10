# Automated Playlist Generation with Unsupervised Machine Learning

**Python | pandas | scikit-learn | PCA | K-Means Clustering**

---

## Project Overview

This project explores the use of **unsupervised machine learning** in generating playlists automatically by identifying similarities between songs using their audio features. The case study focuses on **Moosic**, a startup that curates music playlists created by human experts, each designed to capture a specific **mood or musical style**. 

As the company grows, manually creating playlists is becoming difficult to scale. Using a dataset of songs collected from the Spotify API, we apply **unsupervised learning techniques** to group songs into clusters that can serve as prototype playlists.

The goal is not to perfectly replace human curators, but to evaluate how machine learning can **support playlist creation and improve scalability**.

---

## Project Goals

Our prototype model allows us to explore the following questions:

- Can Spotify’s audio features capture **human-perceived similarity between songs**?
- Can clustering algorithms create **cohesive playlists**?
- Is **K-Means clustering** an appropriate approach for this task?
- What improvements or additional data might improve playlist generation?

---

## Tools & Libraries

- Python
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- Jupyter Notebook

---

## Methods

The model uses the following techniques:

**Data preprocessing**
- Cleaning and selecting relevant audio features
- Feature scaling using MinMaxScaler

**Dimensionality reduction**
- Principal Component Analysis (PCA) to simplify feature space

**Clustering**
- K-Means clustering to group songs into playlists.
- Multiple values for the number of clusters (K) were explored to evaluate how playlist size and cohesion changed.
- Different random initialisations were tested to explore how the choice of starting points affected clustering results and silhouette scores.
- The model used multiple initialisations (`n_init=50`) to reduce the impact of random starting points.

**Evaluation**
- Inertia and Silhouette scores to evaluate cluster separation
- Visual inspection and listening tests of generated playlists

---

## Dataset

The dataset contains several thousand songs collected from the **Spotify API**, including audio features such as:

- tempo
- danceability
- energy
- loudness
- acousticness
- instrumentalness
- valence
- speechiness
- liveness

These features describe measurable musical characteristics that may relate to the perceived mood or style of a song.

---

## Project Structure

```
WBS-Unsupervised-ML-Clustering/
│
├── project.ipynb            # Main analysis and model development
├── data/                    # Datasets used for clustering
├── presentation.pdf         # Final presentation slides
├── requirements.txt         # Project dependencies
└── README.md                # Project documentation
```

---

## Installation

Clone the repository and install dependencies:

```
git clone https://github.com/delmurphy/WBS-Unsupervised-ML-Clustering.git
cd WBS-Unsupervised-ML-Clustering
pip install -r requirements.txt
```

Then open the notebook:

```
project.ipynb
```

---

## Results

The clustering algorithm grouped 5171 songs into 91 clusters that represent potential **playlists**. Initial evaluation suggests that some clusters successfully group songs with similar musical characteristics. For example:

<img width="998" height="739" alt="playlist51" src="https://github.com/user-attachments/assets/cdaf3bec-d1a5-4457-b455-e4f40e4c4c06" />

<img width="986" height="721" alt="playlist34" src="https://github.com/user-attachments/assets/9927a788-9ea6-4a7e-821c-86d8bf2aa7b4" />

<img width="984" height="724" alt="playlist7" src="https://github.com/user-attachments/assets/bfffc21f-3e5c-41f1-8e98-ae058210a49a" />

However, the results also highlight some limitations:

**Strengths**
- Scalable playlist creation
- Ability to detect patterns across large datasets
- Potential to discover unexpected song connections

**Limitations**
- Audio features may not fully capture subjective aspects such as mood or cultural context
- K-Means assumes spherical clusters and requires selecting the number of clusters in advance
- Little control over the number of songs in each cluster

---

## Conclusions

This prototype demonstrates that **machine learning can assist playlist generation**, but it should likely complement rather than replace human expertise.

Spotify audio features can capture certain musical similarities, but they do not fully represent the complex ways humans interpret music.

---

## Potential Next Steps

Future improvements could include:

- Testing other clustering methods (DBSCAN, hierarchical clustering)
- Incorporating **genre labels or metadata**
- Using **user listening behavior data**
- Adding **natural language processing on lyrics**
- Developing a hybrid system combining **machine learning and human curation**



