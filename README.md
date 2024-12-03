### **TravelBot AI: Your Personalized Travel Guide**

---

## **Project Description**
TravelBot AI is a conversational assistant designed to inspire and assist travelers. It simplifies trip planning by providing detailed destination information, suggesting activities, and offering travel tips. By addressing common challenges like information overload, lack of personalization, and time-consuming online searches, TravelBot AI enhances the travel experience by delivering precise, personalized, and engaging travel advice in real time.

---

## **Problem Statement**

Planning travel can often feel overwhelming due to the fragmented and excessive nature of online information. Searching for reliable travel insights can consume significant time, with results frequently falling short of user expectations. Additionally, generative AI systems, while powerful, often suffer from hallucinations—instances where the model generates plausible-sounding but incorrect or unsupported answers. This can mislead users and further complicate the decision-making process for travelers.

### Key Challenges:
1. **Difficulty Finding Trustworthy, Up-to-Date Travel Information**: Online content is vast and inconsistent, making it hard to locate reliable sources for accurate travel details.
2. **Time-Intensive Searches**: Travelers often spend hours searching for relevant information, only to find that the results don’t match their specific needs.
3. **Limited Personalization**: Generalized travel recommendations fail to consider user preferences, making them less actionable.
4. **Lack of Creativity in Recommendations**: Users miss out on unique and inspiring travel ideas due to the generic nature of suggestions.
5. **AI Hallucination Risks**: Language models may generate fabricated or unsupported information, potentially leading to poor decision-making and dissatisfaction.

---

**TravelBot AI addresses these issues by:**
1. **Delivering Reliable and Personalized Travel Advice Quickly**: Leveraging advanced retrieval-augmented generation (RAG) pipelines to provide accurate and relevant responses.
2. **Aggregating Accurate and Targeted Information**: Combining curated datasets with state-of-the-art retrieval models ensures that users receive precise answers to their questions.
3. **Inspiring Users with Creative Travel Ideas**: Going beyond generic advice by offering unique and lesser-known suggestions tailored to user preferences.
4. **Reducing Complexity in Travel Planning**: Streamlining the process by providing instant, actionable insights.
5. **Implementing a Fact-Checking Pipeline**: To combat AI hallucinations, TravelBot AI incorporates a robust fact-checking mechanism. This pipeline:
   - Extracts claims from generated answers.
   - Cross-verifies claims against retrieved evidence.
   - Classifies claims as "Supported," "Not Supported," or "Insufficient Information."
   - Ensures users receive only accurate and verified information. 


## **Datasets**
### **1. SQuAD v2 (Stanford Question Answering Dataset)**
https://huggingface.co/datasets/rajpurkar/squad_v2
- A comprehensive dataset with rich contexts and corresponding questions and answers, filtered to include travel-related topics such as destinations, activities, and budget tips.

---

## **Solution Overview**
TravelBot AI was developed to:
1. **Curate Reliable Travel Information**: Aggregate structured knowledge about diverse destinations and activities.
2. **Personalize Recommendations**: Tailor answers based on user queries, preferences, and specific needs.
3. **Deliver Creative Suggestions**: Inspire users with lesser-known travel ideas.
4. **Save Time**: Provide quick, precise answers, reducing the need for prolonged searches.
5. **Guarantee Quality**: Ensure high relevance and accuracy of responses through robust evaluation.

---

## **Pipeline Implementation**
The chatbot utilizes a **Retrieval-Augmented Generation (RAG)** framework to deliver accurate and context-aware answers. Key components include:

1. **Retriever Model**: 
   - **ChromadbRM**, leveraging M3 embeddings to fetch the most relevant contexts from the dataset.
   https://www.trychroma.com/
2. **Generator Model**: 
   - **Mistral 7B** via **Ollama**, generating coherent, context-driven responses.
   https://huggingface.co/mistralai/Mistral-7B-v0.1
   https://github.com/ollama/ollama
