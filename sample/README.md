# image pull
```code
 podman pull registry.redhat.io/jboss-eap-7/eap74-openjdk8-openshift-rhel7:7.4.6-7
 podman pull registry.access.redhat.com/ubi8/openjdk-8:1.14-3.1661798447
```

# tekton pipeline 권한설정
 
```code
oc adm policy add-scc-to-user anyuid -z pipeline -n sample
oc adm policy add-scc-to-user privileged -z pipeline -n sample
```
