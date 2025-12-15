# 🚀 Optimizing AI User Experience: Analysis of Daily Assistant Usage Behavior


## 📌 Project Overview
As AI assistants (like ChatGPT, Gemini, Claude) become integral to daily workflows, understanding **user satisfaction drivers** is crucial for optimization. 

This project analyzes the **Daily AI Assistant Usage Behavior Dataset** to answer a critical business question: 
> *"What factors maximize user satisfaction? Is it the model type, the device, or how the user interacts with the AI?"*

Using **Exploratory Data Analysis (EDA)** and **Random Forest (Feature Importance)**, this study uncovers hidden patterns in user behavior and proposes data-driven strategies for cost reduction and UX improvement.

---

## 📊 Key Findings & Insights

### 1. The "167-Word" Rule (User Input)
Contrary to the belief that "AI should understand short commands," the analysis reveals a clear threshold for satisfaction.
* **The Discovery:** User satisfaction remains stagnant (~2.8/5.0) for prompt lengths between 0 and 167 words.
* **The Tipping Point:** Once the prompt length exceeds **167 words**, satisfaction scores jump significantly to **3.20/5.0**.
* **Insight:** Context matters. Detailed prompts lead to significantly better AI responses.

### 2. The "Goldilocks Zone" for Token Usage (System Output)
More is not always better. Analyzing the `Tokens_Used` (combined input + output volume) revealed an optimal range.
* **Low (<512 Tokens):** Satisfaction is average (2.92).
* **Medium (512 - 1020 Tokens):** **Peak Satisfaction (3.14) 🏆**
* **High (>1020 Tokens):** Satisfaction drops (2.90).
* **Insight:** Extremely long responses cause "information overload" and decrease user satisfaction while increasing computational costs.

### 3. Feature Importance (Random Forest)
Machine learning analysis showed that **Interaction Depth (Tokens & Prompt Length)** is far more important than the **Device Type** (Mobile/Desktop) or the **AI Model Brand** in determining user happiness.

---

## 🛠 Methodology

The project followed a structured Data Science pipeline:

1.  **Data Preprocessing:**
    * Converted timestamps to datetime objects.
    * Handled missing values and outliers.
2.  **Exploratory Data Analysis (EDA):**
    * Analyzed distributions of satisfaction across different categories.
3.  **Machine Learning:**
    * Applied **Random Forest Classifier** to determine Feature Importance.
    * Identified that `Tokens_Used` and `Prompt_Length` are the top predictors.
4.  **Statistical Segmentation (Binning):**
    * Used `pd.qcut` to divide data into equal-sized quantiles (Low, Medium, High) to find specific thresholds for Prompt Length and Token Usage.



## 💡 Business Recommendations

Based on the data, the following actions are recommended to improve the product:

1.  **For the UI/UX Team:** Implement a "Prompt Guide" or tooltip that encourages users to provide more context, aiming for the **167+ word threshold**. Short prompts should trigger a gentle suggestion: *"Adding more details helps us give you a better answer."*
    
2.  **For the Engineering/Cost Team:** Limit the maximum response length or encourage the model to be concise. Capping interactions around **1000 tokens** can **reduce API costs** while simultaneously **improving user satisfaction** by avoiding information overload.

---

## 💻 Tech Stack
* **Python:** Core language.
* **Pandas & NumPy:** Data manipulation and statistical analysis.
* **Matplotlib & Seaborn:** Data visualization.
* **Scikit-Learn:** Random Forest implementation for feature importance.



---
