**#Core and Named Groups for the Cluster Management**

**Introduction:**
Kubernetes organizes its API into different groups based on their purpose. These groups, similar to sections in a library, hold various resources related to specific themes.

The two main types of groups are the core group and named groups. The core group contains fundamental resources essential to the platform’s operation, such as Pods, Nodes, Namespaces, and Services.

On the other hand, named groups allow you to extend Kubernetes functionality by introducing custom resources and controllers related to specific areas like networking or storage.

This introduction sets the stage for a deeper dive into the API groups and versions and their pivotal role in your Kubernetes journey.

Let’s get started!


Table of Contents: 
. Why there are named groups and core groups
· Named Groups
. Core group

**Why there are named groups and core groups:**

Kubernetes doesn’t put all its eggs in one basket. Instead, it smartly categorizes its API into different groups based on their purpose. Think of these groups like sections in a library, each holding books (or, in this case, APIs) related to a specific theme.

The named groups and core groups in Kubernetes serve distinct purposes, rooted in the platform’s historical and organizational principles.

The core group, also known as the legacy group, encompasses essential resources integral to Kubernetes’ operation, such as Pods, Nodes, Namespaces, and Services. These resources were initially considered so fundamental to Kubernetes that they did not need to be grouped explicitly.

On the other hand, the named API groups, or namespaces, were introduced to categorize resources thematically. For instance, resources related to networking are grouped under networking.k8s.io. This organizational approach allows for the extension of Kubernetes functionality by introducing custom resources and controllers tailored to specific areas, such as networking or storage.

The core group API endpoint is located at /api/v1. On the other hand, the named groups API endpoint is /apis/$GROUP_NAME/$VERSION.

![Model](https://github.com/rangushiva1/k8s-files/blob/main/k8s.png?raw=true)

**Named Groups:**

The named group API in Kubernetes is more organized and groups resources thematically.

It includes groups for apps, extensions, networking, storage, authentication, authorization certificates, and more.

Going forward, all newer features will be made available to these named groups. The named groups allow for the extension of Kubernetes functionality by introducing custom resources and controllers tailored to specific areas, such as networking or storage.

![Model](https://github.com/rangushiva1/k8s-files/blob/main/k8s2.png?raw=true)

The named groups API is located at /apis/$GROUP_NAME/$VERSION.

$GROUP_NAME : the name of your custom resource
$VERSION: the API version of your custom resource.

/apis/$GROUP_NAME/$VERSION
The named group is identified by the $GROUP_NAME included in the apiVersion field.

apiVersion: $GROUP_NAME/$VERSION

**Resources:**

The resources in named groups depend on the specific named group that is being used. The following are some examples of named groups in Kubernetes and their associated resources:

apps: Deployments, ReplicaSets, StatefulSets, DaemonSets, and DeploymentsRollback.
extensions: Ingresses, NetworkPolicies, and PodSecurityPolicies.
batch: CronJobs and Jobs.
storage.k8s.io: StorageClasses and VolumeAttachments.
policy: PodDisruptionBudgets.

**Core group:**


The core group is where all core functionality exists. Such as namespaces, PODs, replication controllers, events, endpoints, nodes, bindings, Persistent volumes, persistent volume claims, configmaps, secrets, services, etc.

![Model](https://github.com/rangushiva1/k8s-files/blob/main/k8s3.png?raw=true)

The core group’s API endpoint is located at /api/v1.

![Model](https://github.com/rangushiva1/k8s-files/blob/main/k8s4.png?raw=true)

core REST path
/api/v1
apiVersion field in the manifest file:

The core group is not specified as part of the apiVersion field.

![Model](https://github.com/rangushiva1/k8s-files/blob/main/k8s5.png?raw=true)

Core apiVersion
apiVersion: v1
