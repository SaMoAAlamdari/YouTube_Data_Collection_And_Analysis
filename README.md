# YouTube Data Analysis & Trending Insights 🎥📊

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Open Source](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://opensource.org/)

A data-driven exploration of YouTube trends and channel analytics using Python and YouTube Data API v3.

## Table of Contents
- [Project Overview](#-project-overview)
- [Features](#-features)
- [Installation](#-installation)
- [Usage](#-usage)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Contributing](#-contributing)
- [License](#-license)

## 📌 Project Overview

This project analyzes YouTube trending videos to discover:
- Trending video characteristics
- Optimal publishing strategies
- Engagement patterns
- Channel growth factors
- Content category performance

Includes a special case study of **MrBeast's channel** (57M+ subscribers).

## ✨ Features

### Data Collection
- Automated API data fetching
- Pagination handling
- Multi-category analysis

### Analytics
```python
# Sample analysis code
def analyze_engagement(df):
    return df.groupby('category')['view_count'].mean().sort_values(ascending=False)
