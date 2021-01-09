# Softare Repositories

There are many software repositories for the Vector, cloud servers, and
interoperating with Vector.  This pages lists a few.  The diagram below summarises
some of the main ones:

![](Vector Foundation Repositories.png#zoom)
_Figure: Synopsis of the main repositories for Vector's software, the cloud software, and interacting with him via an SDK_

## Programmers API, Guides and Examples
The main PC/Mobile SDK (HTTPS API) include:

- Python Communication SDK: [Vector - Python SDK](https://github.com/ikkez/vector-python-sdk)
- The [original python SDK](https://github.com/anki/vector-python-sdk)
  This is a python framework to access Vector remotely.  _OUTDATED_
- C# Communication SDK: [Anki.Vector.SDK](https://github.com/codaris/Anki.Vector.SDK)
  This is a .NET framework to access Vector remotely from a Windows, Linux or
  Mac OS computer.

- C# [Anki.Vector.WebVizSDK](https://github.com/randym32/Anki.Vector.WebVizSDK)
  to access the WebViz related information in developer builds.
- C# [Anki.Resources.SDK](https://github.com/randym32/Anki.Resources.SDK) to
  access, analyze local (that is, on your computer) copies of the Vectors'
  application resources/assets

- See the SDKs above for examples how to use each



## Other interface-related repositories

- The [https://github.com/digital-dream-labs/api](https://github.com/digital-dream-labs/api)
  repository defines the cloud and SDK protobufs used to interfaces with them. 
  The information in this repository is used by both the robot and the cloud.

- The [OPUS audio code](https://github.com/digital-dream-labs/opus-go)
  is used to encode and transport the spoken audio to the cloud (Chipper)
  and then decode it on the cloud server.

## The software running on Vector 

- [Vector-cloud](https://github.com/digital-dream-labs/vector-cloud)
  This is the code for the vic-cloud and vic-gateway applications that run on
  Vector.

- [Chipper](https://github.com/digital-dream-labs/chipper)
  This is the repository for go-based server receiving data from Vector.

- The [api-clients](https://github.com/digital-dream-labs/api-clients)
  reposistory holds the interfaces and tools that connect Chipper to others
  modules on the cloud server.

- The [hugh](https://github.com/digital-dream-labs/hugh) repository holds
  a framework that acts as a template gRPC server and utilities.


## Bluetooth LE tools

Bluetooth LE implementations.  There isnt an SDK for the Bluetooth LE protocol,
but there are a few implementations that you might wish to look at/reuse:

- [OS-X Objective-C](https://github.com/GooeyChickenman/victor/tree/master/tools/vector-BLE)
- [linux & C](https://github.com/sandsmark/victor/tree/master/tools/vector-BLE)
- [Chrome & Javascript](https://github.com/kercre123/victor-web-setup) and
  [here](https://github.com/digital-dream-labs/vector-web-setup)


Bluetooth LE implementations.  There isnt an SDK for the Bluetooth LE protocol,
but there are a few implementations that you might wish to look at/reuse:

- [OS-X Objective-C](https://github.com/GooeyChickenman/victor/tree/master/tools/vector-BLE)
- [linux & C](https://github.com/sandsmark/victor/tree/master/tools/vector-BLE)
- [Chrome & Javascript](https://github.com/kercre123/victor-web-setup) and
  [here](https://github.com/digital-dream-labs/vector-web-setup)

