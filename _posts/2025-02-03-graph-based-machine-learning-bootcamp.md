---
title: 'Networked AI bootcamp: from Python to graph neural networks'
date: 2025-02-03
permalink: /posts/2025/02/bootcamp-python-to-gnns/
tags:
  - machine learning
  - artificial intelligence
  - python 
  - graph theory
  - data science
  - networks
  - graph neural networks
---

This tutorial aims to help you get ready to work with graph neural networks from zero. You can always ask Google and ChatGPT for help. For example, 
- _"Hey ChatGPT, explain the following code to me ..."_ 
- _"Explain binary search with Python code"_
- _"I am trying to set up Docker on Windows/Linux/MacOS but got this error"_ 
- _"Recommend some free courses or tutorials for learning Python library NetworkX"_
- _"I want to find XXX from professional and trustworthy sources, but I don't want mix with YYY, what query words I should use on Google/DuckDuckGo/Bing?"_

This post will be updated regularly based on feedback.

## **📌 Module 1: Python & Basics (Weeks 1-2)**
### **Goals**
- Set up development environment
- Set up **GitHub repository** and submit all mini-projects  
- Master **programming fundamentals** (loops, conditionals, recursion, sorting)  
- Gain proficiency in **NumPy** for array/matrix operations and **Pandas**  for tabular data manipulation
- Use **Matplotlib** to visualize real-world datasets  

