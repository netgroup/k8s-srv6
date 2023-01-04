 
<!--- the previous line with a space is needed for github pages
      the title is not needed here, as it is taken from the project description in Github 
--->

In this project, we extend Kubernetes to make use of SRv6. The integration of SRv6 in Kubernetes 
can be very beneficial when Kubernetes is used in large scale and/or distributed multi-datacenter scenarios.

We have focused on the [Calico CNI](https://www.tigera.io/project-calico/) plugin, one of the most used networking plugin of Kubernetes.
Calico supports different data planes, we have considered the [Calico-VPP](https://projectcalico.docs.tigera.io/reference/vpp/)
data plane because VPP natively provides support for SRv6 operations with very high performance.

We have developed and released a new overlay type in Calico-VPP, called SRv6 overlay.
The SRv6 overlay can be used instead of the IP-in-IP overlay. The SRv6 overlay supports:

- Encapsulation of both IPv4 and IPv6 pods networking
- Traffic Engineering of the overlay tunnels

We have deployed the proposed SRv6 overlay in two replicable virtual testbeds, which we refer to as _basic testbed_ and _full testbed_.
The _basic testbed_ only demonstrates SRv6 tunneling equivalent to IP-in-IP tunneling. The _full testbed_ demonstrates Traffic Engineering 
capabilities. 

In the _full testbed_ we consider two solutions to distribute the SRv6 Traffic Engineering policies:

- use BGP, for which we have developed a new component called SRv6 Policy Injector (SRv6 PI)
- use Kubernetes control plane 

### Walkthrough

We have described the steps to replicate the testbeds and execute the experiments in this [walkthrough document](https://tiny.one/srv6-calico-vpp). We report its table of content:

- _Basic Testbed:_ SRv6 basic scenario (no Traffic Engineering)	
   - Environment Setup
   - Configure and install Calico VPP
   - Test SRv6 connectivity between pods
- _Full Testbed:_ SRv6 overlay with Traffic Engineering (SRv6-TE)
   - Environment Setup	
   - SRv6-TE overlay with BGP
       - Configure and deploy
       - Test SRv6 connectivity between pods
       - Test SRv6-TE edit policies	
   - SRv6-TE overlay with Kubernetes control plane
       - Configure and deploy
       - Test SRv6 connectivity between pods
       - Test SRv6-TE edit policies

### Scientific papers

- F. Lombardo, S. Salsano, A. Abdelsalam, C. Filsfils, <br>
"[Extending Kubernetes Networking to make use of Segment Routing over IPv6 (SRv6)](https://arxiv.org/pdf/2301.01178)", <br>
Submitted paper, January 2023

### Source code

- The SRv6 overlay code for Calico has been merged in the mainstream Calico-VPP code repository, we refer to [our fork]()
- SRv6 Policy Injector (SRv6 PI) is available [here](https://github.com/zvfvrv/SRv6-PI)
- The repository with the walkthrough scripts is available [here]()

<!--- example of figure
      always put the link to the img source (e.g. gslide):
      https://docs.google.com/presentation/d/1rV0ViQYk9lYUnJH16zvf5qBDUK4yTWAeHoryo6Fe0jo/edit#slide=id.g7f4100c2bd_6_0 
      export the slide as .png, and upload in docs/images with the same name

![example.png](<./images/example.png>)

--->