3. **DSPy Framework**: 
   - Integrates retrieval and generation seamlessly for a unified user experience.
   https://github.com/stanfordnlp/dspy
   https://dspy.ai/
---

## **Examples**

### **Example 1**
**Question**: "What is another name for Universal Studios Inc.?"
- **Answer**: "One of the names for Universal Studios Inc. is Universal Pictures, as it is one of their subsidiaries that focuses on motion picture production."
- **Context**: 
  - *"Universal Studios Inc. (also known as Universal Pictures) is an American film studio, owned by Comcast through its wholly owned subsidiary NBCUniversal..."*
  - *"In 1964 MCA formed Universal City Studios, Inc., merging the motion pictures and television arms of Universal Pictures Company and Revue Productions..."*

### **Example 2**
**Question**: "I am a student that almost broke. When is the cheapest time to visit New York City?"
- **Answer**: "The cheapest time to visit New York City is typically in January or February, as the cold weather reduces tourist demand, leading to lower prices for accommodations and flights."
- **Context**: 
  - *"To keep expenses under control, consider free or low-cost activities such as exploring Central Park, Times Square, and the Brooklyn Bridge..."*
  - *"Look for budget accommodations in Long Island City, Brooklyn, or Hoboken, and take advantage of student discounts on attractions."*

---

## **Evaluation Framework**
The chatbot's performance was rigorously evaluated using:
1. **Precision**: Measures the accuracy of the retrieved information.
2. **Recall**: Evaluates the completeness of the responses.
3. **F1-Score**: Balances precision and recall.
4. **ROUGE**: Evaluates linguistic overlap:
   - ROUGE-1 (unigram overlap)
   - ROUGE-2 (bigram overlap)
   - ROUGE-L (longest common subsequence)
5. **BLEU**: Measures the similarity of generated answers to reference answers.

---

## **Critical Thinking: How the Problem Was Addressed**
1. **Dataset Integration**: Leveraged SQuAD v2 to provide structured and unstructured data relevant to travel.
2. **RAG Pipeline Implementation**: Built a retrieval and generation pipeline using **DSPy** for precise, context-aware answers.
3. **Performance Optimization**: Designed and implemented an evaluation pipeline to improve response quality using NLP metrics.
4. **User-Centric Design**: Focused on delivering quick, personalized, and actionable information to enhance the user experience.

---

## **Critical Thinking: Future Enhancements**
1. **Dynamic Information Retrieval**: Integrate APIs for live data such as flight prices, events, and weather updates.
2. **Enhanced Personalization**: Use advanced machine learning techniques to model user preferences.
3. **Multimedia Features**: Incorporate images and videos to create a more immersive experience.
4. **Expanded Knowledge Base**: Broaden the dataset and integrate with trusted travel platforms.

---

## **Installation and Usage**

### **Prerequisites**
- Python 3.10+
- Install dependencies:
  ```bash
    !pip install dspy-ai
    !pip install dspy-ai[chromadb]
    !pip install chromadb
    !pip install openpyxl
    !pip install spacy
    !python -m spacy download en_core_web_sm
    !pip install transformers
    !pip install scikit-learn
    !pip install peft
    !pip install -U FlagEmbedding
    !pip install rouge-score nltk
  
  ```

---

## **Acknowledgments**
- **Datasets**: SQuAD v2
- **Frameworks**: DSPy, ChromaDB, Mistral 7B.
- **Wikichat**: This project is fully inspired by this iconic paper: https://github.com/stanford-oval/WikiChat


## **Additional Resources**
- https://github.com/stanford-oval/genie_open_text
- Tutorial: Retrieval-Augmented Generation (RAG): https://dspy.ai/tutorials/rag/
- Build your own RAG and run it locally: Langchain + Ollama + Streamlit: https://dspy.ai/tutorials/rag/


TravelBot AI is designed to make your travel planning seamless, efficient, and inspiring. 🚀
