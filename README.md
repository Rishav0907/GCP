# GOOGLE CLOUD PLATFORM (GCP)

## What is Cloud Computing?

a) On Demand Self Service = Whole thing can be done by us

b) Broad Network Access   = Can be accessed over the net

c) Resource Pooling       = Provider shares the resources to the customers

d) Rapid Elasticity       = Resources are scalable

e) Measured Service       = Pay as you go

## GCP Architecture

a) Virtualized data centres gives us Infrastructure as service (IAAS) and Platform as a service(PAAS)

## Google Cloud Basics

a) In GCP we use projects to organise our workloads 

b) Google cloud Identity and Access Management is used to control who can do what 

c) Projects are the main way to organise things. 

d) Principle of least privilege is very for managing any compute infrastructure. 

e) Four ways to interact with GCP's management layer 
    i)   Web based console 

    ii)  SDK and CLI tools 

    iii) API 

    iv)  Mobile apps 

f) When we build an app in the on premises infrastructure then the security of the whole application is the responsibility of the customer 

g) When we build an app in the google cloud platform then the lower level of security is maintained by google and the higher level is the still the responsibility of the customer.

## The Google Cloud Platform Resource Hierarchy

a) All resources in GCP whether virtual machines,cloud storage buckets or big query everything are organised into projects.

b) Optionally these projects can be organised into folders

c) Folders can be placed into other folders.

d) Everything like the projects ,folders and others can be brought under an organisation node.

e) Policies are defined into organisation nodes , projects and folders.

f) Policies are inherited downwards in the hierarchy.

g)Projects can have different users and owners

h) Projects are maintained and managed separately.

i) Project Attributes
    -Project ID = globally unique,chosen by user

    -Project name=need not be unique,chosen by user

    -Project number=globally unique,chosen by GCP

j) In the hierarchy the resources in a folder inherit IAM policies

k) To use folders we need an we need an organisation folder at the top of the hierarchy.

l) Organisation node is generally having admin rights.

m) Policies implemented at the organisation level are automatically inherited by all the children.

n) Policies implemented at higher level cannot take away access granted at the lower level.

## Identity and Access Management

a) IAM lets administrators authorize who can take action on specific resources. An IAM policy has a "who" part, a "can do what" part 

b) The Who part names the user we are talking about 

c) The who part can be defined by a google account,a service account,g suite etc 

d) The can do what part is defined by a IAM role 

e) 3 Kind of roles in google IAM 

    1) Primitive role: Applied to a GCP project and it affects all resources of a project. 
    2) Predefined roles Applied already by GCP

## IAM Roles

a) In GCP one having the compute engine's instance Admin role allows one to perform certain actions:
    - listing the VM

    - Reading and changing their configurations

    - Starting and Stopping them

b) Then there are custom roles where  one person is given the least privilege of a role.

c) Custom roles can only be used at the project or organisation level and not in the folder level

## Virtual Private Cloud

a) People get started in GCP by defining their own virtual private cloud in their first GCP projectg or

by choosing the default VPC

b) We can segment our networks and use firewall rules to restrict access to instances.

c) VPC have a global scope

d) They can have subnets in any GCP zone worldwide and subnets can expand the zonr to make up a region.

e) We can also have resources in different zones on the same subnet.

f) We can increase the size of subnet by increasing the range of ip address and it does not effect already configured Vm's

## Important VPC Capabilities

a)  VPC has routing tables

b) VPC has a global distributed firewalls

c) If there are several GCP projects and the VPC need to communicate to each other, that is also possible

d) VPC peering helps to exchange traffics b/w VPC

c) Shared VPC is used for implementing IAM policies.

d) Cloud load balancing is used when our vm's autoscale them

e) Cloud load balance is totally distributed service.

f) We can use cloud load balancng in https,https and even udp traffic.

g)  Google provides the DNS i.e 8.8.8.8 available to everyone.

h)  Google provides CDN also.

## Types of Storages

Types of storage available:

a) Cloud Storage

b) Cloud SQL

c) Cloud Spanner

d) Cloud Data Store

e) Google Big data

## Google Cloud Storage:

a) Object storage means we storage means we store some data and the storage addresses it with unique key.

b) This unique is often in the form of url

c) Google cloud storage is fully scalable

d) Google cloud storage can be used for:
   
   i)  Serving Web Contents
  
  ii)  Storing data for archival
 
 iii)  Storing for disaster recovery
 
 iv) Distributing large data objects 
      to users for direct download.

e) It is not a file system because each object in storage has a url

f) Cloud storage is comprised of buckets.

g) It means we create and configure and use to hold our storage objects

h) Storage objects are immutable i.e we instead of editing them create new versions.

i) Buckets are given globally unique name, a geographic location and a storage class.

j) Privileges can be controlled by IAM, ACl ,

k) For IAM roles are inheritedfrom project to buckets to objects

l) For finer control we use ACL(Access Control List). ACL contains who can perform the action and what action.

m) It has a kind of version control also.

## Cloud Storage Interaction:

Cloud Storage classes provided by GCP:

a) Mutli Regional

b)Regional

c)Nearline

