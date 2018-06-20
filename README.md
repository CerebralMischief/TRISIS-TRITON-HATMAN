## TRISIS / TRITON / HatMan Malware Repository

### Description

This repository contains original samples and decompiled sources of malware attacking commonly used in Industrial Control Systems (ICS) *Triconex* Safety Instrumented System (SIS) controllers. For more information scroll to "*Learn More*".

Each organization describing this malware in reports used a different name (TRISIS/TRITON/HatMan). For that reason, there is no one, common name for it.

 Folder *original_samples* contains original files used by the malware that could be found in the wild:

| Name       | MD5                              | Contains        | MD5                              |
| ---------- | -------------------------------- | --------------- | -------------------------------- |
| trilog.7z  | 0b4e76e84fa4d6a9716d89107626da9b | trilog.exe      | 6c39c3f4a08d3d78f2eb973a94bd7718 |
| library.7z | 76f84d3aee53b2856575c9f55a9487e7 | library.zip     | 0face841f7b2953e7c29c064d6886523 |
| imain.7z   | d173e8016e73f0f2c17b5217a31153be | imain.bin       | 437f135ba179959a580412e564d3107f |
| all.7z     | 5472e9e6d7fcb34123286878e1fecf85 | All files above | -                                |

All archives are secured with password: *infected*

Folder *decompiled_code* contains decompiled python files, originating from *trilog.exe* file and *library.zip* archive described above:

| Origin      | Result                  | Method                |
| ----------- | ----------------------- | --------------------- |
| trilog.exe  | script_test.py          | unpy2exe + uncompyle6 |
| library.zip | Files in folder library | uncompyle6            |

Folder *yara_rules* contains yara rules (that I am aware of) detecting this malware:

| File          | Author                    |
| ------------- | ------------------------- |
| mandiant.yara | @itsreallynick (Mandiant) |
| ics-cert.yara | DHS/NCCIC/ICS-CERT        |

Folder *symbolic_execution* contains script for running imain.bin with ANGR symbolic execution engine – credits to [@bl4ckic3](https://twitter.com/bl4ckic3)

### Why Publishing? Isn't it dangerous?

Some people in the community were raising the issue that publishing the samples and decompiled sources might be dangerous. I agreed until these were not public. I have found the included files in at least two publicly available sources, that means anyone can download it if know where to search. What is more, I believe that organizations/people who could be able to reuse it and have the capability to deploy it in a real attack have already accessed it long time ago. This repository makes it more accessible for community and academia who might work on improving defense solutions and saves some time on looking for decompilers.

### Learn more
#### Technical Analysis:
* [Report by Dragos](https://dragos.com/blog/trisis/TRISIS-01.pdf)
* [Report by Mandiant (FireEye)](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)
* [Report by ICS-CERT (NCCIC)](https://ics-cert.us-cert.gov/sites/default/files/documents/MAR-17-352-01%20HatMan%E2%80%94Safety%20System%20Targeted%20Malware_S508C.pdf)
* [Report by ICS-CERT (NCCIC) Update A](https://ics-cert.us-cert.gov/sites/default/files/documents/MAR-17-352-01%20HatMan%20-%20Safety%20System%20Targeted%20Malware%20%28Update%20A%29_S508C.pdf)
* [Webinar by Dragos (video)](https://vimeo.com/248057640)
* [Analysis by Craftsman Safety Lab (in Chinese)](http://icsmaster.com/security/Triton_src_analysis.html)
* [Analysis by Midnight Blue](https://www.midnightbluelabs.com/blog/2018/1/16/analyzing-the-triton-industrial-malware)
* [Schneider Electric analysis on S4x18 (video)](https://www.youtube.com/watch?v=f09E75bWvkk)
* [Mandiant analysis on S4x18 (video)](https://www.youtube.com/watch?v=nAU8X03Eg9c)
* [Dragos analysis on S4x18 (video)](https://www.youtube.com/watch?v=m51JrxdvEV8)
* [Accenture analysis](https://www.accenture.com/t20180123T095554Z__w__/us-en/_acnmedia/PDF-46/Accenture-Security-Triton-Trisis-Threat-Analysis.pdf)
* [Description of a group behind - "Xenotime"](https://dragos.com/blog/20180524Xenotime.html) 
* [Similarities between Triton code and TriStation dlls](https://www.fireeye.com/blog/threat-research/2018/06/totally-tubular-treatise-on-triton-and-tristation.html)

#### News Publications:
* [Assumption that Aramco was a target](http://foreignpolicy.com/2017/12/21/cyber-attack-targets-safety-system-at-saudi-aramco/)
* [Description of analysis and information sharing process](https://www.cyberscoop.com/trisis-ics-malware-saudi-arabia/)
* [How it was leaked to the Internet](https://www.cyberscoop.com/trisis-virus-total-schneider-electric/)

#### Others:
* [Academic POC attack on Tricon (published a year ahead)](http://ieeexplore.ieee.org/document/7920614/)
* [Defense recommendations](http://titaniumaics.blogspot.com.es/2018/)
* [Files compilation times](https://twitter.com/ItsReallyNick/status/944399647442956288)

**Any updates to the repository are warmly welcome**

Currently looking for the missing *inject.bin (0544d425c7555dc4e9d76b571f31f500)* file

Contact: 

* [@dudekmar](https://twitter.com/dudekmar)
* contact(at)marcindudek.com
