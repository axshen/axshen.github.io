---
title: Earth observation
layout: post
categories:
- projects
description: Fundamentals of satellite imagery and spatiotemporal data modelling.
---

It's been a busy couple of days with CSIRO's [MARS 2021 conference](https://research.csiro.au/mlai-fsp/conference/mars-2021/) and a satellite imagery workshop by [Pawsey](https://pawsey.org.au/). Without intending to these two events provided an interesting overview of the same topic - processing of spatiotemporal satellite data and remove sensing. The workshop discusses the basics (e.g. data structures and analysis of this data - see [this paper of the prediction of wheat yield][1]), while one particular MARS 2021 talk of interest explored hybrid modelling of physical dynamics with satellite data to improve inferences. Hybrid modelling seems like an advanced use-case of satellite and spatiotemporal data.

While the last couple of days have provided an introduction to some ideas in remote sensing/earth observation, I'm interested to explore all of this further in the form of some personal projects in this space.

### Basics of satellite imagery

#### Data representation

There is little difference between satellite imagery and other image datasets. In raster form the data is represented as a matrix of pixel values (height, width, channels). The number of channels/bands is likely to differ, because in addition to RGB you can have information from other wavelengths of light (e.g. near IR, far IR, radio etc) or indexes constructed from other channels (e.g. [NDVI](http://www.bom.gov.au/climate/austmaps/about-ndvi-maps.shtml)). Width and height properties are effectively the same. Satellite imagery also uses vector representations (i.e. points, lines and polygons) which capture regions of the image for maps. In addition, image headers contain additional metadata that differs from regular images.

#### Resolution

One interesting difference is how the resolution of the image is defined. There are four different types of resolution for satellite image data:

* temporal resolution: the time between different images
* spatial resolution: the size of the physical space captured in a pixel
* spectral resolution: the channel/band properties of the image (number of bands, wavelength centre, wavelength width)
* radiometric resolution: the amount of data available in the pixel (e.g. 8 bit vs 16 bits)

I guess regular image data has the same resolution but we often don't talk about spectral or radiometric resolution as they are typically represented by RGB values ranging from 0-256. Aside from this small difference 

### Hybrid modelling

The term "hybrid" this case refers to the combination of physical data with generate models of the dynamics to perform inference. The deep learning model architectures used for these generative models make use of convolutional layers for reducing map/image data, residual layers for allowing combination of the latent information with other temporal data (e.g. weather information), and upscaling to re-produce the dynamics. 

[1]: https://pdf.sciencedirectassets.com/271723/1-s2.0-S0168192319X00064/1-s2.0-S0168192319301224/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjEFEaCXVzLWVhc3QtMSJIMEYCIQCvJBe3bwj5Eu0Zago8h9cjtGBX0TV3QnYy%2Fq4%2FTt87jgIhAPQVB7TLZaU9OjhxihpchMLfNKsCWWPQCveV8jq04MBNKoMECPr%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEQBBoMMDU5MDAzNTQ2ODY1IgxH47GwZ6E3dN%2BrbmQq1wNzIe8q%2BK17VwDIYy0MdhhBJmdu%2F265iGL74P6SMe1zrsLnLb35MFQSs6jKFuczX8EQ%2B02RaTDXcjRkli3M9wWL5ZOOpsIac6AGMt0RptJvijNZSMBTm7QqQyLTgvoxyPbDAhRMfSYp5JY8SZc0D53tzDNxflJjW8aSDUBZU7lMx5xUERFnGn%2FbrPOmwU93smNgW215k8kVslsuxyv2jTRBDYU4nPCbLJICpHiQe5bO%2FiBE0EDcYz1yOFYr53SLn646tMxBoK7SFOBT2y9M2JPsJYcLzHAFVIxZaK%2F52Yjhubim%2FsfdFoDE%2F8pyESH7ywA6eHPA7dLzXlOJSgEjjb%2BRrBndAWGr0mm1X14Dug5KbJP10sRk8APSVmjkgG7yx3jZyUrafU6W1MjnU9GkzfUV2szDYvZUIqNDO2Cej4VkvOypZIqs5RvXdLUHYxpNWq6hSYhdbhZjBRgBkAsSxNFLBgETZskCRjJuQn%2FLE53wKp66wtTvRV3Ylj1vjAMJ8q2m13eeJkpDyMw7XsnDTYFlAjBY6jNqBVJkKDxyIBSIauPUhiUP%2F7k2houYIpITu3%2FbxXbK60ukxtXvPLFTkfkzkuyXOhDvCnbNXax8HVA718YZY%2BTrhrMwjPLlhQY6pAF6wx6%2FJY6aS4prk8z4789Dggyj9pJ0ntGYJGAazewi9jbs0rzllAwWrBuCJ%2Bd8GLPlP%2FkhiSTlq4fa43KFfiggC5%2B3s5MetpdQhkglDnf5cbWG9AvqS%2BZn26ye5SwKIZ8kPBsNijAYktsLYNOIGZp0qz5j8yjpbsjdMaSQwEX1mhJGxeij9JWWsX2tF1Sles%2Bn8eYWSzLHoivAXsELl32WyIvxnQ%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20210604T014222Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTY37C2TRHO%2F20210604%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=1013fffe06a41c567b8f87f73ac1b2786addc1a462394b434a14766f98f21966&hash=88e7426e40414e6c3485c7bc3a1557842b1fefa4178d6275d84a31e90ff19436&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0168192319301224&tid=spdf-b0c3eaf8-f77a-40b3-bba0-5e1ee745e968&sid=17d05b309876824b7d69da725c6ef2f95063gxrqa&type=client