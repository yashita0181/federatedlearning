FEDERATED LEARNING USING SECURE MODEL AGGREGATION

In this project:
On the client side, each federated learning client begins by loading its local dataset from .npy files, which are simple, structured NumPy arrays. The model used is a lightweight neural network—specifically, a Softmax-based model—suitable for classifying numbers from 1 to 10. After local training, we securely share encrypted gradients using PySyft, which ensures that raw model updates are never exposed during transmission. These updates are sent over network services to a central aggregator for further processing."\

At the server or aggregator end, the system waits for incoming encrypted model updates from all clients. These updates are securely aggregated using PySyft’s privacy-preserving protocols. Once aggregated, the server updates the global model and broadcasts the new global parameters back to all clients. The system is designed to be robust, meaning that even if some clients are delayed or temporarily unavailable, the training process can continue smoothly.

"For deployment, we use Kubernetes configuration files—client-deployment.yml and aggregator-deployment.yml—to define how the client and aggregator pods operate and interact. We also use Docker Compose and Dockerfiles to simplify local development and manage multiple containers. The training data used in our setup is synthetic and stored in .npy format, such as client_1_data.npy and client_2_data.npy. This makes the whole process reproducible and easily scalable, which is ideal for federated learning experiments."

process and commands:

1.Extract the files client1.py and client2.py to Docker

2.Set the paths and environment of these files in docker-compose.yml file

3.Install python-mnist(pip install python-mnist)

4.Install flask( pip install flask )

5.Run the commands (docker compose up --build client1) and (docker compose up --build client2) separately in two terminals of docker ehich creates two client containers and an aggregator container and runs
