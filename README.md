****GKE Application 10.1P****

1. Create a new kubernetes cluster on your GCP project.
2. Once created connect to your cluster.
3. Before deploying to this project, upload the files contained within this repository onto your cloud shell editor

****Pulling The Image From Docker And Deploying****
1. `gcloud auth configure-docker`
2. `docker pull nichollsb/mongo:v1`
3. `docker tag nichollsb/mongo:v1 gcr.io/<your-project-id-here>/nichollsb:v1`
4. `docker push gcr.io/<your-project-idea-here>/nichollsb:v1`
5. `kubectl apply -f gDeployment.yaml`
6. `kubectl expose deployment my-app  --type=LoadBalancer --port 8080  --target-port 3000`

****Adding the database****

Adding the database is simple, first we'll need to create a persistent disk on the compute engine
1. In the cloud shell, run `gcloud compute disks create my-disk --size=10GB --zone=australia-southeast2-a`
2. `Run `kubectl apply -f gCreatePersistentVolume2.yaml`
3. `Run `kubectl apply -f gCreatePersistentVolumeClaim.yaml`
4. `kubectl apply -f gCreateStorageClass.yaml`
5. `kubectl apply -f gCreateService.yaml`
6. `kubectl apply -f gCreateMongoDeployment.yaml`


Using postman, play around with the Get, Post, Update, and Delete methods as demonstrated in the video below:
https://youtu.be/bIOXIfwChMU

Contributing
If you are interested in contributing to this project, feel free to submit a pull request or open an issue.

License
This project is licensed under the MIT License - see the LICENSE file for details.
