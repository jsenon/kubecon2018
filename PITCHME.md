# Kubecon Europe 2018

---

## Keynotes

+++

#### Day 1

* Number of attendee: ~4000 (Berlin 2017: ~1200)
* Growing of CNCF project form 8 in Berlin to 20 in Copenhaguen
* SPIFFE or NATS now part of CNCF
* Growing of k8s communities 29 SIG 10 Working groups
* Cisco introduce Service Mesh
* Introduce High velocity
* Just run my Code (using transparent tools: Faas, Container, Istio, Prometheus Scrap)

+++

#### Day 1 (Part2)

* Monzo Feedback outage 
* Outage Post mortem: 
    * Bug in gRPC client library affecting etcd
    * Incompatibility K8S and Linkerd
* Outage Lessons learn
    * Chaos engineering
    * Be transparent; embrace community

+++

#### Day 1 (Part3)

* Prometheus 2.0
* Anouncement of gvisor and google stackdriver for k8s

+++

#### Day 2

* Some figures: 54% of most industries are using k8s
* Security is now part of kubernetes
* Application compatibility growing (Kafka operator or kubeflow as an example)

+++

#### Day 2 (Part2)

* Feedback from Financial Time, who has migrated from legagcy to k8s and nicroservices
* Rethinking networking for microservices
* Use case: CERN and K8S

+++

#### Day 3

* Introduce/Demo kubeflow v0.1 for AI, v0.2 coming soon (summer)
* Demo around pod security and root privileges
* Use cases with booking.com who's using K8S for learning model in poduction
* How you can map your environment, identify opportunities to exploit and learn patterns of change 

[Great talk I recommend](https://kccnceu18.sched.com/event/EDv7/keynote-crossing-the-river-by-feeling-the-stones-simon-wardley-researcher-leading-edge-forum)

---

## Technical Session Day 1

+++

#### Istio SIG Configuration

* Introduce better configuration, rollout, and autoscalling: Galley
* It will use internal and external CRD as many of new tools

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/30/Introduction%20to%20Istio%20Configuration%20--%20Kubecon%20EU%202018%20%20%283%29.pdf)

+++

#### Replace NGINX by Envoy @TurbineLabs

* User feedback
* HTTP/2 was not available on nginx when project has been started
* Before switch to envoy, an xDS is needed in order to have automatic discovery on envoy sidecar
* Envoy don't have GC so it's predictible
* Envoy can be deploy has a simple proxy with image `envoy-simple`

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/a6/Turbine%20Labs_Move%20to%20Envoy%20Deck_V2.pdf)

+++

#### Notary and TUF

* Usage of Webhook admission controller in order to check image launch by kubernetes container engine
* Introduce portieris that is admission control for enforcing image
* Ensure that Kubernetes pulls the signed version

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/41/kubernetes-notary-tuf.pdf)

+++

#### Envoy@Lyft

* Network team at lyft want to hide network complexity
* Lyft is 200 services, 20,000 hosts, 5 million RPS
* Move form routing static file to dynamic definition through routing tables
* Dynamic Configuratio management is handle by xDS (RDS, CDS, LDS)
* Route is manage during deployment of service 

[For further information presentation is online](https://www.slideshare.net/JoseUlisesNinoRivera/envoy-lyft-developer-productivity)

+++

#### Istio and fortio Performance

* Istio is an open platform provide uniform way to connect, manage and secure microservices
* Presentation of some results about performance on AWS, GCE, Azure 
* Performace could be mesasure through Fortio, but also jmeter

+++

#### Istio and fortio Performance (Part2)

* Metrics is available for each daily release
* User Centrics: Some lack has been identified and will be fixe or has been fixed
* Needs industry feedback (as we do) to the SIG perf

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/62/Istio_Perf_KC_CNC_EU_2018_ppt_v3.pdf)

+++

#### How to contribute

* Start with Docs
* Second step is to have look on issue and try to solve it, some issue with category could be study firstly
* When you have a mentor you can be promote to member and be part of org
* Issue triage (Bug or Feature request) could be done as member to have global overview of projet 

+++

#### How to contribute (Part2)

* Ask questions, ask shadow on slack
* Release process is around 3 months

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/3e/KubeConEU2018%20Growing%20in%20Your%20Contributor%20Role.pdf)

+++

#### Zalando K8S Deploymkent

* Use git nd branch to deploy new K8S cluster and perform e2e testing
* No pet clusters
* Always provide latest stable
* Be careful volume in another region

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/18/2018-05-02%20Continuously%20Deliver%20your%20Kubernetes%20Infrastructure%20-%20KubeCon%202018%20Copenhagen.pdf)

---

## Technical Session Day 2

+++

#### Network CNI

* Present how to use and write Network driver (CNI)
* CNI don't manage multiple network right now
* Attaching multiple network interface to a POD is currently in design

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/64/Kubernetes-and-the-CNI-Kubecon-218.pdf)

+++


#### GPU k8s

* Roadmap: Aplha GPU <1.7, Device plugin 1.8 to 1.10, GPU enhancements >2018
* Create a daemonset on each node to be aware of GPU and have driver
* Warn about number of instance GPU on aws
* 5 to 15 minute to spawn a new instance : Unfortunately you need to pre provision a node 

+++

#### GPU k8s (Part2)

* GPU Metrics exists
* To be followed because will be used by AI and machine learning

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/de/Kubecon%20Talk.pdf)

+++

#### Envoy Internal Deep dive

* Explain how envoy is composed and architectured internally
* Write with C++
* Main thread deals with xDS, admin, process ... 
* Worker thread(s) manage listeners and connections
* Designed to be 100% non blocking and to scale massive parallelism
* Design for containerized world

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/75/Kubecon_EU_18_Draft.pdf)

+++

#### Event driven with Brigade

* Brigade is a lightweight opensource event-driven tool 
* Accept Javscript expression of pipelinbe and convert it to Kubernetes runtime objects (Jobs)

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/fe/KubeCon%202018%20Brian%20Redmond.pdf)

+++

#### AWS CNI

* Present new opensource CNI used on AWS EKS
* Main target is to reduce number of overlay as google do
* Number of POD = EC2 Flavor : Number of Eth * Number of Private address

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/6f/KC_CNC_EU_2018_CNI_AWS.pdf)

---

## Technical Session Day 3

+++

#### Istio User Journey by Weathear.com

* Weather.com Want Blue green / Circuit breaking / Retry 
* Visibility
* Use istio for service inside and outside cluster

[For further information presentation is online](https://schd.ws/hosted_files/kccnceu18/0e/Istio%20-%20The%20Weather%20Company%27s%20Journey.pdf)

+++

#### Kubelet to Istio: Security topics

* Talking about multiple security topics around k8s
* Recommandation: Use cert with istio-ca who rotate certificate for your workload
* Activate mTLS wich is available with Istio
* SPIFFE to identify application workload, is automatically added with Istio if mTLS is enable
* Conclusion: encrypt everywhere

[For further information presentation is online](https://drive.google.com/file/d/16gHu0lQroIW1c9xAAU_u4V8MJa7AD4XT/view)

+++

#### Marchine Learning - Kubeflow

* Heptio Sonoboy is a tools from heptio for k8s configuraiton check and compliance
* Before deploy kubeflow run sonoboy to be sure that all your cluster have same configuration
* Use Heptio Ark to back up and restore your Kubernetes cluster resources and persistent volumes




