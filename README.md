# lab-tekton

git clone https://github.com/lcolagio/lab-tekton.git
cd lab-tekton


# Init Pipeline

oc new-project devsecops


oc apply -f pipeline/task-apply-manifests.yaml
oc apply -f pipeline/pipeline-build-and-deploy.yaml

# Execute pipeline

tkn pipeline start build-and-deploy -w name=shared-workspace,volumeClaimTemplateFile=pipeline/pvc-pipeline.yaml




