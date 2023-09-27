---
layout: article
title: Paper Library
nav_key: Papers
aside:
  toc: true
# sidebar:
#   nav: Papers
key: page-library
---



## ML papers

### Generating electron flows (arrow pushing)

- [Non-Autoregressive Electron Redistribution Modeling for Reaction Prediction (NERF)](https://arxiv.org/abs/2106.07801) [GitHub Repo](https://github.com/20171130/NERF)  
Hangrui Bi, Hengyi Wang, Chence Shi, Connor Coley, Jian Tang, and Hongyu Guo  
*in Proceedings of the 38th International Conference on Machine Learning*, PMLR 139, **2021**  
&ensp; Models reactions as electron flow. Predicts flow non-autoregressively. Trained on USPTO-MIT; SOTA results. Graph rep from SMILES input.  

- [Molecule Edit Graph Attention Network (MEGAN): Modeling Chemical Reactions as Sequences of Graph Edits](https://doi.org/10.1021/acs.jcim.1c00537) [GitHub Repo](https://github.com/molecule-one/megan)  
Mikołaj Sacha, Mikołaj Błaż, Piotr Byrski, Paweł Dąbrowski-Tumański, Mikołaj Chromiński, Rafał Loska, Paweł Włodarczyk-Pruszyński, and Stanisław Jastrzębski  
*J. Chem. Inf. Model.* **2021**, *61*, (7), 3273–3284.  
&ensp; Models chemical reations as series of graph edits, most similar to existing environment. Learns to predict sequences autoregressively.  

- [A Generative Model For Electron Paths (ELECTRO)](https://openreview.net/forum?id=r1x4BnCqKX) [GitHub Repo](https://github.com/john-bradshaw/electro)  
John Bradshaw, Matt J. Kusner, Brooks Paige, Marwin H. S. Segler, and José Miguel Hernández-Lobato  
*in ICLR* **2019**  
&ensp; Learns to generates probabilbty distribution of electron paths. Trained on USPTO (w/ and w/o reaction condition data), 2e- chemistry only. Graph rep from SMILES input.  

The Baldi papers don't have available source code but programs are available on [ChemDB](https://cdb.ics.uci.edu/).  
- [Deep learning for chemical reaction prediction](https://doi.org/10.1039/C7ME00107J)  
David Fooshee, Aaron Mood, Eugene Gutman, Mohammadamin Tavakoli, Gregor Urban, Frances Liu, Nancy Huynh, David Van Vrankenb, and Pierre Baldi  
*Mol. Syst. Des. Eng.* **2018**, *3*, 442-452  

- [A Machine Learning Approach to Predict Chemical Reactions](https://papers.nips.cc/paper_files/paper/2011/hash/b337e84de8752b27eda3a12363109e80-Abstract.html)  
Matthew Kayala and Pierre Baldi  
*in NeurIPS* **2011**  

- [Learning to Predict Chemical Reactions](https://doi.org/10.1021/ci200207y)  
Matthew A. Kayala, Chloé-Agathe Azencott, Jonathan H. Chen, and Pierre Baldi  
*J. Chem. Inf. Model.* **2011**, *51*, 9, 2209–2222
&ensp; Maps e- sources and sinks, combinatorially generates probability distribution of electron flows. Described classifiers are used to filter source-sink pairs before eval. Trained on in-house data.   


### Reaction network graphs

- [Efficient prediction of reaction paths through molecular graph and reaction network analysis](https://doi.org/10.1039/C7SC03628K)  
Yeonjoon Kim, Jin Woo Kim, Zeehyo Kim, and Woo Youn Kim  
*Chem. Sci.* **2018**, *9*, 825-835  
&ensp; Search method for reaction intermediate networks. Uses DFT energies as heuristic.


## Chemistry papers



## My papers

- [Sodiated Oppolzer enolates: solution structures, mechanism of alkylation, and origin of stereoselectivity.](https://doi.org/10.1039/D3QO01021J) **NM Lui** & DB Collum, *Organic Chemistry Frontiers* **2023**, *10* (19), 4750.  
- [MoFlowGAN: Combining adversarial and likelihood learning for targeted molecular generation.](https://doi.org/10.26434/chemrxiv-2023-kwwv3) **NM Lui**, MD Li, & M Ford, *ChemRxiv Preprint* **2023**. [Code](https://github.com/thisisntnathan/MoFlowGAN)  
- [Lithiated Oppolzer Enolates: Solution Structures, Mechanism of Alkylation, and the Origin of Stereoselectivity.](https://doi.org/10.1021/jacs.2c09341) **NM Lui**, SN MacMillan & DB Collum, *Journal of the American Chemical Society* **2022**, *144* (51), 23379.  
- [Sodium Isopropyl(trimethylsilyl)amide (NaPTA): A Stable and Highly Soluble Lithium Diisopropylamide Mimic.](https://pubs.acs.org/doi/10.1021/acs.joc.2c01745) Y Ma, **NM Lui**, I Keresztes, RA Woltornist & DB Collum, *The Journal of Organic Chemistry* **2022**, *87* (21), 14223.  
- [Spectrochemistry of firefly bioluminescence.](https://doi.org/10.1021/acs.chemrev.1c01047) MB Al-Handawi, S Polavaram, A Kurlevskaya, P Commins, S Schramm, C Carrasco-López, **NM Lui**, KM Solntsev, SP Laptenok, I Navizet & P Naumov, *Chemical Reviews* **2022**, *122* (16), 13207.  
- [The elusive relationship between structure and colour emission in beetle luciferases.](https://www.nature.com/articles/s41570-020-00238-1) C Carrasco-Lopez, **NM Lui**, S Schramm & P Naumov, *Nature Reviews Chemistry* **2021**, *5* (1), 4.  
- [Thermochemiluminescent peroxide crystals.](https://www.nature.com/articles/s41467-019-08816-8) S Schramm, DP Karothu, **NM Lui**, P Commins, E Ahmed, L Catalano, L Li, J Weston, T Moriwaki, KM Solntsev & P Naumov, *Nature Communications* **2019**, *10* (1), 997.  
- [pH-Dependent fluorescence from firefly oxyluciferin in agarose thin films.](https://doi.org/10.1039/C8NJ05469J) **NM Lui**, S Schramm & P Naumov, *New Journal of Chemistry* **2019**, *43* (3), 1122.  
- [Beetle luciferases with naturally red-and blue-shifted emission.](https://www.life-science-alliance.org/content/1/4/e201800072) C Carrasco-López, JC Ferreira, NM Lui, S Schramm, R Berraud-Pache, I Navizet, S Panjikar, P Naumov, WM Rabeh, *Life Science Alliance* **2018**, *1* (4), e201800072.  