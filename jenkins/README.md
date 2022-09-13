# ose-jenkins pv,pvc 설정, 생성

oc create -f pv/jenkins-pv-data.yaml
oc create -f pv/jenkins-pvc-data.yaml

# ose-jenkins-agent-maven 이미지에 buildah,podman 설치

podman build -t registry.ocp4.local/openshift4/ose-jenkins-agent-maven:v4.10-podman .
