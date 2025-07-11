# 📚 Book Recommendation System

[![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/jupyter-notebook-orange.svg)](https://jupyter.org/)

An intelligent book recommendation system built with Python using the **Apriori algorithm** and **association rules** to suggest books based on user preferences and reading patterns.

## 🎯 Features

- ✨ **Interactive System**: Simple command-line interface for book recommendations
- 📚 **5 Recommendations**: Always returns exactly 5 book suggestions
- 🎯 **Complete Information**: Displays full book titles, authors, and recommendation scores
- 🔍 **Smart Search**: Finds books even with partial title matches
- 📊 **Apriori Algorithm**: Uses association rules based on real purchase data
- 🤖 **Multiple Fallbacks**: Author-based and popularity-based recommendations when needed

## 📋 Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [System Architecture](#system-architecture)
- [Data](#data)
- [Algorithm](#algorithm)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook
- Kaggle API credentials (for dataset download)

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/books_recommendation_system.git
   cd books_recommendation_system
   ```

2. **Create virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Setup Kaggle API:**
   - Download your `kaggle.json` from Kaggle Account Settings
   - Place it in `~/.kaggle/` directory
   - Set permissions: `chmod 600 ~/.kaggle/kaggle.json`

## 💻 Usage

### Quick Start

1. **Open Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Navigate to:**
   ```
   notebook/books_system_recomend_clean.ipynb
   ```

3. **Run all cells** to initialize the system

4. **Start the interactive system:**
   ```python
   interactive_system()
   ```

### Interactive Mode

Once the system is running, you can:

1. **Enter a book title** (e.g., "Harry Potter")
2. **Get 5 personalized recommendations** instantly
3. **Type 'exit'** to quit the system

### Example Usage

```python
# Direct function call
recommendations = search_and_recommend("The Alchemist", n_recommendations=5)

# Interactive mode
interactive_system()
```

## 📁 Project Structure

```
books_recommendation_system/
├── notebook/
│   └── books_system_recomend_clean.ipynb    # Main notebook
├── dataset/                                 # Auto-generated dataset folder
│   ├── Books.csv
│   ├── Ratings.csv
│   └── Users.csv
├── requirements.txt                         # Python dependencies
├── README.md                               # This file
└── venv/                                   # Virtual environment
```

## 🏗️ System Architecture

The system is organized in **8 main sections**:

1. **📦 Library Import** - Essential Python libraries
2. **💾 Data Loading** - Kaggle dataset download and loading
3. **🔧 Data Preparation** - Data cleaning and transaction creation
4. **🧮 Apriori Algorithm** - Association rules generation
5. **🛠️ Auxiliary Functions** - Helper functions for book information
6. **🎯 Main Recommendation System** - Core recommendation engine
7. **💻 User Interface** - Display and interaction functions
8. **🎮 Interactive System** - Command-line interface

## 📊 Data

The system uses the **Book Recommendation Dataset** from Kaggle:
- **271,379 books** with detailed information
- **1,149,780 ratings** from users
- **278,858 users** with demographic data

### Data Processing

- Filters high-quality ratings (≥ 7)
- Focuses on active users (≥ 3 ratings)
- Creates book purchase transactions
- Generates association rules

## 🤖 Algorithm

### Apriori Algorithm

The system uses the **Apriori algorithm** to find frequent itemsets and generate association rules:

```python
association_rules = apriori(
    transactions=transactions,
    min_support=0.001,
    min_confidence=0.1,
    min_lift=1.0,
    min_length=2,
    max_length=2
)
```

### Recommendation Strategy

1. **Primary**: Apriori association rules
2. **Secondary**: Co-occurrence patterns
3. **Tertiary**: Author-based recommendations
4. **Fallback**: Popularity-based suggestions

## 📖 Examples

### Example 1: Fantasy Books
```
🔍 Enter book name: Harry Potter
✅ Found: Harry Potter and the Sorcerer's Stone

📚 RECOMMENDATIONS:
1. 📖 The Lord of the Rings
   👤 J.R.R. Tolkien
   📊 Score: 15.30

2. 📖 The Chronicles of Narnia
   👤 C.S. Lewis
   📊 Score: 12.45
```

### Example 2: Classic Literature
```
🔍 Enter book name: 1984
✅ Found: 1984

📚 RECOMMENDATIONS:
1. 📖 Animal Farm
   👤 George Orwell
   📊 Score: 18.75

2. 📖 Brave New World
   👤 Aldous Huxley
   📊 Score: 14.20
```

## 🛠️ Technical Details

### Dependencies

```python
pandas           # Data manipulation
numpy            # Numerical computing
scikit-learn     # Machine learning utilities
matplotlib       # Data visualization
seaborn          # Statistical plotting
kaggle           # Dataset download
mlxtend          # Apriori algorithm
```

### Key Functions

- `search_books_by_title()` - Search engine for books
- `recommend_books()` - Core recommendation algorithm
- `display_recommendations()` - Format and display results
- `interactive_system()` - Command-line interface

## 🎯 Performance

- **Response Time**: < 1 second per recommendation
- **Accuracy**: Based on real user purchase patterns
- **Coverage**: 270K+ books in database
- **Scalability**: Handles large datasets efficiently

## 🙏 Acknowledgments

- [Kaggle](https://www.kaggle.com/) for the book recommendation dataset
- [Apyori](https://github.com/ymoch/apyori) for the Apriori algorithm implementation
- The open-source community for the amazing tools and libraries

## 📧 Contact

If you have any questions or suggestions, feel free to reach out:

- **GitHub**: https://github.com/zbialaz
- **Email**: eduardobialas74@gmail.com

---

⭐ **If you found this project helpful, please give it a star!** ⭐
