# Lab-tekton-simple

git clone https://github.com/lcolagio/lab-tekton.git

cd lab-tekton

# Init via Manifest K8S

oc delete project devsecops

oc new-project devsecops

oc apply -f pipeline-simple/base/task-apply-manifests.yaml

oc apply -f pipeline-simple/base/pipeline-build-and-deploy.yaml

# Init use case via kustomize

oc delete project devsecops

oc new-project devsecops

oc apply -k pipeline

# Execute Pipeline

tkn pipeline start build-and-deploy -w name=shared-workspace,volumeClaimTemplateFile=pipeline-simple/base/pvc-pipeline.yaml
