---
layout: article
title: Library
nav_key: Papers
aside:
  toc: true
# sidebar:
#   nav: Papers
key: page-library
mathjax: true
mathjax_autoNumber: false
---

# Molecular Generation

Generative models for molecules. Most typically text-based inputs (SMILES/SELFIES) or graph reps (parallel models on atom and bond matrices). Usually have some property optimization ability (latent space search/interpolation, reinformcement learning, guided genetic exploration). Most commonly these methods are autoregressive, but more recently non-autoregressive molecular generation methods have started to arise.  

## Reviews

- [Machine learning-aided generative molecular design](https://doi.org/10.1038/s42256-024-00843-5)  
Yuanqi Du, Arian R. Jamasb, Jeff Guo, Tianfan Fu, Charles Harris, Yingheng Wang, Chenru Duan, Pietro Liò, Philippe Schwaller, and Tom L. Blundell  
*Nat. Mach. Intell.* **2024**, 6, 589  

- [Deep Generative Models in *De Novo* Drug Molecule Generation](https://pubs.acs.org/doi/10.1021/acs.jcim.3c01496)  
Chao Pang, Jianbo Qiao, Xiangxiang Zeng, Quan Zou, and Leyi Wei  
*J. Chem. Inf. Model.* **2024**, 64 (7), 2174  

## Diffusion / Flow Matching Models

- [Exploring Discrete Flow Matching for 3D De Novo Molecule Generation](https://arxiv.org/abs/2411.16644) + [GitHub Repo](https://github.com/dunni3/FlowMol)  
Ian Dunn, and David R. Koes  
*NeurIPS* **2024**  
&ensp; Benchmarks discrete flow matching techniques for 3D molecular design. Paper introduces FlowMol-CTMC, a state-of-the-art model with fewer parameters than existing methods, demonstrating superior performance on small molecule generation. Other models often generate chemically valid but atypical functional groups outside the training distribution. Paper highlights gaps in structural motif prediction while advancing generative approaches for drug discovery.  

- [ShEPhERD: Diffusing shape, electrostatics, and pharmacophores for bioisosteric drug design](https://doi.org/10.48550/arXiv.2411.04130) + [GitHub Repo (model)](https://github.com/coleygroup/shepherd) + [GitHub Repo (scoring functions)](https://github.com/coleygroup/shepherd-score)  
Keir Adams, Kento Abeywardane, Jenna Fromer, and Connor W. Coley  
*ArXiv* **2024**  

- [A dual diffusion model enables 3D molecule generation and lead optimization based on target pockets](https://doi.org/10.1038/s41467-024-46569-1) + [GitHub Repo](https://github.com/Layne-Huang/PMDM/tree/main)  
Lei Huang, Tingyang Xu, Yang Yu, Peilin Zhao, Xingjian Chen, Jing Han, Zhi Xie, Hailong Li, Wenge Zhong, Ka-Chun Wong & Hengtong Zhang  
*Nat. Commun.* **2024**, *15*, 2657  

- [Mixed Continuous and Categorical Flow Matching for 3D De Novo Molecule Generation](https://arxiv.org/abs/2404.19739) + [GitHub Repo](https://github.com/dunni3/FlowMol)  
Ian Dunn and David Ryan Koes  
*ArXiv* **2024**  
&ensp; Extends the flow matching framework to categorical data by constructing flows that are constrained to exist on a continuous representation of categorical data known as the probability simplex. Finds that, in practice, a simpler approach that makes no accommodations for the categorical nature of the data yields equivalent or superior performance. Presents FlowMol, a flow matching model for 3D *de novo* generative model that achieves improved performance over prior flow matching methods.

- [GeoLDM: Geometric Latent Diffusion Models for 3D Molecule Generation](https://arxiv.org/abs/2305.01140) + [GitHub Repo](https://github.com/MinkaiXu/GeoLDM)  
Minkai Xu, Alexander Powers, Ron Dror, Stefano Ermon, and Jure Leskovec  
*ICML* **2023**  
&ensp; Stable (latent) diffusion model for 3D point clouds and 2D graphs. Capable of free and property conditioned generation (split-train-condition).  

- [Equivariant Diffusion for Molecule Generation in 3D](https://proceedings.mlr.press/v162/hoogeboom22a.html) + [GitHub Repo](https://github.com/ehoogeboom/e3_diffusion_for_molecules)  
Emiel Hoogeboom, Vı́ctor Garcia Satorras, Clément Vignac, and Max Welling  
*in Proceedings of the 39th International Conference on Machine Learning*, PMLR 162:8867-8887, **2022**  
&ensp; Non-autoregressive diffusion model (rotation invariant). Reps: $$x = (x_1 ... x_M) \in \mathbb{R}^{M \times 3}$$ (atom position matrix) with corresponding feature vectors $$h = (h_1 ... h_M) \in \mathbb{R}^{M \times num feat}$$.  


## Normalizing Flows

- [MolGrow: A Graph Normalizing Flow for Hierarchical Molecular Generation](https://arxiv.org/abs/2106.05856) (No implementation available)  
Maksim Kuznetsov and Daniil Polykovskiy  
*Proceedings of the AAAI Conference on Artificial Intelligence* **2021**, 35 (9), 8226-8234  
&ensp; Heirarchical normalizing flow for molecular graphs, autoregressive. Builds either BFS or fragment based (better). Model is composed of "plug-and-play" modules. Trained on MOSES, QM9, Zinc250k. Property-constrained optimization is based on genetic algorithm.    

- [FastFlows: Flow-Based Models for Molecular Graph Generation](https://arxiv.org/abs/2201.12419)  
Nathan C. Frey, Vijay Gadepally, and Bharath Ramsundar  
*ELLIS Machine Learning for Molecule Discovery Workshop* **2021**  
&ensp; Framework for normalizing flows from SELFIES. Uses substructure filtering to speed up training and work from small training sets. Built in MPO functionality.  
[TDS article](https://towardsdatascience.com/fastflows-flow-based-models-for-molecular-graph-generation-a8327bb9bee1)  

- [MoFlow: An Invertible Flow Model for Generating Molecular Graphs](https://arxiv.org/abs/2006.10137) + [GitHub Repo](https://github.com/calvin-zcx/moflow)  
Chengxi Zang and Fei Wang  
*in Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining* **2020**  
&ensp; Non-autoregressive normalizing Flow for molecular graphs; two-stage flow (bonds (based on GLOW network from Nvidia) > bond-conditioned flow for atoms). Similar to GraphNVP. Trained (NLL) on QM9 and ZINC250k. Developed new architecture. Excellent results.

- [GraphAF: a Flow-based Autoregressive Model for Molecular Graph Generation](https://openreview.net/forum?id=S1esMkHYPr) + [GitHub repo](https://github.com/DeepGraphLearning/GraphAF)  
Chence Shi, Minkai Xu, Zhaocheng Zhu, Weinan Zhang, Ming Zhang, and Jian Tang  
*ICLR* **2020**  
&ensp; How to explain this better than reviewer #1...
<blockquote>
"This paper proposes a generative model architecture for molecular graph generation based on autoregressive flows. The main contribution of this paper is to combine existing techniques (auto-regressive BFS-ordered generation of graphs, normalizing flows, dequantization by Gaussian noise, fine-tuning based on reinforcement learning for molecular property optimization, and validity constrained sampling). Most of these techniques are well-established either for data generation with normalizing flows or for molecular graph generation and the novelty lies in the combination of these building blocks into a framework."
</blockquote>

## GANs

- [druGAN: An Advanced Generative Adversarial Autoencoder Model for de Novo Generation of New Molecules with Desired Molecular Properties in Silico](https://doi.org/10.1021/acs.molpharmaceut.7b00346) - No official implementation available  
Artur Kadurin, Sergey Nikolenko, Kuzma Khrabrov, Alex Aliper, and Alex Zhavoronkov  
*Mol. Pharmaceutics* **2017**, *14* (9), 3098–3104  

- [The cornucopia of meaningful leads: Applying deep adversarial autoencoders for new molecule development in oncology](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5355231/) + [GitHub Repo](https://github.com/spoilt333/onco-aae)  
Artur Kadurin, Alexander Aliper, Andrey Kazennov, Polina Mamoshina, Quentin Vanhaelen, Kuzma Khrabrov, and Alex Zhavoronkov  
*Oncotarget.* **2017**, *8*, 10883-10890  

- [MolGAN: An implicit generative model for small molecular graphs](https://arxiv.org/abs/1805.11973) + [GitHub Repo](https://github.com/nicola-decao/MolGAN)  
Nicola De Cao and Thomas Kipf  
*ICML 2018 Workshop on Theoretical Foundations and Applications of Deep Generative Models*  
&ensp; GAN for molecular graphs (tandem atom identity and bond matrices). Trained as W-GAN on QM9 with basic "RL" input. Implemented with R-GCNs.  

## Other

- [TamGen: drug design with target-aware molecule generation through a chemical language model](https://doi.org/10.1038/s41467-024-53632-4) + [GitHub Repo](https://github.com/SigmaGenX/TamGen)  
Kehan Wu, Yingce Xia, Pan Deng, Renhe Liu, Yuan Zhang, Han Guo, Yumeng Cui, Qizhi Pei, Lijun Wu, Shufang Xie, Si Chen, Xi Lu, Song Hu, Jinzhi Wu, Chi-Kin Chan, Shawn Chen, Liangliang Zhou, Nenghai Yu, Enhong Chen, Haiguang Liu, Jinjiang Guo, Tao Qin & Tie-Yan Liu  
*Nat. Commun.* **2024**, *15*, 9360

- [TurboHopp: Accelerated Molecule Scaffold Hopping with Consistency Models](https://doi.org/10.48550/arXiv.2410.20660)  
Kiwoong Yoo, Owen Oertell, Junhyun Lee, Sanghoon Lee & Jaewoo Kang  
*NeurIPS* **2024**  

- [DrugSynthMC: An Atom-Based Generation of Drug-like Molecules with Monte Carlo Search](https://pubs.acs.org/doi/10.1021/acs.jcim.4c01451)  
Milo Roucairol, Alexios Georgiou, Tristan Cazenave, Filippo Prischi & Olivier E. Pardo  
*J. Chem. Inf. Model.* **2024**, *64*, 18, 7097  

- [Enabling target-aware molecule generation to follow multi objectives with Pareto MCTS](https://www.nature.com/articles/s42003-024-06746-w?fromPaywallRec=false) + [GitHub Repo](https://github.com/CNDOTA/ParetoDrug)  
Yaodong Yang, Guangyong Chen, Jinpeng Li, Junyou Li, Odin Zhang, Xujun Zhang, Lanqing Li, Jianye Hao, Ercheng Wang & Pheng-Ann Heng  
*Commun. Biol.* **2024**, *7*, 1074  

- [Llamol: a dynamic multi-conditional generative transformer for de novo molecular design](https://doi.org/10.1186/s13321-024-00863-8)  
Niklas Dobberstein, Astrid Maass & Jan Hamaekers  
*J. of Cheminf.*, **2024**, 16, 73  
&ensp; Transformer based on Llama2, tweaked for molgen. Not the most impressive paper, but some interesting tidbits scatted throughout (e.g., SCL, etc...)  

- [REINVENT4: Modern AI–driven generative molecule design](https://doi.org/10.1186/s13321-024-00812-5) + [GitHub Repo](https://github.com/MolecularAI/REINVENT4)  
Hannes H. Loeffler, Jiazhen He, Alessandro Tibo, Jon Paul Janet, Alexey Voronov, Lewis H. Mervin & Ola Engkvist  
*J. of Cheminf.*, **2024**, 16, 20  
&ensp; AstraZeneca's molecular design tool for *de novo* design, scaffold hopping, R-group replacement, linker design and molecule optimization.  

- [Masked graph modeling for molecule generation](hhttps://doi.org/10.1038/s41467-021-23415-2) + [GitHub Repo](https://github.com/nyu-dl/dl4chem-mgm)  
Omar Mahmood, Elman Mansimov, Richard Bonneau, and Kyunghyun Cho  
*Nat. Commun.* **2021**, *12*, 3156  
&ensp; MPNN for moleular graphs. Generation by iterative sampling of subsets of graphs components, furuter generation steps are conditionalized on the rest of the graph. Trained on QM9 and ChEMBL. Paper provides analysis of GuacaMol benchmark metrics particularly their independence. Conclusions:  
1. Validity, KL-divergence and Fréchet Distance scores correlate highly with each other  
2. These three metrics correlate negatively with the novelty score  
3. Uniqueness does not correlate strongly with any other metric  


# Reaction Informatics

These models predict mechanisms for chemical reactions, ideally similar to how we teach 2nd years to push arrows. There are reltatively few of expamples of this task but they fall into 3 major categories electron flows, graph edits, reaction netowrks. At inference these models are used for forward synthesis prediction, potntially for prediction of chemo/regio-selectivity. Largely trained on pattern recognition from atom-mapped inputs (USPTO) though there are exceptions (e.g., Baldi papers below).  

## Electron Flow Prediction

- [Non-Autoregressive Electron Redistribution Modeling for Reaction Prediction (NERF)](https://arxiv.org/abs/2106.07801) + [GitHub Repo](https://github.com/20171130/NERF)  
Hangrui Bi, Hengyi Wang, Chence Shi, Connor Coley, Jian Tang, and Hongyu Guo  
*in Proceedings of the 38th International Conference on Machine Learning*, PMLR 139, **2021**  
&ensp; Models reactions as electron flow. Predicts flow non-autoregressively. Trained on USPTO-MIT; SOTA results. Graph rep from SMILES input. Fast (27x).  

- [Data-Efficient, Chemistry-Aware Machine Learning Predictions of Diels–Alder Reaction Outcomes](https://pubs.acs.org/doi/10.1021/jacs.4c03131) + [GitHub Repo](https://github.com/angusketo/DA_DataExtraction)  
Angus Keto, Taicheng Guo, Morgan Underdue, Thijs Stuyver, Connor W. Coley, Xiangliang Zhang, Elizabeth H. Krenske, and Olaf Wiest*  
*J. Am. Chem. Soc.*, **2024**, *146*, 23, 16052–16061  
&ensp; NERF applied to Diels-Alder cycloadditions. Typical training set reaches 90% accuracy (in line with general predictive accuracy...). No special improvements to NERF code released.  

- [A Generative Model For Electron Paths (ELECTRO)](https://openreview.net/forum?id=r1x4BnCqKX) + [GitHub Repo](https://github.com/john-bradshaw/electro)  
John Bradshaw, Matt J. Kusner, Brooks Paige, Marwin H. S. Segler, and José Miguel Hernández-Lobato  
*ICLR* **2019**  
&ensp; Learns to generates probabilbty distribution of electron paths. Trained on USPTO (w/ and w/o reaction condition data), 2e- chemistry only. Graph rep from SMILES input.  

- [Molecule Edit Graph Attention Network (MEGAN): Modeling Chemical Reactions as Sequences of Graph Edits](https://doi.org/10.1021/acs.jcim.1c00537) + [GitHub Repo](https://github.com/molecule-one/megan)  
Mikołaj Sacha, Mikołaj Błaż, Piotr Byrski, Paweł Dąbrowski-Tumański, Mikołaj Chromiński, Rafał Loska, Paweł Włodarczyk-Pruszyński, and Stanisław Jastrzębski  
*J. Chem. Inf. Model.* **2021**, *61*, (7), 3273–3284  
&ensp; Not technically an electron flow model. Models chemical reations as series of graph edits, most similar to existing environment. Learns to predict sequences autoregressively.


### Sources and Sinks

The Baldi papers map e- sources and sinks, combinatorially generates probability distribution of electron flows. Described classifiers are used to filter source-sink pairs before eval. Trained on in-house (unavailable) data. Papers don't have available source code but ready-to-use programs are available on [ChemDB](https://cdb.ics.uci.edu/).  
- [Deep learning for chemical reaction prediction](https://doi.org/10.1039/C7ME00107J)  
David Fooshee, Aaron Mood, Eugene Gutman, Mohammadamin Tavakoli, Gregor Urban, Frances Liu, Nancy Huynh, David Van Vrankenb, and Pierre Baldi  
*Mol. Syst. Des. Eng.* **2018**, *3*, 442-452  

- [A Machine Learning Approach to Predict Chemical Reactions](https://papers.nips.cc/paper_files/paper/2011/hash/b337e84de8752b27eda3a12363109e80-Abstract.html)  
Matthew Kayala and Pierre Baldi  
*NeurIPS* **2011**  

- [Learning to Predict Chemical Reactions](https://doi.org/10.1021/ci200207y)  
Matthew A. Kayala, Chloé-Agathe Azencott, Jonathan H. Chen, and Pierre Baldi  
*J. Chem. Inf. Model.* **2011**, *51* (9), 2209–2222     

- [PMechDB: A Public Database of Elementary Polar Reaction Step](https://pubs.acs.org/doi/10.1021/acs.jcim.3c01810)  
Mohammadamin Tavakoli, Ryan J. Miller, Mirana Claire Angel, Michael A. Pfeiffer, Eugene S. Gutman, Aaron D. Mood, David Van Vranken, and Pierre Baldi  
*J. Chem. Inf. Model.* **2024**, 64, 6, 1975–1983  
&ensp; Dataset paper for the Baldi papers. 100k polar elementary steps. [PMechDB platform](https://deeprxn.ics.uci.edu/pmechdb)  


## Reaction Network Graphs

- [Discovery of novel chemical reactions by deep generative recurrent neural network](https://doi.org/10.1038/s41598-021-81889-y)  
William Bort, Igor I. Baskin, Timur Gimadiev, Artem Mukanov, Ramil Nugmanov, Pavel Sidorov, Gilles Marcou, Dragos Horvath, Olga Klimchuk, Timur Madzhidov, and Alexandre Varnek  
*Sci. Rep.* **2021**, *11*, 3178  

- [Efficient prediction of reaction paths through molecular graph and reaction network analysis](https://doi.org/10.1039/C7SC03628K)  
Yeonjoon Kim, Jin Woo Kim, Zeehyo Kim, and Woo Youn Kim  
*Chem. Sci.* **2018**, *9*, 825-835  
&ensp; Search method for reaction intermediate networks. Uses DFT energies as heuristic.  


## Other

- [Reaction rebalancing: a novel approach to curating reaction databases](https://doi.org/10.1186/s13321-024-00875-4) + [GitHub Repo](https://github.com/TieuLongPhan/SynRBL)  
Tieu-Long Phan, Klaus Weinbauer, Thomas Gärtner, Daniel Merkle, Jakob L. Andersen, Rolf Fagerberg, and Peter F. Stadler  
*J. Cheminf.* **2024**, *16*, 82  

- [Transfer learning enables the molecular transformer to predict regio- and stereoselective reactions on carbohydrates](https://doi.org/10.1038/s41467-020-18671-7) + [GitHub Repo](https://github.com/rxn4chemistry/OpenNMT-py/tree/carbohydrate_transformer)  
Giorgio Pesciullesi, Philippe Schwaller, Teodoro Laino, and Jean-Louis Reymond  
*Nat. Commun.* **2020**, *11*, 4874  
&ensp; Seq2Seq model for SMILES strings. Transfer learning allows for success on few-instance reactions. [Blog post](https://communities.springernature.com/posts/transfer-learning-enables-the-molecular-transformer-to-predict-regio-and-stereoselective-reactions-on-carbohydrates)


## Atom Mapping

- [Precise atom-to-atom mapping for organic reactions via human-in-the-loop machine learning](https://www.nature.com/articles/s41467-024-46364-y) + [GitHub Repo](https://github.com/snu-micc/LocalMapper)  
Shuan Chen, Sunggi An, Ramil Babazade, and Yousung Jung  
*Nat. Commun.* **2024**, *15*, 2250  

- [Bidirectional Graphormer for Reactivity Understanding: Neural Network Trained to Reaction Atom-to-Atom Mapping Task](https://pubs.acs.org/doi/10.1021/acs.jcim.2c00344) + [GitHub Repo](https://github.com/chython/chytorch-rxnmap)  
Ramil Nugmanov, Natalia Dyubankova, Andrey Gedich, and Joerg Kurt Wegner  
*J. Chem. Inf. Model.* **2022**, *62*, 14, 3307–3315  
&ensp; Chython RxnMapper/Graphormer Mapper that's heavily based on RXNMapper and CGR Tools. Semisupervised graph attention based model trained on USPTO and Pistachio datasets.  

- [Atom-to-atom Mapping: A Benchmarking Study of Popular Mapping Algorithms and Consensus Strategies](https://doi.org/10.1002/minf.202100138)  
Arkadii Lin, Natalia Dyubankova, Timur I. Madzhidov, Ramil I. Nugmanov, Jonas Verhoeven, Timur R. Gimadiev, Valentina A. Afonina, Zarina Ibragimova, Assima Rakhimbekova, Pavel Sidorov, Andrei Gedich, Rail Suleymanov, Ravil Mukhametgaleev, Joerg Wegner, Hugo Ceulemans, and Alexandre Varnek  
*Mol. Inf.* **2022**, *41*, 2100138  

- [Extraction of organic chemistry grammar from unsupervised learning of chemical reactions](https://www.science.org/doi/10.1126/sciadv.abe4166) + [GitHub Repo](https://github.com/rxn4chemistry/rxnmapper) + ~~[RxnMapper app](http://rxnmapper.ai/)~~ Webpage looks like it's down  
Philippe Schwaller, Benjamin Hoover, Jean-Louis Reymond, Hendrik Strobelt, and Teodoro Laino  
*Sci. Adv.* **2021**, *7* (15), eabe4166  

- [Reaction Data Curation I: Chemical Structures and Transformations Standardization](https://doi.org/10.1002/minf.202100119) + [GitHub Repo](https://github.com/Laboratoire-de-Chemoinformatique/Reaction_Data_Cleaning)  
Timur R. Gimadiev, Arkadii Lin, Valentina A. Afonina, Dinar Batyrshin, Ramil I. Nugmanov, Tagir Akhmetshin, Pavel Sidorov, Natalia Duybankova, Jonas Verhoeven, Joerg Wegner, Hugo Ceulemans, Andrey Gedich, Timur I. Madzhidov, and Alexandre Varnek  
*Mol. Inf.* **2021**, *40*, 2100119  


# Computer-Aided Retrosynthesis Planning

- [RLSynC: Offline–Online Reinforcement Learning for Synthon Completion](https://pubs.acs.org/doi/10.1021/acs.jcim.4c00554)  
Frazier N. Baker, Ziqi Chen, Daniel Adu-Ampratwum, and Xia Ning*  
*J. Chim. Inf. Model.* **2024**, *64* (17), 6723  

- [Constrained synthesis planning with disconnection-aware transformer and multi-objective search](https://doi.org/10.26434/chemrxiv-2024-c77p4)  
Annie M. Westerlund, Lakshidaa Saigiridharan, Samuel Genheden  
*ChemRxiv preprint* **2024**  
&ensp; Retrosynthesis planning with the ability to constrain bonds, i.e., built in divergent synthesis constraints leading to shorter routes.  
&ensp; AiZynthFinder with MO-MCTS and broken bonds score was used to run multistep experiments and can be found at: [https://github.com/MolecularAI/aizynthfinder](https://github.com/MolecularAI/aizynthfinder). Chemformer can be found at: [https://github.com/MolecularAI/Chemformer](https://github.com/MolecularAI/Chemformer). AiZynthTrain was used to tag disconnection-sites in the Chemformer training data and can be found at: [https://github.com/MolecularAI/aizynthtrain](https://github.com/MolecularAI/aizynthtrain). 

- [Retrosynthesis prediction using an end-to-end graph generative architecture for molecular graph editing](https://doi.org/10.1038/s41467-023-38851-5) + [GitHub Repo](https://github.com/Jamson-Zhong/Graph2Edits)  
Weihe Zhong, Ziduo Yang, and Calvin Yu-Chian Chen  
*Nat. Commun.* **2023**, *14*, 3009  


# Publication Parsing

- [OpenChemIE: An Information Extraction Toolkit for Chemistry Literature](https://doi.org/10.1021/acs.jcim.4c00572) + [Web App](https://mit.openchemie.info/)  
Vincent Fan, Yujie Qian, Alex Wang, Amber Wang, Connor W. Coley, and Regina Barzilay  
*J. Chem. Inf. Model.* **2024**, *64* (14), 5521  

- [Advancements in hand-drawn chemical structure recognition through an enhanced DECIMER architecture](https://doi.org/10.1186/s13321-024-00872-7)  
Kohulan Rajan, Henning Otto Brinkhaus, Achim Zielesny & Christoph Steinbeck  
*J. Cheminf.* **2024**, *16*, 76


# ML Driven Drug Design

- [MolE: a foundation model for molecular graphs using disentangled attention](https://www.nature.com/articles/s41467-024-53751-y) + [GitHub Repo](https://github.com/recursionpharma/mole_public)  
Oscar Méndez-Lucio, Christos A. Nicolaou & Berton Earnshaw  
*Nat. Commun.* **2024**, *15*, 9431  
&ensp; Non-commercial license  

- [MolCompass: multi-tool for the navigation in chemical space and visual validation of QSAR/QSPR models](https://doi.org/10.1186/s13321-024-00888-z) + [GitHub Repo](https://github.com/sergsb/molcomplib)  
Sergey Sosnin  
*J. Cheminf.* **2024**, *16*, 98  

- [HydraScreen: A Generalizable Structure-Based Deep Learning Approach to Drug Discovery](https://doi.org/10.1021/acs.jcim.4c00481) + [GitHub Repo](https://github.com/Ro5-ai/hydrascreen)  
Alvaro Prat, Hisham Abdel Aty, Orestis Bastas, Gintautas Kamuntavičius, Tanya Paquet, Povilas Norvaišas, Piero Gasparotto, and Roy Tal  
*J. Chem. Inf. Model.* *64* (15), 5817  

- [Exposing the Limitations of Molecular Machine Learning with Activity Cliffs](https://pubs.acs.org/doi/10.1021/acs.jcim.2c01073)  
Derek van Tilborg, Alisa Alenicheva, and Francesca Grisoni  
*J. Chem. Inf. Model.* **2022**, *62* (23), 5938  
&ensp; Overview of SAR cliffs and challenges for ML  

## Property/Activity Prediction

- [Reusability report: exploring the utility of variational graph encoders for predicting molecular toxicity in drug design](https://doi.org/10.1038/s42256-024-00923-6) + [GitHub Repo (NYAN)](https://github.com/Chokyotager/NotYetAnotherNightshade) + [GitHub Repo (Reuse)](https://github.com/LuJiangTHU/NYAN_reuse) + [GitHub Repo (Acute Tox MTL)](https://github.com/LuJiangTHU/Acute_Toxicity_NYAN)  
Ruijiang Li, Jiang Lu, Ziyi Liu, Duoyun Yi, Mengxuan Wan, Yixin Zhang, Peng Zan, Song He & Xiaochen Bo  
*Nat. Mach. Intell.* **2024**  

- [ChemXTree: A Feature-Enhanced Graph Neural Network-Neural Decision Tree Framework for ADMET Prediction](https://doi.org/10.1021/acs.jcim.4c01186)  
Yuzhi Xu, Xinxin Liu, Wei Xia, Jiankai Ge, Cheng-Wei Ju, Haiping Zhang, John Z.H. Zhang  
*J. Chem. Inf. Model.* **2024**, *ASAP*

- [Quantitative structure–activity relationships of chemical bioactivity toward proteins associated with molecular initiating events of organ-specific toxicity](https://doi.org/10.1186/s13321-024-00917-x) + [GitHub Repo](https://github.com/DGadaleta88/MIE_QSAR)  
Domenico Gadaleta, Marina Garcia de Lomana, Eva Serrano-Candelas, Rita Ortega-Vallbona, Rafael Gozalbes, Alessandra Roncaglioni & Emilio Benfenati  
*J. Cheminformatics* **2024**, *16*, 122  

- [A bioactivity foundation model using pairwise meta-learning](https://doi.org/10.1038/s42256-024-00876-w) + [GitHub Repo](https://github.com/BFeng14/ActFound)  
Bin Feng, Zequn Liu, Nanlan Huang, Zhiping Xiao, Haomiao Zhang, Srbuhi Mirzoyan, Hanwen Xu, Jiaran Hao, Yinghui Xu, Ming Zhang & Sheng Wang  
*Nat. Mach. Intell.* **2024**, *6*, 962  

- [Ligand-Based Compound Activity Prediction via Few-Shot Learning](https://doi.org/10.1021/acs.jcim.4c00485) + [GitHub Repo](https://github.com/Rose-STL-Lab/FS-CAP)  
Peter Eckmann*, Jake Anderson*, Rose Yu, and Michael K. Gilson  
*J. Chem. Inf. Model.* **2024**, *64*, (14), 5492  

- [QSARtuna: An Automated QSAR Modeling Platform for Molecular Property Prediction in Drug Design](https://doi.org/10.1021/acs.jcim.4c00457) + [GitHub Repo](https://github.com/MolecularAI/QSARtuna/tree/master) + [Docs](https://molecularai.github.io/QSARtuna/)  
Lewis Mervin, Alexey Voronov, Mikhail Kabeshov, and Ola Engkvist  
*J. Chem. Inf. Model.* **2024**, *64*, (14), 5365 

- [Quantum-Informed Molecular Representation Learning Enhancing ADMET Property Prediction](https://pubs.acs.org/doi/10.1021/acs.jcim.4c00772)  
Jungwoo Kim, Woojae Chang, Hyunjun Ji, and InSuk Joung  
*J. Chem. Inf. Model.* **2024**, *64*, (13), 5028  
&ensp; Supplementing a Graph Transformer with pretraing on DFT features. SoTA performance on 7 of 22 ADME-Tox tasks in TDC. Of particular interest is the data methods and architecture.  

### Active Learning Methods

- [Human-in-the-loop active learning for goal-oriented molecule generation](https://doi.org/10.1186/s13321-024-00924-y) + [GitHub Repo](https://github.com/yasminenahal/hitl-al-gomg)  
Yasmine Nahal, Janosch Menke, Julien Martinelli, Markus Heinonen, Mikhail Kabeshov, Jon Paul Janet, Eva Nittinger, Ola Engkvist & Samuel Kaski  
*J. Cheminformatics* **2024**, *16*, 138  

- [Finding the most potent compounds using active learning on molecular pairs](hhttps://doi.org/10.3762/bjoc.20.185) + [GitHub Repo](https://github.com/RekerLab/ActiveDelta)  
Zachary Fralish, and Daniel Reker  
*Beilstein J. Org. Chem.* *2024*, *20*, 2152  
&ensp; Extension of the matched pair methodology from the Reker group. Applied to Chemprop and XGB.  

- [DeepDelta: predicting ADMET improvements of molecular derivatives with deep learning](https://doi.org/10.1186/s13321-023-00769-x) + [GitHub Repo](https://github.com/RekerLab/DeepDelta)  
Zachary Fralish, Ashley Chen, Paul Skaluba, and Daniel Reker  
*J. Cheminformatics* **2023**, *15*, 101  
&ensp; Uses matched molecular pairs to predict property diverences. D-MPNN architecture is based on ChemProp, modified to take in 2 molecules.

### Synthetic Accessibility

- [Analog Accessibility Score (AAscore) for Rational Compound Selection](https://doi.org/10.1021/acs.jcim.4c01691) + [GitHub Repo](https://github.com/U-T100/AAscore)  
Takato Ue, Akinori Sato, and Tomoyuki Miyao  
*J. Chem. Inf. Model.* **2024**, *ASAP*  

- [Estimating the synthetic accessibility of molecules with building block and reaction-aware SAScore](https://doi.org/10.1186/s13321-024-00879-0) + [GitHub Repo](https://github.com/snu-micc/BR-SAScore)  
Shuan Chen and Yousung Jung  
*J. Cheminf.* **2024**, *16*, 83  

## Molecular Optimization

- [Projecting Molecules into Synthesizable Chemical Spaces](https://arxiv.org/abs/2406.04628)  
Shitong Luo, Wenhao Gao, Zuofan Wu, Jian Peng, Connor W. Coley, and Jianzhu Ma  
*ArXiv Preprint*, **2024**  
&ensp; Interesting new approach to making molecules more synthesizable from genenerated virtual hits. Cleaning the chaff energy. Describes a new postfix notation (A B +) for synthetic transformations. Transformer-based model that translates graphs to postfix notation. Model capable of synthesis planning, generating similar and more synthesizable analogues, exploring chemical space in the syntesizablilty dimension.  

- [Evolutionary Multiobjective Molecule Optimization in an Implicit Chemical Space](https://pubs.acs.org/doi/10.1021/acs.jcim.4c00031) + [GitHub Repo](https://github.com/ahu-bioinf-lab/MOMO-master)  
Xin Xia, Yiping Liu, Chunhou Zheng, Xingyi Zhang, Qingwen Wu, Xin Gao, Xiangxiang Zeng, and Yansen Su  
*J. Chem. Inf. Model.* **2024**, *64*, (13), 5161  
&ensp; Multiobjective molecule optimization framework (MOMO) is a pareto-based MPO tool that evolves moelcules into better molecules. Genetic/ecolutionary algorithm in the latent (implicit) space ended by a VAE.  

## Virtual Screening

- [Introducing SpaceGA: A Search Tool to Accelerate Large Virtual Screenings of Combinatorial Libraries](https://doi.org/10.1021/acs.jcim.4c01308) + [GitHub Repo](https://github.com/lmoesgaard/SpaceGA)  
Laust Moesgaard and Jacob Kongsted  
*J. Chem. Inf. Model.* **2024**, *64* (21), 8123  

- [molli: A General Purpose Python Toolkit for Combinatorial Small Molecule Library Generation, Manipulation, and Feature Extraction](https://doi.org/10.1021/acs.jcim.4c00424) + [GitHub Repo](https://github.com/SEDenmarkLab/molli)  
Alexander S. Shved, Blake E. Ocampo, Elena S. Burlova, Casey L. Olen, N. Ian Rinehart & Scott E. Denmark  
*J. Chem. Inf. Model.* **2024**, *64* (21), 8083    

- [PheSA: An Open-Source Tool for Pharmacophore-Enhanced Shape Alignment](https://doi.org/10.1021/acs.jcim.4c00516) = [GitHub Repo](https://github.com/joewah/PheSAExamples)  
Joel Wahl  
*J. Chem. Inf. Model.* **2024**, *64* (15), 5944-5953    

- [ROSHAMBO: Open-Source Molecular Alignment and 3D Similarity Scoring](https://doi.org/10.26434/chemrxiv-2024-6wk09)  
Rasha Atwi, Ye Wang, Simone Sciabola, and Adam Antoszewskim  
*ChemRxiv Preprint* **2024**  

- [Pareto Optimization to Accelerate Multi-Objective Virtual Screening](https://arxiv.org/abs/2310.10598) + [GitHub Repo](https://github.com/coleygroup/molpal/tree/multiobj)  
Jenna C. Fromer, David E. Graff, and Connor W. Coley  
*arXiv preprint* **2023**  
&ensp; Application of MolPAL (Molecular Pool-based Active Learning) to multi-objective virtual screening. Implements multiobjective Bayesian optimization to reduce the computational cost and apply it to the identification of ligands predicted to be selective based on docking scores to on- and off-targets. Identifies all pareto front molecules after 8% library exploration. Demonstrates superority of pareto optimization over scalarization.  

- [Accelerating high-throughput virtual screening through molecular pool-based active learning](https://pubs.rsc.org/en/content/articlelanding/2021/sc/d0sc06805e) + [GitHub Repo](https://github.com/coleygroup/molpal)  
David E. Graff, Eugene I. Shakhnovicha, and Connor W. Coley  
*Chem. Sci.*, **2021**, *12*, 7866  
&ensp; Active learning tool for acceleration of virtual screening campaigns.  


# Cheminformatics

## Reviews

- [Modern chemical graph theory](https://doi.org/10.1002/wcms.1729)  
Leonardo S. G. Leite, Swarup Banerjee, Yihui Wei, Jackson Elowitt, Aurora E. Clark  
*WIREs Comput. Mol. Sci.* **2024**, *14*, (5), e1729  

- [Research Progresses and Applications of Knowledge Graph Embedding Technique in Chemistry](https://doi.org/10.1021/acs.jcim.4c00791)  
Chuanghui Wang, Yunqing Yang, Jinshuai Song & Xiaofei Nan  
*J. Chem. Inf. Model.* **2024**, *64*, (19), 7213  

## General

- [UNIQUE: A Framework for Uncertainty Quantification Benchmarking](https://doi.org/10.1021/acs.jcim.4c01578) + [GitHub Repo](https://github.com/Novartis/UNIQUE)  
Jessica Lanini, Minh Tam Davide Huynh, Gaetano Scebba, Nadine Schneider, and Raquel Rodríguez-Pérez  
*J. Chim. Inf. Model.* **2024** *ASAP*  
&ensp; Combo platform for model-agnostic uncertaintly quantification. Quasi-review paper.  

- [Topological Similarity Search in Large Combinatorial Fragment Spaces](https://doi.org/10.1021/acs.jcim.0c00850)  
Louis Bellmann, Patrick Penner, Matthias Rarey  
*J. Chem. Inf. Model.* **2021**, *61*, (1), 238  

- [Open-Source Approach to GPU-Accelerated Substructure Search](https://doi.org/10.1021/acs.jcim.4c00679) + [GitHub Repo](https://github.com/ZIFODS/Open_ChemSearch)  
Andrew J. Whitehouse, Melchor Sanchez-Martinez, Seyedeh Maryam Salehi, Natalja Kurbatova, and Euan Dean  
*J. Chem. Inf. Model.* **2024**, *64*, (18), 6993  

- [When Do Quantum Mechanical Descriptors Help Graph Neural Networks to Predict Chemical Properties?](https://doi.org/10.1021/jacs.4c04670)  
Shih-Cheng Li, Haoyang Wu, Angiras Menon, Kevin A. Spiekermann, Yi-Pei Li & William H. Green  
*J. Am. Chem. Soc.* **2024**, *146*, (33), 23103  

- [Hilbert-curve assisted structure embedding method](https://doi.org/10.1186/s13321-024-00850-z) + [GitHub Repo](https://github.com/ncats/hcase)  
Gergely Zahoránszky-Kőhalmi, Kanny K. Wan & Alexander G. Godfrey  
*J. Cheminf.* **2024**, *16*, 87  

## Δ-machine learning

- [Combining Hammett σ constants for Δ-machine learning and catalyst discovery](https://doi.org/10.1039/D4DD00228H) + [GitHub Repo](https://github.com/dianarak/cHIP)  
V. Diana Rakotonirina, Marco Bragato, Stefan Heinenc & O. Anatole von Lilienfeld  
*Digital Discovery* **2024**, *ASAP*  

- [Big Data meets Quantum Chemistry Approximations: The Δ-Machine Learning Approach](https://doi.org/10.48550/arXiv.1503.04987)  
Raghunathan Ramakrishnan, Pavlo O. Dral, Matthias Rupp, O. Anatole von Lilienfeld  
*J. Chem. Theory Comput.* **2015**, *11*, (5), 2087  


# Protein Structure Prediction

- [Accurate structure prediction of biomolecular interactions with AlphaFold 3](https://doi.org/10.1038/s41586-024-07487-w) - No code released  
Josh Abramson, Jonas Adler, Jack Dunger, ... & John M. Jumper  
*Nat.* **2024** *630*, 493  
&ensp; AlphaFold 3, a diffusion-based architecture that is capable of predicting the joint structure of complexes including proteins, nucleic acids, small molecules, ions and modified residues. [Blog at Isomorphic](https://www.isomorphiclabs.com/articles/rational-drug-design-with-alphafold-3)  

- [State-specific protein-ligand complex structure prediction with a multiscale deep generative model](https://doi.org/10.1038/s42256-024-00792-z) + [GitHub Repo](https://github.com/zrqiao/NeuralPLexer)  
Zhuoran Qiao, Weili Nie, Arash Vahdat, Thomas F. Miller III & Animashree Anandkumar  
*Nat. Mach. Intell.* **2024**, *6*, 195  
&ensp; NeuralPLexer, a computational approach that can directly predict protein-ligand complex structures solely using protein sequence and ligand molecular graph inputs. Owing to its specificity in sampling both ligand-free-state and ligand-bound-state ensembles, NeuralPLexer consistently outperforms AlphaFold2 in terms of global protein structure accuracy on both representative structure pairs with large conformational changes and recently determined ligand-binding proteins.  

- [DiffDock: Diffusion Steps, Twists, and Turns for Molecular Docking](https://openreview.net/forum?id=kKF8_K-mBbS) + [GitHub Repo](https://github.com/gcorso/DiffDock)  
Gabriele Corso, Hannes Stärk, Bowen Jing, Regina Barzilay, and Tommi Jaakkola  
*ICLR* **2023**  
&ensp; Cool paper that treats docking as a generative task instead of a search/regression task. DiffDock is a diffusion model over the non-Euclidean manifold of ligand poses. Really interesting way of thinking of things.

- [Structure-based Drug Design with Equivariant Diffusion Models (DiffSBDD)](https://arxiv.org/abs/2210.13695) + [GitHub Repo](https://github.com/arneschneuing/diffsbdd)  
Arne Schneuing, Yuanqi Du, Charles Harris, Arian Jamasb, Ilia Igashov, Weitao Du, Tom Blundell, Pietro Lió, Carla Gomes, Max Welling, Michael Bronstein, and Bruno Correia  
*ArXiv Preprint* **2022**  
&ensp; Diffusion model for SBDD, serious issues with results in this paper see [OpenReview](https://openreview.net/forum?id=uKmuzIuVl8z)  

- [Accelerating Inference in Molecular Diffusion Models with Latent Representations of Protein Structure](https://arxiv.org/abs/2311.13466) + [GitHub Repo](https://github.com/dunni3/keypoint-diffusion)  
Ian Dunn and David Ryan Koes  
*NeurIPS* **2023**  
&ensp; GNN-based architecture for learning latent representations of molecular structure. Encodes protein represntation into reduced set of key points. When trained end-to-end with a diffusion model (DiffSBDD) for *de novo* ligand design, achieves comparable performance to one with an all-atom protein representation while exhibiting a 3-fold reduction in inference time. Unclear whether or not the original issues with DiffSBDD were address in this implementation...  


# Deep Learning

- [Mixture of A Million Experts](https://doi.org/10.48550/arXiv.2407.04153)  
Xu Owen He  
*ArXiv Preprint* **2024**  

- [Graph Neural Networks with Learnable Structural and Positional Representations](https://arxiv.org/abs/2110.07875) + [GitHub Repo](https://github.com/vijaydwivedi75/gnn-lspe)  
Vijay Prakash Dwivedi, Anh Tuan Luu, Thomas Laurent, Yoshua Bengio, Xavier Bresson  
*ICLR* **2022**  

- [Do Transformers Really Perform Badly for Graph Representation?](https://proceedings.neurips.cc/paper/2021/hash/f1c1592588411002af340cbaedd6fc33-Abstract.html) + [GitHub Repo](https://github.com/Microsoft/Graphormer)  
Chengxuan Ying, Tianle Cai, Shengjie Luo, Shuxin Zheng, Guolin Ke, Di He, Yanming Shen, Tie-Yan Liu  
*NeurIPS* **2021**  
&ensp; Microsoft's Graphormer paper  

- [Denoising Diffusion Probabilistic Models](https://doi.org/10.48550/arXiv.2006.11239) + [GitHub Repo](https://github.com/hojonathanho/diffusion) + [Website](https://hojonathanho.github.io/diffusion/)  
Jonathan Ho, Ajay Jain, Pieter Abbee  
*NeurIPS* **2020**  

- [Attention is All You Need](https://arxiv.org/abs/1706.03762) + [GitHub Repo (archived)](https://github.com/tensorflow/tensor2tensor)  
Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, and Illia Polosukhin  
*NeurIPS* **2017**  
&ensp; The one, the only...  Original transformer paper. This code eventually becomes the 🤗 Transformers library  

- [Adversarial Autoencoders](https://arxiv.org/abs/1511.05644) - No official implementation available  
Alireza Makhzani, Jonathon Shlens, Navdeep Jaitly, Ian Goodfellow, and Brendan Frey  
*ArXiv Preprint* **2016**  

- [PointerNets](https://papers.nips.cc/paper_files/paper/2015/hash/29921001f2f04bd3baee84a12e98098f-Abstract.html)  
Oriol Vinyals, Meire Fortunato, and Navdeep Jaitly  
*NeurIPS* **2015**  


## LLMs and Agents

- [MemGPT: Towards LLMs as Operating Systems](https://doi.org/10.48550/arXiv.2310.08560) + [GitHub Repo](https://github.com/letta-ai/letta)  
Charles Packer, Sarah Wooders, Kevin Lin, Vivian Fang, Shishir G. Patil, Ion Stoica, and Joseph E. Gonzalez  
*arXiv* **2024**  

- [AvaTaR: Optimizing LLM Agents for Tool Usage via Contrastive Reasoning](https://doi.org/10.48550/arXiv.2406.11200) + [GitHub Repo](https://github.com/zou-group/avatar)  
Shirley Wu, Shiyu Zhao, Qian Huang, Kexin Huang, Michihiro Yasunaga, Kaidi Cao, Vassilis N. Ioannidis, Karthik Subbian, Jure Leskovec, and James Zou  
*NeurIPS* **2024**  

- [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685) + [GitHub Repo](https://github.com/microsoft/LoRA)    
Edward J. Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, and Weizhu Chen  
*ICLR* **2022**  
&ensp; LoRA is now wrapped into the 🤗 PEFT library

- [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://doi.org/10.48550/arXiv.2005.11401)   
Patrick Lewis, Ethan Perez, Aleksandra Piktus, Fabio Petroni, Vladimir Karpukhin, Naman Goyal, Heinrich Küttler, Mike Lewis, Wen-tau Yih, Tim Rocktäschel, Sebastian Riedel, and Douwe Kiela  
*NeurIPS* **2020**  
  

## Neural Reasoning & Decision Making

- [Quiet-STaR: Language Models Can Teach Themselves to Think Before Speaking](https://doi.org/10.48550/arXiv.2403.09629)  
Eric Zelikman, Georges Harik, Yijia Shao, Varuna Jayasiri, Nick Haber, and Noah D. Goodman  
*CoLM* **2024**  

- [LLaVA-CoT: Let Vision Language Models Reason Step-by-Step](https://doi.org/10.48550/arXiv.2411.10440) + [GitHub Repo](https://github.com/PKU-YuanGroup/LLaVA-CoT)  
Guowei Xu, Peng Jin, Hao Li, Yibing Song, Lichao Sun, and Li Yuan  
*NeurIPS* **2024**  

- [Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://doi.org/10.48550/arXiv.2305.10601) + [GitHub Repo](https://github.com/princeton-nlp/tree-of-thought-llm)  
Shunyu Yao, Dian Yu, Jeffrey Zhao, Izhak Shafran, Thomas L. Griffiths, Yuan Cao, Karthik Narasimhan  
*NeurIPS* **2023**  
&ensp; [ReasoningAgent (Tree of Thought with Beam Search)](https://ag2ai.github.io/ag2/docs/notebooks/agentchat_reasoning_agent/)  

- [STaR: Bootstrapping Reasoning With Reasoning](https://doi.org/10.48550/arXiv.2203.14465)  
Eric Zelikman, Yuhuai Wu, Jesse Mu, and Noah D. Goodman  
*NeurIPS* **2022**  

- [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://doi.org/10.48550/arXiv.2201.11903)  
Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Brian Ichter, Fei Xia, Ed Chi, Quoc Le, and Denny Zhou  
*NeurIPS* **2022**

## Contrastive Learning

- [A Simple Framework for Contrastive Learning of Visual Representations](https://doi.org/10.48550/arXiv.2002.05709) + [GitHub Repo](https://github.com/google-research/simclr)  
Ting Chen, Simon Kornblith, Mohammad Norouzi & Geoffrey Hinton  
*in Proceedings of the 37th International Conference on Machine Learning*, PMLR 119:1597-1607, **2020**  

- [FaceNet: A Unified Embedding for Face Recognition and Clustering](https://doi.org/10.48550/arXiv.1503.03832)  
Florian Schroff, Dmitry Kalenichenko, James Philbin  
*in Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*, **2015**, 815


# Chemistry

## Med Chem

- [Escape from Flatland: Increasing Saturation as an Approach to Improving Clinical Success](https://doi.org/10.1021/jm901241e)  
Frank Lovering, Jack Bikker, and Christine Humblet  
*J. Med. Chem.* **2009**, *52* (21), 6752-6756  

- [Escape from Flatland 2: complexity and promiscuity](hhttps://doi.org/10.1039/C2MD20347B)  
Frank Lovering  
*Med. Chem. Commun.* **2013**, *4*, 515-519  


# My papers

- [Sodium Alkyl(trimethylsilyl)amides: Substituent- and Solvent-dependent Solution Structures and Reactivities](https://doi.org/10.1021/jacs.4c10836)  
Qiulin You, Yun Ma, Ryan A. Woltornist, **Nathan M. Lui**, Jesse A. Spivey, Ivan Keresztes, David B. Collum  
*Journal of the American Chemical Society* **2024**, *146* (44), 30397  

- [Natural Product Isolation of the Extract of Cleome rupicola Fruits Exhibiting Antioxidant Activity](https://doi.org/10.1002/cbdv.202301382)  
Yumi Gambrill, Patrick Commins, Stefan Schramm, **Nathan M. Lui**, Shaikha S. AlNeyadi, Panče Naumov  
*Chemistry & Biodiversity* **2024**, *21* (4), e20230138  

- [Structure-Selectivity Principles Underlying Alkylations of Oppolzer's Camphorsultam Enolates](https://www.proquest.com/openview/c20f7b7aa67c2b55b8917c4cf91f27ff)  
**Nathan M. Lui**  
*Cornell University ProQuest Dissertations & Theses* **2023**, 30570998

- [Sodiated Oppolzer enolates: solution structures, mechanism of alkylation, and origin of stereoselectivity](https://doi.org/10.1039/D3QO01021J)  
**Nathan M. Lui** and David B. Collum  
*Organic Chemistry Frontiers* **2023**, *10* (19), 4750  

- [MoFlowGAN: Combining adversarial and likelihood learning for targeted molecular generation](https://doi.org/10.26434/chemrxiv-2023-kwwv3) + [GitHub Repo](https://github.com/thisisntnathan/MoFlowGAN)  
**Nathan M. Lui**, Max D. Li, and Matt Ford  
*ChemRxiv Preprint* **2023**  

- [Lithiated Oppolzer Enolates: Solution Structures, Mechanism of Alkylation, and the Origin of Stereoselectivity](https://doi.org/10.1021/jacs.2c09341)  
**Nathan M. Lui**, Samantha N. MacMillan, and David B. Collum  
*Journal of the American Chemical Society* **2022**, *144* (51), 23379  

- [Sodium Isopropyl(trimethylsilyl)amide (NaPTA): A Stable and Highly Soluble Lithium Diisopropylamide Mimic](https://pubs.acs.org/doi/10.1021/acs.joc.2c01745)  
Yun Ma, **Nathan M. Lui**, Ivan Keresztes, Ryan A. Woltornist, and David B. Collum  
*The Journal of Organic Chemistry* **2022**, *87* (21), 14223  

- [Spectrochemistry of firefly bioluminescence](https://doi.org/10.1021/acs.chemrev.1c01047)  
Marieh B. Al-Handawi, Srujana Polavaram, Anastasiya Kurlevskaya, Patrick Commins, Stefan Schramm, César Carrasco-López, **Nathan M. Lui**, Kyril M. Solntsev, Sergey P. Laptenok, Isabelle Navizet, and Panče Naumov  
*Chemical Reviews* **2022**, *122* (16), 13207  

- [The elusive relationship between structure and colour emission in beetle luciferases](https://doi.org/10.1038/s41570-020-00238-1)  
César Carrasco-López, **Nathan M. Lui**, Stefan Schramm, and Panče Naumov  
*Nature Reviews Chemistry* **2021**, *5* (1), 4  

- [Thermochemiluminescent peroxide crystals](https://doi.org/10.1038/s41467-019-08816-8)  
Stefan Schramm, Durga Prasad Karothu, **Nathan M. Lui**, Patrick Commins, Ejaz Ahmed, Luca Catalano, Liang Li, James Weston, Taro Moriwaki, Kyril M. Solntsev, and Panče Naumov  
*Nature Communications* **2019**, *10* (1), 997  

- [pH-Dependent fluorescence from firefly oxyluciferin in agarose thin films](https://doi.org/10.1039/C8NJ05469J)  
**Nathan M. Lui**, Stefan Schramm, and Panče Naumov  
*New Journal of Chemistry* **2019**, *43* (3), 1122  

- [Beetle luciferases with naturally red-and blue-shifted emission](https://doi.org/10.26508/lsa.201800072)  
César Carrasco-López, Juliana C Ferreira, **Nathan M. Lui**, Stefan Schramm, Romain Berraud-Pache, Isabelle Navizet, Santosh Panjikar, Panče Naumov, Wael M. Rabeh  
*Life Science Alliance* **2018**, *1* (4), e201800072  
