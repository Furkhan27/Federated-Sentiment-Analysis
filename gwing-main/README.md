#  README — Federated Learning Sentiment Analysis System
### *Flower FL + Hugging Face DistilBERT + Flask Deployment*

##  **Project Summary**
This project implements a complete **Federated Learning (FL) system** for sentiment analysis using the **Flower** framework. Instead of collecting all user data into a central server, model training happens on multiple **simulated client devices**, each holding its own private dataset. The global model is aggregated using **Federated Averaging (FedAvg)**, enabling **privacy-preserving**, distributed machine learning.

A fine-tuned **DistilBERT** NLP model is used as the sentiment classifier, and the final aggregated global model is deployed as a **Flask REST API** for real-time predictions.

This project demonstrates modern industry practices such as FL, privacy-aware ML, NLP model serving, and distributed system orchestration.

##  **Key Features**
- Federated Learning with Flower
- DistilBERT NLP Model
- Multi-client simulation
- Central aggregation with FedAvg
- Flask API deployment

##  Project Structure
```
federated-sentiment/
├── data/
│   ├── raw.csv
│   └── clients/
├── fed_model/
├── src/
│   ├── utils.py
│   ├── split_dataset.py
│   ├── client.py
│   ├── server.py
│   ├── train_local.py
│   ├── visualize.py
│   └── app.py
├── plots/
├── requirements.txt
└── README.md
```

##  Installation
```
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

##  Split Dataset
```
python src/split_dataset.py --raw data/raw.csv --clients 3
```

##  Run Server
```
python src/server.py
```

##  Run Clients
```
python src/client.py --cid 0
python src/client.py --cid 1
python src/client.py --cid 2
```

##  Run Flask API
```
python src/app.py
```

## Test API
POST → http://127.0.0.1:5000/predict  
Body:
```
{
  "text": "This product is amazing!"
}
```

##  Author
MOHAMMED FURQAN SIDDIQ
