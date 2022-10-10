 
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

We have developed a new component called SRv6 Policy Injector (SRv6 PI).

### Scientific papers

- F. Lombardo, S. Salsano, A. Abdelsalam, C. Filsfils, "[Extending Kubernetes Networking to make use of Segment Routing over IPv6 (SRv6)]()", Submitted paper, October 2022

### Source code

- The SRv6 overlay code has been merged in the mainstream Calico-VPP
- SRv6 Policy Injector (SRv6 PI) is available [here](https://github.com/zvfvrv/SRv6-PI)

<!--- example of figure
      always put the link to the img source (e.g. gslide):
      https://docs.google.com/presentation/d/1rV0ViQYk9lYUnJH16zvf5qBDUK4yTWAeHoryo6Fe0jo/edit#slide=id.g7f4100c2bd_6_0 
      export the slide as .png, and upload in docs/images with the same name

![example.png](<./images/example.png>)

--->

