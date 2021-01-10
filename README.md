# Serverless Deployment on GCP

## Tech stack: ExpressJs | Sqlite | Cloud Run | Container Registry | Docker | GKE | Kubernetes | Spinnaker | Terraform 

### Implementation:

> Preq :monocle_face: : GCP service account, Docker, K8s, Node, Cloud Shell, editor


0. Dockerfile to create Docker image, k8s yaml to create the container
``` 
npm install
npm start
```
1. Set project ID and enable Cloud Shell APIs
```
gcloud config set project [$DEVSHELL_PROJECT_ID]

Enable Cloud Shell APIs
```
[![Enable the APIs](http://gstatic.com/cloudssh/images/open-btn.svg)](https://console.cloud.google.com/flows/enableapi?apiid=container,cloudbuild.googleapis.com,sourcerepo.googleapis.com&_ga=2.185517153.956019484.1610277110-628287784.1609161758)

2. Create and push a Docker image to the Container Registry (REPLACE $DEVSHELL_PROJECT_ID `nordcloud2021` with your current project ID)  
``` 
gcloud builds submit --tag gcr.io/nordcloud2021/gke-test-image:v1.0.0 .
```
3. Create a new GKE cluster to run the web app
``` 
gcloud container clusters create gke-test-cluster --disk-size 10 --num-nodes 2 --enable-autoscaling --min-nodes 2 --max-nodes 8 --zone europe-north1-a
```
4. Apply Kubernetes services. (REPLACE $DEVSHELL_PROJECT_ID `nordcloud2021` with your current project ID in /k8s/deployment.yaml)  
```
kubectl apply -f k8s/
```
5. Check if the k8 is created and accessible. curl loadbalance_EXTERNAL-IP
```
kubectl get services
```
6. Check the log if the container does not work, reasons can be it is creating, invalid params, VPC blocked ports, missing IAM rights.
```
https://console.cloud.google.com/logs/
```
7. Create Continous Deployment pipeline with Cloud Build
```
gcloud beta builds triggers create github \
    --repo-name=[REPO_NAME] \
    --repo-owner=[REPO_OWNER] \
    --branch-pattern=".*" \
    --tag-pattern=[DEV\RELEASE] \
    --build-config=cloudbuild.yaml \
```
10. Clean Up :metal:
```
kubectl delete service gke-test-app
gcloud container clusters delete gke-test-cluster
gcloud container images delete gcr.io/$DEVSHELL_PROJECT_ID/gke-test-image:v1.0.0  --force-delete-tags --quiet
```


# TO DO :rocket:

0. Spinnaker for dev/stage/release; canary, blue/green deployment 

1. Terraform to provision the whole thing

2. Deprecate Sqlite, not scalable, use GCP Cloud SQL in the private VPC.

3. Refactoring the code to JS 2017, update libraries

4. Use microservices instead of monolith. Frontend, authentication, notes.

#  Hung Luu

Notejam source code is cloned from <https://github.com/komarserjio/notejam>
*
Notejam: Express
*

Notejam application implemented using `Express.js <http://expressjs.com/>`_ microframework.

Express version: 4.2

Middlewares/extentions used:

* `Passport.js <http://passportjs.org/>`_ for authentication
* `Node ORM 2 <https://github.com/dresende/node-orm2>`_ for database
* `Mocha <http://mochajs.org/>`_ and `Superagent <http://visionmedia.github.io/superagent/>`_ for testing
* ... and `others <https://github.com/komarserjio/notejam/blob/express/express/notejam/package.json>`_


Installation and launching


Cloning


Clone the repo:

.. code-block:: bash

    $ git clone git@github.com:komarserjio/notejam.git YOUR_PROJECT_DIR/


Install environment

Use `npm <https://www.npmjs.org/>`_ to manage dependencies.

Install dependencies

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ npm install

Create database schema

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ node db.js


Launch


Start built-in web server:

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ DEBUG=* ./bin/www

Go to http://127.0.0.1:3000/ in your browser


Running unit tests


Run unit tests:

.. code-block:: bash

    $ cd YOUR_PROJECT_DIR/express/notejam/
    $ ./node_modules/mocha/bin/mocha tests


Contribution


Please send your pull requests in the ``master`` branch.

Always prepend your commits with a framework name:

.. code-block:: bash

    Express: Implemented sign in functionality