d) Coldline

i) The first two are high performance object storage

ii) The last two are backup and archival storage

iii) All the storage classes can be accessed by cloud storage API

iii) Regional Storages lets us store our data in a a specific GCP region like US central one , Europe West one etc. Its cheaper than multi regional storage but is less redundant. This storage is used to store data close to compute engines,vm or kubernetes engine.

iv) Multi Regional storage costs a bit more but is geo redundant i.e we pick a broad geographical region like the United States, the European union etc and cloud storage stores our data in atleast to geographic location separated by at least 160 km. This storage is used for storing frequently accessed data like web contents.interactive workflow,data part of gaming apps.

v) Nearline is a low cost and highly durable service for storing infrequently accessed data

vi) Coldline storage is a very low cost and highly durable service for data archiving,online backup and recovery. Availability is low

vii) Availability of mutil regional=99.95%
     Availability of regional=99.90%
     Availability of nearline=99.00%
     Availability of coldline=99.00%

viii) Costs depend on GB of data stored per month
ix) Besides the normal cost nearline also incurs a access fee per gb of data stored and Coldline incurs a higher fee for per GB of data 

x) gsutil is the cloud storage command

xi) We can import data from big tables,compute engine,cloud sql and datastore backups

## Google Cloud Big Table:

a) Cloud Bigtable is google's NOSQL big data database service.

b) Databases in Bigtables are sparsely populated tables that can scale to billion of rows and thousand of columns.

c) Cloud bigtable is ideal for storing very large amount of data with very low latency.

d) Cloud Bigtable is the native database for Apache Hadoop.

e) Bigtable is scalable,data encryption is present,IAM can be used. 

##Google Cloud SQL and Cloud Spanner:

i) Offers MySQL and PostGreSql as a fully managed service

ii) We can also run our database servers inside the a compute engine virtual machine.

iii) In case of disaster cloud sql can automatically replicate data within different zones

iv) It provides on demand and schedule backups.

v)Cloud sql include network firewalls.

vi) Accessible by other gcp services.

vii) Cloud spanner offers transactional consistency in a global scale,schemas,sql .

viii)database service can scale to higher database sizes

## Google Cloud Datastore

a) Cloud Datastore is another highly scalable NoSQL database service.

b) Used to store structure data from App engine apps.

c) It handles sharding and replication.

c) Offers transaction that affects multiple database rows and can perform SQL like queries.

## Container,Kubernetes and Kubernetes engine

a) Compute Engine is Iaas service of GCP and App engine is Paas service of GCP.

b) Kubernetes engine is like both Iaas and Paas.

c) Iaas let us share infrastructure by virtualizing a hardware. Each vm has a instance of OS of our choice and we can run application on it.

d) VM are highly configurable , so we can configure as our choice and install web servers.

e) Auto Scaling is done

f) Kubernetes makes it easy to arrange many containers on hosts, updating new versions.

## Intro to Kubernetes and GKE

a) Kubernetes provides an API  called kubectl whch allows authorized users to control its utilities.

b) Kubernetes allows to deploy containers on a set of node called clusters.

c) A cluster is a set of master components that control the system as a whole and a set of nodes that run containers.

d) A cluster can be created with the command " gcloud container cluster create k1 "

e) Kubernetes deploy a container inside a pod.

f) Any containers in the same pod will share the same resources and local network. Containers can easily communicate with other containers in the same pod as though they were on the same machine

g)Although pods are the basic unit of computation in Kubernetes, they are not typically directly launched on a cluster. Instead, pods are usually managed by one more layer of abstraction: the deployment.

## Intro to App Engine

a) Kubernetes and Compute Engine provides Infrastructure as a service.

b) App engine uses Platform as a service.

c)The app engine manages the hardware and network configurations required to run tour code.

d) App engine provide us services like nosql db,load balancing,health checks,auth.

e) Auto scaling is provides.

## App Engine Standard Environment

a) Two environments of app engine - Standard and Flexible.

b) Standard is simpler,offers simple deployment exp.

C) Standard one provides free daily usage quota.

d) In standard ,low utilization application might be able to run at no charge.

e) App engine standard environment provides runtime for java,python,php,go etc.

f) Standard environment sandboxes our application

## App Engine Flexible Environment

a) In Flexible environment , app engines allows us to specify the container in which app engine runs.

c)  Our application runs inside docker containers inside google compute engine vm.

d) We can choose the geographical region.

## App Engine Standard Environment VS Flexible Environment

                                Standard Environment            Flexible Environment
                                
  Instance Startup               Milliseconds                     Minutes
  
  SSH                            No                               Yes
  
  Write to local disk            No                               Yes
  
  Support for 3rd party          No                               Yes
  binaries                              
  
  Network Access                 Vis app engine service           Yes


## Kubernetes VS App Engine

                            Kubernetes                App engine flexible           App engine standard
                            
   Language Support          Any                        Any                           Java,Python,php,Go
   
   Service Models            Hybrid                     Paas                          Paas
   
   Primary Use case          Container based            Web and mobile app            Web and mobile app based.                workloads                  based,container workloads
                                              
