# edge-gitops-vms

![Version: 0.2.9](https://img.shields.io/badge/Version-0.2.9-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

Edge GitOps VMs

This chart is used to set up Edge GitOps VMs in conjunction with OpenShift Virtualization

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.clusterDomain | string | `"example.com"` |  |
| global.pattern | string | `"ansible-edge-gitops"` |  |
| job.image | string | `"image-registry.openshift-image-registry.svc:5000/openshift/cli:latest"` |  |
| jobTerminationGracePeriod | int | `3600` |  |
| rbac.roleBindings[0].createBinding | bool | `true` |  |
| rbac.roleBindings[0].name | string | `"view-machine-api"` |  |
| rbac.roleBindings[0].roleRef.kind | string | `"ClusterRole"` |  |
| rbac.roleBindings[0].roleRef.name | string | `"view-machine-api"` |  |
| rbac.roleBindings[0].scope.cluster | bool | `false` |  |
| rbac.roleBindings[0].scope.namespace | string | `"openshift-machine-api"` |  |
| rbac.roleBindings[0].subjects.apiGroup | string | `""` |  |
| rbac.roleBindings[0].subjects.kind | string | `"ServiceAccount"` |  |
| rbac.roleBindings[0].subjects.name | string | `"ansible-edge-gitops-sa"` |  |
| rbac.roleBindings[0].subjects.namespace | string | `"edge-gitops-vms"` |  |
| rbac.roles[0].apiGroups[0] | string | `"machine.openshift.io"` |  |
| rbac.roles[0].createRole | bool | `true` |  |
| rbac.roles[0].name | string | `"view-machine-api"` |  |
| rbac.roles[0].resources[0] | string | `"machinesets"` |  |
| rbac.roles[0].scope.cluster | bool | `true` |  |
| rbac.roles[0].verbs[0] | string | `"get"` |  |
| rbac.roles[0].verbs[1] | string | `"list"` |  |
| rbac.roles[0].verbs[2] | string | `"watch"` |  |
| secretStore.kind | string | `"ClusterSecretStore"` |  |
| secretStore.name | string | `"vault-backend"` |  |
| serviceAccountName | string | `"ansible-edge-gitops-sa"` |  |
| vmDefaults.accessMode | string | `"ReadWriteMany"` |  |
| vmDefaults.cloudInitSecret | string | `"secret/data/hub/cloud-init"` |  |
| vmDefaults.cloudinitsecret | string | `"secret/data/hub/cloud-init"` |  |
| vmDefaults.cores | int | `1` |  |
| vmDefaults.count | int | `1` |  |
| vmDefaults.flavor | string | `"medium"` |  |
| vmDefaults.machineType | string | `"pc-q35-rhel8.4.0"` |  |
| vmDefaults.memory | string | `"4Gi"` |  |
| vmDefaults.os | string | `"rhel8"` |  |
| vmDefaults.ports[0].name | string | `"ssh"` |  |
| vmDefaults.ports[0].port | int | `22` |  |
| vmDefaults.ports[0].protocol | string | `"TCP"` |  |
| vmDefaults.ports[0].targetPort | int | `22` |  |
| vmDefaults.publishService | bool | `false` |  |
| vmDefaults.routeEnableTlsBlock | bool | `false` |  |
| vmDefaults.routeTlsTermination | string | `"passthrough"` |  |
| vmDefaults.routes | object | `{}` |  |
| vmDefaults.serviceType | string | `"NodePort"` |  |
| vmDefaults.sockets | int | `1` |  |
| vmDefaults.sshpubkeyfield | string | `"publickey"` |  |
| vmDefaults.sshsecret | string | `"secret/data/hub/vm-ssh"` |  |
| vmDefaults.storage | string | `"30Gi"` |  |
| vmDefaults.storageClassName | string | `"ocs-storagecluster-ceph-rbd-virtualization"` |  |
| vmDefaults.template | string | `"rhel8-desktop-medium"` |  |
| vmDefaults.threads | int | `1` |  |
| vmDefaults.volumeMode | string | `"Block"` |  |
| vmDefaults.workload | string | `"desktop"` |  |
| vmNamespace | string | `"edge-gitops-vms"` |  |
| vms | object | `{}` |  |
| waitForMetalNode | bool | `true` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
