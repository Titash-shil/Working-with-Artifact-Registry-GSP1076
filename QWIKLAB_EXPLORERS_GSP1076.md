# Working with Artifact Registry || [GSP1076](https://www.cloudskillsboost.google/focuses/52830?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

```
export ZONE=
```
```
export REGION="${ZONE%-*}"
export PROJECT_ID=$(gcloud config get-value project)
export PROJECT_NUMBER=$(gcloud projects describe $PROJECT_ID --format='value(projectNumber)')
gcloud config set compute/region $REGION

gcloud services enable \
  cloudresourcemanager.googleapis.com \
  container.googleapis.com \
  artifactregistry.googleapis.com \
  containerregistry.googleapis.com \
  containerscanning.googleapis.com

sleep 10

git clone https://github.com/GoogleCloudPlatform/cloud-code-samples/
cd ~/cloud-code-samples

gcloud container clusters create container-dev-cluster --zone=$ZONE

gcloud artifacts repositories create container-dev-repo --repository-format=docker \
  --location=$REGION \
  --description="Docker repository for Container Dev Workshop"

gcloud auth configure-docker $REGION-docker.pkg.dev

cd ~/cloud-code-samples/java/java-hello-world

docker build -t $REGION-docker.pkg.dev/$PROJECT_ID/container-dev-repo/java-hello-world:tag1 .

docker push $REGION-docker.pkg.dev/$PROJECT_ID/container-dev-repo/java-hello-world:tag1

cd ~/cloud-code-samples/
cloudshell workspace .
```

* *NOW FOLLOW VIDEO'S INSTRUCTIONS CAREFULLY, STEP BY STEP!*

### Run again the following Commands in CloudShell

```
export REGION="${ZONE%-*}"

gcloud artifacts repositories create container-dev-java-repo \
    --repository-format=maven \
    --location=$REGION \
    --description="Java package repository for Container Dev Workshop"
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
