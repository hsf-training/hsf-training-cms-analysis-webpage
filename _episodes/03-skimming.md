---
title: "Step 1: Skim the initial datasets"
teaching: 5
exercises: 10
questions:
- "What happens in the skimming step?"
objectives:
- "Perform this step of the analysis by yourself"
keypoints:
- "We reduce the initial datasets by filtering suitable events and the selection of the interesting observables."
- "This step includes finding the interesting muon-tau pair in each selected event."
---
<iframe width="431" height="263" src="https://www.youtube.com/embed/KgDgn6tEhiE?list=PLKZ9c4ONm-Vk0wnDKaaovoEkOk3PVdL0V" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

In this step, the NanoAOD files containing data and simulated events are pre-processed. This step is called skimming since the event selection reduces the size of the datasets significantly. In addition, we perform a pair selection to find from the muon and tau collections the pair which is most likely to have originated from a Higgs boson.

This step is implemented in the file `skim.cxx` and is written in C++ for performance reasons. To compile and run the program, use the script `skim.sh`. Note that you may need to change the compiler in the script based on your system.

Execute the following command to run the skimming:

```bash
mkdir -p $HOME/awesome-workshop/skims
bash skim.sh root://eospublic.cern.ch//eos/root-eos/HiggsTauTauReduced/ $HOME/awesome-workshop/skims
```

In case you want to download the files first, for example if you want to run many times, execute the following two commands. The overall size of the initial samples is 6.5 GB.

```bash
mkdir -p $HOME/awesome-workshop/samples $HOME/awesome-workshop/skims
bash download.sh $HOME/awesome-workshop/samples
bash skim.sh $HOME/awesome-workshop/samples $HOME/awesome-workshop/skims
```

The results of this step are files in `$HOME/awesome-workshop/skims` with the suffix `*Skim.root`.

{% include links.md %}
