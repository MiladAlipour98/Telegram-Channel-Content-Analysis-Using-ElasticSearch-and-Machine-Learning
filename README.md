# Telegram-Channel-Content-Analysis-Using-ElasticSearch-and-Machine-Learning
This project involves collecting, processing, and classifying data from specific Telegram channels using Python and ElasticSearch. It provides insights into political, sports, and entertainment content by crawling data, storing it in a database, preprocessing text, and training a machine learning model for content classification.
Here’s a structured plan with steps and code snippets to complete the project and document it for a GitHub repository:

## Steps

### Step 1: Retrieve `api_id` and `api_hash` for Telegram API Access
1. Visit [Telegram’s API Development Tools](https://my.telegram.org/apps).
2. Log in with your Telegram account and follow the prompts to obtain the `api_id` and `api_hash`.
3. Document the process and save `api_id` and `api_hash` securely.

### Step 2: Join Telegram Channels
- Channels to join:
  - `@Film_news` (Entertainment)
  - `@varzesh3` (Sports)
  - `@Tasnimnews` (Politics)
- **Optional:** Programmatically join channels within the code for extra functionality.

### Step 3: Crawl and Store First 20 Posts in ElasticSearch
1. Use the Telegram API to retrieve the first 20 posts from each channel.
2. Save the retrieved posts in a local file and send them to ElasticSearch for indexing.

### Step 4: Post a Comment on the Latest Post
- Retrieve the latest post from each channel and post a comment using the Telegram API.

### Step 5: Retrieve and Label the Last 50 Posts from Each Channel
1. Collect the last 50 posts (text only) from each channel.
2. Add a label for each channel:
   - `0` for Politics
   - `1` for Sports
   - `2` for Entertainment

### Step 6: Text Preprocessing
- Preprocess text by cleaning, removing emojis, and other noise.

### Step 7: Save Preprocessed Data with Labels
- Store preprocessed, labeled data in a file for further analysis.

### Step 8: Simple Machine Learning Model for Classification
1. **Choose a model**: Use a basic classifier such as Naive Bayes or Logistic Regression.
2. Split the data into training and testing sets, train the model, and evaluate it.

### Step 9: Model Evaluation
- **Training Accuracy**: Achieved accuracy on the training set.
- **Testing Accuracy**: Achieved accuracy on the testing set, indicating model performance and generalizability.
Using a Support Vector Classifier (SVC) with `random_state=36`, we evaluated the model’s performance on the test set. Here is the detailed classification report:

| Metric        | Class 0 (Politics) | Class 1 (Sports) | Class 2 (Entertainment) | Overall Accuracy |
|---------------|--------------------|-------------------|-------------------------|-------------------|
| Precision     | 1.00               | 0.65             | 0.86                    | **0.79**         |
| Recall        | 0.47               | 1.00             | 1.00                    | -                |
| F1-Score      | 0.64               | 0.79             | 0.92                    | -                |
| Support (No. of Samples) | 15         | 11              | 12                      | -                |

- **Overall Accuracy**: 79%
- **Precision** indicates high accuracy in predicting political (1.00) and entertainment (0.86) content but lower for sports (0.65).
- **Recall** shows that the model captures nearly all true instances for entertainment (1.00) and sports (1.00) but less effectively for politics (0.47).
- **F1-Score** provides a balance between precision and recall, with higher values for entertainment content.

The SVC model performs reasonably well across the categories, particularly excelling in detecting entertainment content, with potential areas of improvement in detecting political content.
## Conclusion
This project provides a complete pipeline for gathering, storing, and analyzing data from Telegram channels. The results highlight the accuracy of a simple machine learning model in classifying content types across different channels.
