# tekton pipeline 권한설정
 
oc adm policy add-scc-to-user privileged -z pipeline -n sample
