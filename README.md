# YouTube Trending Videos Analysis 📈

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Open Source](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://opensource.org/)

A data-driven exploration of YouTube trending videos and channel analytics using Python and YouTube Data API v3.


## Table of Contents
- [📌 Project Overview](#-project-overview)
- [✨ Key Features](#-key-features)
- [🛠️ Installation](#-installation)
- [🚀 Usage](#-usage)
- [🔍 Key Insights](#-key-insights)
- [📊 Visualizations](#-visualizations)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)

## 📌 Project Overview

This project analyzes YouTube's trending videos to uncover:
- 🎭 Most popular content categories
- ⏱️ Optimal video duration for engagement
- 📅 Best publishing times
- 🏷️ Impact of tags/metadata
- 📈 Channel growth patterns (with MrBeast case study)

## ✨ Key Features

### 🔄 Data Pipeline
```python
# Sample data collection
from src.data_collection import get_trending_videos

videos = get_trending_videos(api_key=API_KEY, max_results=200)
```

### 📊 Analytics Engine
```python
# Example: Convert ISO duration to minutes
from isodate import parse_duration

def convert_duration(iso_duration):
    return parse_duration(iso_duration).total_seconds() / 60
```

### 📉 Visualization Suite
```python
from src.visualization import plot_engagement_heatmap

plot_engagement_heatmap(df)
```

## 🛠️ Installation

### Clone Repository
```bash
git clone https://github.com/yourusername/youtube-trend-analysis.git
cd youtube-trend-analysis
```

### Install Requirements
```bash
pip install -r requirements.txt
```

### API Setup
Create a YouTube API key at **Google Cloud Console**, then add it to your environment:

```bash
echo 'export YOUTUBE_API_KEY="your_api_key"' >> ~/.bashrc
source ~/.bashrc
```

## 🚀 Usage

### Basic Analysis
```python
# Get trending videos
from src.data_collection import get_trending_videos
df = pd.DataFrame(get_trending_videos(max_results=200))

# Show category distribution
df['category_name'].value_counts().plot(kind='bar')
```

### Channel Analysis
```python
# Analyze specific channel
from src.channel_analysis import ChannelAnalyzer

mrbeast = ChannelAnalyzer('UCX6OQ3DkcsbYNE6H8uQQuVA')
mrbeast.generate_report()
```

### Generate Visualizations
```python
from src.visualization import (
    plot_category_distribution,
    plot_duration_impact,
    plot_publishing_patterns
)

plot_category_distribution(df)
plot_duration_impact(df)
```

## 🔍 Key Insights

| Metric               | Finding                | Impact       |
|----------------------|----------------------|-------------|
| **Peak Engagement Time** | 2-4 PM (Local Time) | +25% 🚀 |
| **Optimal Duration** | 8-12 minutes | +38% ⏳ |
| **Top Category** | Music (32%) vs Gaming (12%) | 🎧 > 🎮 |
| **Tag Effectiveness** | 7-10 tags optimal | +18% 🏷️ |

## 📊 Visualizations

### Engagement Correlation - Heatmap
```python
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title("Engagement Metrics Correlation")
```

### Category Performance
```python
sns.barplot(x='category', y='view_count', data=df)
plt.xticks(rotation=45)
plt.title("YouTube Category Performance")
```

### Publishing Patterns
```python
df['publish_hour'].value_counts().plot(kind='bar')
plt.title("Publishing Time Distribution")
```

## 🤝 Contributing

### Fork the repository
Create your feature branch:
```bash
git checkout -b feature/amazing-feature
```
Commit your changes:
```bash
git commit -m "Add amazing feature"
```
Push to the branch:
```bash
git push origin feature/amazing-feature
```
Then, open a **Pull Request**.

## 📜 License

Distributed under **MIT License**. See [LICENSE](LICENSE) for details.

## 🙏 Acknowledgements

- **YouTube Data API**
- **Pandas Development Team**
- **Matplotlib & Seaborn Communities**
- **Google Cloud Platform**
