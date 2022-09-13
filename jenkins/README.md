# image pull

```code
podman pull registry.redhat.io/openshift4/ose-jenkins:v4.10.0-202208150436.p0.gc5b7159.assembly.stream

podman pull registry.redhat.io/openshift4/ose-jenkins-agent-maven:v4.10.0-202209021828.p0.ga4845c1.assembly.stream

```
# ose-jenkins pv,pvc 설정, 생성

```code
oc create -f pv/jenkins-pv-data.yaml
oc create -f pv/jenkins-pvc-data.yaml
```
# ose-jenkins-agent-maven 이미지에 buildah,podman 설치

```code
podman build -t registry.ocp4.local/openshift4/ose-jenkins-agent-maven:v4.10-podman .
podman push registry.ocp4.local/openshift4/ose-jenkins-agent-maven:v4.10-podman .
oc import-image jenkins-agent-maven:v4.10-podman --from=registry.ocp4.local/openshift4/ose-jenkins-agent-maven:v4.10-podman --confirm -n openshift
oc tag jenkins-agent-maven:v4.10-podman jenkins-agent-maven:latest -n openshift

```
# buildconfig jenkinsfile cicd
```code
yaml/jenkins-demo-v1-buildconfig.yaml   # eap
yaml/jenkins-sample-v1-buildconfig.yaml # openjdk
```
