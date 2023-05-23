<!--
.slide: data-background-image="https://external-preview.redd.it/u_-suSzOk6vEL1ycsRTYXbbMmW-UtHwyLuhCdmgjEpw.jpg?auto=webp&s=1d34292ebbad99d5152ceaeed8041271904c9fe6" data-background-opacity="0.2"
-->

## Case Studies 1

![](https://home.cern/sites/default/files/logo/cern-logo.png)
### OpenStack at CERN

---

### Introduction to CERN

- CERN is a leading global research organisation focused on high-energy physics.
- The World Wide Web was invented at CERN in 1989.
- It operates the Large Hadron Collider (LHC), the world's largest particle accelerator.
- CERN's collaboration with scientists worldwide and generated a massive volume of data its experiments.

---

### Challenges Faced by CERN

- [CERN generates petabytes of data](https://home.cern/resources/faqs/facts-and-figures-about-lhc) from particle collisions, requiring immense computing power for analysis.
- Traditional data center environments couldn't meet the scalability and flexibility demands of CERN's research.
- Scientific research at CERN is dynamic, with evolving objectives and requirements. They needed a flexible infrastructure that could provide a wide range of services.

Note:
CERN Data Centre stores more than 30 petabytes of data per year from the LHC experiments. Over 100 petabytes of data are permanently archived, on tape.

---

### OpenStack at CERN

- CERN developed a private cloud infrastructure based on OpenStack.
- The OpenStack cloud provides a flexible choice of compute, storage, and networking resources.
- OpenStack allows CERN to provide a large service catalog to its users, including virtual machines, block storage, containers, container ochestration, object storage, and databases.

---

![](https://techblog.web.cern.ch/techblog/img/post/10-years-of-openstack-part2-3.png)

<small>Source: [_CERN cloud infrastructure service catalogue- 2021_](https://techblog.web.cern.ch/techblog/post/10-years-of-openstack-at-cern-part-2/)<small>

---

![](https://techblog.web.cern.ch/techblog/img/post/10-years-of-openstack-part2-4.png)

<small>Source: [_Overview of CERN cloud infrastructure resource - 2021_](https://techblog.web.cern.ch/techblog/post/10-years-of-openstack-at-cern-part-2/)<small>


---

## More Info

- [CERN OpenStack Cloud](https://clouddocs.web.cern.ch/)
- [CERN Cloud Blog](https://techblog.web.cern.ch/techblog/)

---

<!--
.slide: data-background-image="https://www.filepicker.io/api/file/hCX99LXRRmeR7WD8D1cT" data-background-opacity="0.6"
-->

## Case Studies 2

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>


### Kubernetes at Squarespace

---

### Introduction to Squarespace

- Squarespace is a website building and hosting company.
- It provides software as a service (SaaS) for website building and hosting.
- It has over 2 million paying customers and 1,200 employees.

---

### Challenges Faced by Squarespace

- Squarespace's infrastructure was built on a monolithic architecture.
- "The infrastructure deployment process on our 5,000 VM hosts was slowing everyone down."
- "When we're deploying VMs, we have to build tooling to ensure that a service is spread across racks appropriately and can withstand failure,"

---

### Kubernetes at Squarespace

- Squarespace adopted Kubernetes to manage its infrastructure.
- Before, their VM deployment would take half an hour; now, a templated application can be generated and deployed in five minutes.
- “If a node goes down, it’s rescheduled immediately and there’s no performance impact.”

---

![](https://image.slidesharecdn.com/kubernetessquarespacesreportlandmeetupoctober2017-171024205334/75/kubernetes-squarespace-sre-portland-meetup-october-2017-3-2048.jpg)

<small>Source: [_Squarespace - Kubernetes @ Squarespace (SRE Portland Meetup October 2017)_](https://www.slideshare.net/KevinLynch26/kubernetes-squarespace-sre-portland-meetup-october-2017-81165445)<small>
---

## More Info

- [Squarespace Kubernetes Case Study](https://kubernetes.io/case-studies/squarespace/)
- [Squarespace Engineering Blog](https://engineering.squarespace.com/)
- [Kubernetes @ Squarespace](https://www.slideshare.net/KevinLynch26/kubernetes-squarespace-sre-portland-meetup-october-2017-81165445)
