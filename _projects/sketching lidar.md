---
layout: page
title: sketching single-photon data
description: 
img: assets/img/sheehan2021sketching.gif
importance: 3
category: work
---

Single-photon lidar is an emerging ranging technique that can obtain 3D information at kilometre distance with centimetre precision, and has important applications in self-driving cars, forest canopy monitoring, non-line-of-sight imaging and more. This modality consists of contracting a histogram of time-of-arrival of individual photons per pixel. For each object in the line-of-sight of the device there is a peak in the histogram. These peaks are found by a 3D reconstruction algorithm that takes into account the Poisson statistics of the photon-count data, while promoting spatial smoothness in the reconstructed point clouds. In a previous post, I presented an algorithm that can find multiple peaks per pixel in a matter of milliseconds even in challenging very long range scenarios with high background noise. As the algorithm needs to process the histogram data, the <strong>reconstruction time</strong> depends (linearly) on the total number of non-zero bins in the histogram:


<div><figure><img src="{{ timing_bins.png| prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" width="509" height="241"/><figcaption>Fig. 1: Execution time of a 3D reconstruction algorithm as a function the number of non-zero bins in the collected time-of-arrival histograms (from ).</figcaption></figure></div>

As single-photon lidar arrays get bigger and faster, the number of photons collected per histogram gets bigger, while there is an increased need for faster real-time frame rates. The volume of photon data that needs to be transmitted is ever-increasingly large, generating a <strong>data transfer bottleneck</strong>. Moreover, reconstruction algorithms are required to deal with ever-increasingly large and dense histograms, generating a <strong>computational bottleneck</strong>. So far, most attempts to alleviate these bottlenecks consisted in building coarser histograms. Despite reducing the amount of information to be transferred and processed, this approach sacrifices important depth resolution.


In {% cite sheehan2021sketching %}, we propose a sketching method to massively <strong>compress the histograms without any significant loss of information</strong>, removing the data and computational bottlenecks. The technique builds on recent advances in <a href="https://arxiv.org/abs/1706.07180">compressive learning</a>, a theory for compressing distributions. The compressed data consists of a series of $$K$$ statistics 



$$\Phi_k(t) = [\cos(w_k t),  \sin(w_kt)]^{T} \quad \text{for} \quad k=1, \dots, K$$


where $$t$$ denotes the time of arrival. The statistics can be <strong>computed on-the-fly</strong>, i.e. updated with each photon arrival, hence completely by-passing the need to construct a histogram. Below you can see the large difference between reducing the data by coarse binning the histogram and our proposed method:


<div><figure><img src="{{ sheehan2021sketching2.gif | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}"></figure></div>

### Related papers
<div class="publications">
{% bibliography --cited -f papers %}
</div>