### **Short Course (~1 Week, Self-paced)**
- **[LearnPython.org](https://www.learnpython.org/)** An interactive tutorial that covers Python fundamentals, including data types, control structures, functions, and modules.
- **[Python for Beginners – Full Course](https://www.youtube.com/watch?v=eWRfhZUzrAc)** 4-hour video tutorial with practical examples.

### **Topics**
#### **1️⃣ Python Fundamentals & Git Setup**
- Install [Python](https://www.python.org/downloads/) and [virtualenv](https://virtualenv.pypa.io/en/latest/installation.html) 
- [PyCharm CE](https://www.jetbrains.com/products/compare/?product=pycharm&product=pycharm-ce) (or [VSCode](https://code.visualstudio.com/download)) & [Jupyter Notebook](https://jupyter.org/install) setup  
- Install libraries `python3 -m pip numpy pandas matplotlib` , learn [how to use `requirements.txt`](https://www.freecodecamp.org/news/python-requirementstxt-explained/)
- **Git Basics:** Creating a repo, committing code, branching, pull requests  
- **Control Flow:** Loops (`for`, `while`), `if-else`, recursion  

✅ **Exercise 1.1: GitHub Repo & Environment Setup**  
- Create a **GitHub repository** and submit future projects here  
- Write a script to **print system information (OS, Python version, libraries installed)**  

#### **2️⃣ Implementing Classical Algorithms**
- **Binary Search:** Recursive & iterative versions  
- **Sorting Algorithms:** Implement **Merge Sort** and **Quick Sort**  
- **Compare Time Complexity:** Measure performance using `time` module  

✅ **Exercise 1.2: Algorithm Implementation & Performance Comparison**  
- Implement **Binary Search (recursive & iterative)**  
- Implement **Merge Sort & Quick Sort**  
- Measure execution time for **sorted vs. unsorted lists of different sizes**  
- **Push project to GitHub**  

#### **3️⃣ NumPy: Array & Matrix Operations**
- **Basic Operations:** Creating, reshaping, slicing arrays  
- **Matrix Operations:** Broadcasting, dot product, matrix multiplication  
- **Performance Comparison:** Vectorized NumPy vs. loops  

✅ **Exercise 1.3: Numerical Computation & Performance Analysis**  
- Create **two large matrices (random data) and perform:**  
  - **Element-wise addition, multiplication, dot product**  
  - **Matrix inversion, determinant calculation**  
- Compare **vectorized NumPy operations vs. naive loops** (measure execution time)  
- **Push project to GitHub**  

#### **4️⃣ Pandas & Matplotlib for Data Exploration**
- **Pandas Basics:** DataFrames, indexing, filtering, `groupby`  
- **Matplotlib Basics:** Histograms, line plots, scatter plots, heatmaps  
- **Download & explore real-world datasets** (e.g., from Kaggle or UCI)  

✅ **Exercise 1.4: Data Analysis & Visualization**  
- **Download a dataset** (e.g., population statistics, weather data)  
- Use **Pandas to clean & analyze the data**  
- Generate **histograms, line plots, scatter plots, heatmaps**  
- **Push project to GitHub**  

---

## **📌 Module 2: PyTorch & TensorFlow (Weeks 3-4)**
### **Goals**
- Understand **deep learning fundamentals**  
- Install and set up **PyTorch and TensorFlow**
- Install **Docker** and run **TensorFlow & PyTorch images with Jupyter Notebook**
- Learn **both PyTorch and TensorFlow** through tutorials  
- Implement **basic ML tasks (MNIST classification, t-SNE visualization, RL agents)**  

### **Short Course (~1 Week, Self-paced)**
- **Deep Learning Basics:** [Deep Learning Specialization -- DeepLearning.ai](https://www.coursera.org/specializations/deep-learning), [YouTube Playlist](https://www.youtube.com/watch?v=CS4cs9xVecg&list=PLkDaE6sCZn6Ec-XTbcX1uRg2_u4xOEky0&index=1)
- **PyTorch & TensorFlow Basics:** Tensors, computation graphs  
- **Recommended Resources:**
  - *Fast.ai's Deep Learning for Coders (first few chapters)*  
  - *TensorFlow & PyTorch official tutorials*  [Learning PyTorch with Examples](https://pytorch.org/tutorials/beginner/pytorch_with_examples.html), [PyTorch for Deep Learning & Machine Learning – Full Course](https://www.youtube.com/watch?v=V_xro1bcAuA)

✅ **Deliverable:** Complete **one tutorial per framework** (PyTorch & TensorFlow)  

### **Hands-on Projects**
#### **1️⃣ Installation & Setup**
- Install PyTorch & TensorFlow (follow official setup guides)
- Check CUDA availability for GPU acceleration
- Install Docker and pull official images for TensorFlow & PyTorch
✅ **Exercise 2.1: Docker Setup for AI Frameworks**

- Install Docker
- Pull TensorFlow 2 Docker image with Jupyter Notebook
- Pull PyTorch Docker image (if available) with Jupyter Notebook
- Run Jupyter Notebook inside Docker and test with a simple tensor operation

#### **2️⃣ Neural Network Basics**
- Train a **basic NN on MNIST**  
- Compare PyTorch vs. TensorFlow implementations  

✅ **Exercise 2.2: MNIST Classification (PyTorch & TensorFlow)**  
- Train & evaluate a **2-layer NN**  
- Compare **accuracy & training time**  
- Modify hyperparameters: change the number of layers, hidden layer dimensions, learning rate

#### **3️⃣ Visualizing Embeddings**
- Apply **t-SNE to MNIST embeddings**  

✅ **Exercise 2.3: t-SNE Visualization**  
- Train a model and visualize **hidden layer embeddings**  

#### **4️⃣ Reinforcement Learning**
- Train RL agents for **CartPole & Lunar Lander**  

✅ **Exercise 2.4: RL for Gym Environments**  
- Train an RL agent for **CartPole**  
- Modify hyperparameters & observe performance changes  

---

## **📌 Module 3: Graphs & NetworkX (Weeks 5-6)**
### **Goals**
- Learn **graph theory concepts** and representation in Python  
- Implement **basic graph algorithms (BFS, DFS, shortest path)**  
- Explore **community detection** using real-world graph datasets  
- Understand **graph visualization** using NetworkX  

### **Topics**

#### **1️⃣ Graph Representation**
- **Graph Basics:** Nodes, edges, adjacency lists, adjacency matrices  
- **NetworkX Fundamentals:** Creating, modifying, and analyzing graphs  
- **Graph Operations:** Node degree, centrality, connectivity  

✅ **Exercise 3.1: Representing & Visualizing Graphs**  
- Create a **synthetic graph** using NetworkX  
- Assign **random edge weights** (like travel time)  
- Visualize graphs using **different layouts**  


#### **2️⃣ Search & Path-Finding Algorithms**
- **Breadth-First Search (BFS) & Depth-First Search (DFS)**  
- **Dijkstra’s Algorithm:** Find shortest paths  
- **A\*** Algorithm: Path-finding with heuristics  

✅ **Exercise 3.2: Graph Search Algorithms**  
- Implement **BFS & DFS** to explore a random graph  
- Implement **Dijkstra’s Algorithm** to find shortest paths  
- Compare **Dijkstra vs. A\*** performance  

#### **3️⃣ Community Detection & Karate Club Graph**
- **What is Community Detection?** Finding groups in networks  
- **Graph Clustering Methods:** Modularity-based detection  
- **Karate Club Graph:** A classic social network dataset  

✅ **Exercise 3.3: Community Detection in the Karate Club Graph**  
- Load the **Zachary's karate club graph** from NetworkX  
- Apply **Louvain or Girvan-Newman community detection**  
- Visualize **detected communities with different colors**  

#### **4️⃣ Graph Visualization & Animation**
- **NetworkX with Matplotlib:** Visualizing graphs  
- **Animating path traversal:** Using Matplotlib’s animation tools  

✅ **Exercise 3.4: Animated Path Traversal**  
- Visualize how BFS/DFS explores a graph  
- Animate the **shortest path found by Dijkstra**  

---

## **📌 Module 4: Graph Neural Networks (GNNs) (Weeks 7-8)**
### **Goals**
- Learn **how GNNs work** and why they are powerful for structured data  
- Implement **basic GNN models** using PyTorch Geometric (PyG) or Deep Graph Library (DGL)  
- Train a **GNN for node classification and link prediction**  

### **Topics**
#### **1️⃣ Introduction to GNNs**
- **Why GNNs?** Limitations of traditional ML for graphs  
- **Message Passing in GNNs**  
- **Common GNN Architectures:** Graph Convolutional Networks (GCNs), Graph Attention Networks (GATs)  

✅ **Exercise 4.1: Implement a Simple GNN**  
- Train a **basic GNN for node classification** on a synthetic graph  
- Compare **GNN vs. traditional ML models**  

#### **2️⃣ Hands-on with PyG / DGL**
- **Data Handling in GNNs:** Graph datasets in PyG/DGL  
- **Building a GNN Model** from scratch  
- **Training & Evaluating a GNN**  

✅ **Exercise 4.2: GNN for Link Prediction**  
- Implement a **GNN to predict missing edges in a graph**  
- Use **GraphSAGE or GAT for link prediction**  

#### **3️⃣ Advanced GNN Topics (Optional)**
- **Graph Transformers & GNN variants**  
- **Real-world applications of GNNs**  

✅ **Exercise 4.3: Experiment with Different GNN Models**  
- Modify a **GCN model** to use **GAT or GraphSAGE**  
- Compare **performance on node classification**  

---

## **📌 Module 5 (optional): Traffic Simulation with CityFlow (Weeks 9-10)**
### **Goals**
- Learn **how to set up and run CityFlow simulations**  
- Understand **how to integrate ML-based control in future work**  

### **Resources**
- [RL for Traffic Signal Control](https://traffic-signal-control.github.io/), [Tutorial](https://bit.ly/RLSignal)
- [CityFlow](https://cityflow-project.github.io/#cta)

### **Topics**
#### **1️⃣ Setting Up CityFlow**
- **Installation & Configuration**  
- **Defining a Road Network**  
- **Running a Basic Simulation**  

✅ **Exercise 5.1: Run a Simple CityFlow Simulation**  
- Create a **basic road network**  
- Run a **simulation with fixed-time signals**  

#### **2️⃣ Modifying Traffic Light Control**
- **Manually adjusting signal timing**  
- **Simulating different traffic conditions**  

✅ **Exercise 5.2: Compare Different Traffic Light Strategies**  
- Simulate **fixed-cycle signals vs. simple adaptive control**  
- Measure **average vehicle delay**  

#### **3️⃣ CityFlow Visualization & Analysis**
- **Extracting simulation data**  
- **Visualizing vehicle movements**  

✅ **Exercise 5.3: Visualizing CityFlow Results**  
- Plot **congestion heatmaps** using Matplotlib  
- Analyze **travel times under different scenarios**  

