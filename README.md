# Application starter kit

## What is this ? 

This project is a starter kit that can easily deploy a web application using Java + Spring Boot as backend and React as frontend. The apps will be deployed on Google Cloud Platform.

## GCP : Create project in GCP (Optional)

If you already have an existing project in Google Cloud, you can use it and skip this step. If you want / need to create a new one, create it here :

https://console.cloud.google.com/projectcreate

You maye want to specify a custom project-id as well, so be sure to click "EDIT" below the project name.

Set this project in gcloud CLI using 

```
gcloud config set project <project-id>
```

## GCP : Enable Cloud Build API (takes a few minutes)

```
gcloud services enable cloudbuild.googleapis.com
```

## GCP : Enable Kubernetes Engine API (takes a few minutes)

```
gcloud services enable container.googleapis.com
```

## GCP : Create cluster (takes a few minutes)

```
gcloud beta container --project "gcp-starter-kit" clusters create-auto "gcp-starter-kit" --region "us-central1" --release-channel "regular" --network "projects/gcp-starter-kit/global/networks/default" --subnetwork "projects/gcp-starter-kit/regions/us-central1/subnetworks/default" --cluster-ipv4-cidr "/17" --binauthz-evaluation-mode=DISABLED
```

## JAVA : change for your needs

The backend app is just named 'backend'. You can change it if you want. Note the line `application.name` in the `application.properties` file. 

## Add IAM accounts

