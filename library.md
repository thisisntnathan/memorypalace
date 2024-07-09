---
layout: article
title: Paper Library
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

- [Machine learning-aided generative molecular design](https://www.nature.com/articles/s42256-024-00843-5)  
Yuanqi Du, Arian R. Jamasb, Jeff Guo, Tianfan Fu, Charles Harris, Yingheng Wang, Chenru Duan, Pietro Liò, Philippe Schwaller, and Tom L. Blundell  
*Nat. Mach. Intell.*, **2024**  

- [Deep Generative Models in *De Novo* Drug Molecule Generation](https://pubs.acs.org/doi/10.1021/acs.jcim.3c01496)  
Chao Pang, Jianbo Qiao, Xiangxiang Zeng, Quan Zou, and Leyi Wei  
*J. Chem. Inf. Model.* **2024**, 64 (7), 2174–2194  

## Diffusion Models

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

- [Llamol: a dynamic multi-conditional generative transformer for de novo molecular design](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-024-00863-8)  
Niklas Dobberstein, Astrid Maass & Jan Hamaekers  
*J. of Cheminf.*, **2024**, 16, 73  
&ensp; Transformer based on Llama2, tweaked for molgen. Not the most impressive paper, but some interesting tidbits scatted throughout (e.g., SCL, etc...)  

- [REINVENT4: Modern AI–driven generative molecule design](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-024-00812-5) + [GitHub Repo](https://github.com/MolecularAI/REINVENT4)  
Hannes H. Loeffler, Jiazhen He, Alessandro Tibo, Jon Paul Janet, Alexey Voronov, Lewis H. Mervin & Ola Engkvist  
*J. of Cheminf.*, **2024**, 16, 20  
&ensp; AstraZeneca's molecular design tool for *de novo* design, scaffold hopping, R-group replacement, linker design and molecule optimization.  

- [Masked graph modeling for molecule generation](https://www.nature.com/articles/s41467-021-23415-2) + [GitHub Repo](https://github.com/nyu-dl/dl4chem-mgm)  
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

- [Discovery of novel chemical reactions by deep generative recurrent neural network](https://www.nature.com/articles/s41598-021-81889-y)  
William Bort, Igor I. Baskin, Timur Gimadiev, Artem Mukanov, Ramil Nugmanov, Pavel Sidorov, Gilles Marcou, Dragos Horvath, Olga Klimchuk, Timur Madzhidov, and Alexandre Varnek  
*Sci. Rep.* **2021**, *11*, 3178  

- [Efficient prediction of reaction paths through molecular graph and reaction network analysis](https://doi.org/10.1039/C7SC03628K)  
Yeonjoon Kim, Jin Woo Kim, Zeehyo Kim, and Woo Youn Kim  
*Chem. Sci.* **2018**, *9*, 825-835  
&ensp; Search method for reaction intermediate networks. Uses DFT energies as heuristic.  


## Other

- [Transfer learning enables the molecular transformer to predict regio- and stereoselective reactions on carbohydrates](https://www.nature.com/articles/s41467-020-18671-7) + [GitHub Repo](https://github.com/rxn4chemistry/OpenNMT-py/tree/carbohydrate_transformer)  
Giorgio Pesciullesi, Philippe Schwaller, Teodoro Laino, and Jean-Louis Reymond  
*Nat. Commun.* **2020**, *11*, 4874  
&ensp; Seq2Seq model for SMILES strings. Transfer learning allows for success on few-instance reactions. [Blog post](https://communities.springernature.com/posts/transfer-learning-enables-the-molecular-transformer-to-predict-regio-and-stereoselective-reactions-on-carbohydrates)


## Tools

- [Bidirectional Graphormer for Reactivity Understanding: Neural Network Trained to Reaction Atom-to-Atom Mapping Task](https://pubs.acs.org/doi/10.1021/acs.jcim.2c00344) + [GitHub Repo](https://github.com/chython/chytorch-rxnmap)  
Ramil Nugmanov, Natalia Dyubankova, Andrey Gedich, and Joerg Kurt Wegner  
*J. Chem. Inf. Model.* **2022**, *62*, 14, 3307–3315  
&ensp; Chython RxnMapper/Graphormer Mapper that's heavily based on RXNMapper and CGR Tools. Semisupervised graph attention based model trained on USPTO and Pistachio datasets.  

- [Atom-to-atom Mapping: A Benchmarking Study of Popular Mapping Algorithms and Consensus Strategies](https://onlinelibrary.wiley.com/doi/10.1002/minf.202100138)  
Arkadii Lin, Natalia Dyubankova, Timur I. Madzhidov, Ramil I. Nugmanov, Jonas Verhoeven, Timur R. Gimadiev, Valentina A. Afonina, Zarina Ibragimova, Assima Rakhimbekova, Pavel Sidorov, Andrei Gedich, Rail Suleymanov, Ravil Mukhametgaleev, Joerg Wegner, Hugo Ceulemans, and Alexandre Varnek  
*Mol. Inf.* **2022**, *41*, 2100138  

- [Reaction Data Curation I: Chemical Structures and Transformations Standardization](https://onlinelibrary.wiley.com/doi/10.1002/minf.202100119) + [GitHub Repo](https://github.com/Laboratoire-de-Chemoinformatique/Reaction_Data_Cleaning)  
Timur R. Gimadiev, Arkadii Lin, Valentina A. Afonina, Dinar Batyrshin, Ramil I. Nugmanov, Tagir Akhmetshin, Pavel Sidorov, Natalia Duybankova, Jonas Verhoeven, Joerg Wegner, Hugo Ceulemans, Andrey Gedich, Timur I. Madzhidov, and Alexandre Varnek  
*Mol. Inf.* **2021**, *40*, 2100119  


# Computer-Aided Retrosynthesis Planning

- [Constrained synthesis planning with disconnection-aware transformer and multi-objective search](https://doi.org/10.26434/chemrxiv-2024-c77p4)  
Annie M. Westerlund, Lakshidaa Saigiridharan, Samuel Genheden  
*ChemRxiv preprint* **2024**  
&ensp; Retrosynthesis planning with the ability to constrain bonds, i.e., built in divergent synthesis constraints leading to shorter routes.  
&ensp; AiZynthFinder with MO-MCTS and broken bonds score was used to run multistep experiments and can be found at: [https://github.com/MolecularAI/aizynthfinder](https://github.com/MolecularAI/aizynthfinder). Chemformer can be found at: [https://github.com/MolecularAI/Chemformer](https://github.com/MolecularAI/Chemformer). AiZynthTrain was used to tag
disconnection-sites in the Chemformer training data and can be found at: [https://github.com/MolecularAI/aizynthtrain](https://github.com/MolecularAI/aizynthtrain). 

- [Retrosynthesis prediction using an end-to-end graph generative architecture for molecular graph editing](https://www.nature.com/articles/s41467-023-38851-5) + [GitHub Repo](https://github.com/Jamson-Zhong/Graph2Edits)  
Weihe Zhong, Ziduo Yang, and Calvin Yu-Chian Chen  
*Nat. Commun.* **2023**, *14*, 3009  


# Publication Parsing

- [OpenChemIE: An Information Extraction Toolkit for Chemistry Literature](https://doi.org/10.1021/acs.jcim.4c00572) + [Web App](https://mit.openchemie.info/)  
Vincent Fan, Yujie Qian, Alex Wang, Amber Wang, Connor W. Coley, and Regina Barzilay  
*J. Chem. Inf. Model.* **2024**, *ASAP*  

- [Advancements in hand-drawn chemical structure recognition through an enhanced DECIMER architecture](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-024-00872-7)  
Kohulan Rajan, Henning Otto Brinkhaus, Achim Zielesny & Christoph Steinbeck  
*J. Cheminf.* **2024**, *16*, 76



# ML Driven Drug Design

## General

- [Exposing the Limitations of Molecular Machine Learning with Activity Cliffs](https://pubs.acs.org/doi/10.1021/acs.jcim.2c01073)  
Derek van Tilborg, Alisa Alenicheva, and Francesca Grisoni  
*J. Chem. Inf. Model.* **2022**, *62* (23), 5938–5951  
&ensp; Overview of SAR cliffs and challenges for ML  

## Property Prediction

- [Ligand-Based Compound Activity Prediction via Few-Shot Learning](https://doi.org/10.1021/acs.jcim.4c00485) + [GitHub Repo](https://github.com/Rose-STL-Lab/FS-CAP)  
Peter Eckmann*, Jake Anderson*, Rose Yu*, and Michael K. Gilson  
*J. Chem. Inf. Model.* **2024**, *ASAP*  

-[QSARtuna: An Automated QSAR Modeling Platform for Molecular Property Prediction in Drug Design](https://doi.org/10.1021/acs.jcim.4c00457) + [GitHub Repo](https://github.com/MolecularAI/QSARtuna/tree/master) + [Docs](https://molecularai.github.io/QSARtuna/)  
Lewis Mervin, Alexey Voronov, Mikhail Kabeshov, and Ola Engkvist  
*J. Chem. Inf. Model.* **2024**, *ASAP*  

- [Quantum-Informed Molecular Representation Learning Enhancing ADMET Property Prediction](https://pubs.acs.org/doi/10.1021/acs.jcim.4c00772)  
Jungwoo Kim, Woojae Chang, Hyunjun Ji, and InSuk Joung  
*J. Chem. Inf. Model.* **2024**, *64*, 13, 5028  
&ensp; Supplementing a Graph Transformer with pretraing on DFT features. SoTA performance on 7 of 22 ADME-Tox tasks in TDC. Of particular interest is the data methods and architecture.  

- [DeepDelta: predicting ADMET improvements of molecular derivatives with deep learning](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-023-00769-x) + [GitHub Repo](https://github.com/RekerLab/DeepDelta)  
Zachary Fralish, Ashley Chen, Paul Skaluba, and Daniel Reker  
*J. Cheminformatics* **2023**, *15*, 101  
&ensp; Uses matched molecular pairs to predict property diverences. D-MPNN architecture is based on ChemProp, modified to take in 2 molecules.

## Molecular Optimization

- [Projecting Molecules into Synthesizable Chemical Spaces](https://arxiv.org/abs/2406.04628)  
Shitong Luo, Wenhao Gao, Zuofan Wu, Jian Peng, Connor W. Coley, and Jianzhu Ma  
*ArXiv Preprint*, **2024**  
&ensp; Interesting new approach to making molecules more synthesizable from genenerated virtual hits. Cleaning the chaff energy. Describes a new postfix notation (A B +) for synthetic transformations. Transformer-based model that translates graphs to postfix notation. Model capable of synthesis planning, generating similar and more synthesizable analogues, exploring chemical space in the syntesizablilty dimension.  

- [Evolutionary Multiobjective Molecule Optimization in an Implicit Chemical Space](https://pubs.acs.org/doi/10.1021/acs.jcim.4c00031) + [GitHub Repo](https://github.com/ahu-bioinf-lab/MOMO-master)  
Xin Xia, Yiping Liu, Chunhou Zheng, Xingyi Zhang, Qingwen Wu, Xin Gao, Xiangxiang Zeng, and Yansen Su  
*J. Chem. Inf. Model.* **2024**, *ASAP*  
&ensp; Multiobjective molecule optimization framework (MOMO) is a pareto-based MPO tool that evolves moelcules into better molecules. Genetic/ecolutionary algorithm in the latent (implicit) space ended by a VAE.  

## Virtual Screening

- [Pareto Optimization to Accelerate Multi-Objective Virtual Screening](https://arxiv.org/abs/2310.10598) + [GitHub Repo](https://github.com/coleygroup/molpal/tree/multiobj)  
Jenna C. Fromer, David E. Graff, and Connor W. Coley  
*arXiv preprint* **2023**  
&ensp; Application of MolPAL (Molecular Pool-based Active Learning) to multi-objective virtual screening. Implements multiobjective Bayesian optimization to reduce the computational cost and apply it to the identification of ligands predicted to be selective based on docking scores to on- and off-targets. Identifies all pareto front molecules after 8% library exploration. Demonstrates superority of pareto optimization over scalarization.  

- [Accelerating high-throughput virtual screening through molecular pool-based active learning](https://pubs.rsc.org/en/content/articlelanding/2021/sc/d0sc06805e) + [GitHub Repo](https://github.com/coleygroup/molpal)  
David E. Graff, Eugene I. Shakhnovicha, and Connor W. Coley  
*Chem. Sci.*, **2021**, *12*, 7866-7881  
&ensp; Active learning tool for acceleration of virtual screening campaigns.  


# Protein Structure Prediction

- [Accurate structure prediction of biomolecular interactions with AlphaFold 3](https://www.nature.com/articles/s41586-024-07487-w) - No code released  
Josh Abramson, Jonas Adler, Jack Dunger, ... & John M. Jumper  
*Nat.* **2024** *630*, 493–500  
&ensp; AlphaFold 3, a diffusion-based architecture that is capable of predicting the joint structure of complexes including proteins, nucleic acids, small molecules, ions and modified residues. [Blog at Isomorphic](https://www.isomorphiclabs.com/articles/rational-drug-design-with-alphafold-3)  

- [State-specific protein–ligand complex structure prediction with a multiscale deep generative model](https://www.nature.com/articles/s42256-024-00792-z) + [GitHub Repo](https://github.com/zrqiao/NeuralPLexer)  
Zhuoran Qiao, Weili Nie, Arash Vahdat, Thomas F. Miller III & Animashree Anandkumar  
*Nat. Mach. Intell.* **2024** *6*, 195–208  
&ensp; NeuralPLexer, a computational approach that can directly predict protein–ligand complex structures solely using protein sequence and ligand molecular graph inputs. Owing to its specificity in sampling both ligand-free-state and ligand-bound-state ensembles, NeuralPLexer consistently outperforms AlphaFold2 in terms of global protein structure accuracy on both representative structure pairs with large conformational changes and recently determined ligand-binding proteins.  

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

- [Graph Neural Networks with Learnable Structural and Positional Representations](https://arxiv.org/abs/2110.07875) + [GitHub Repo](https://github.com/vijaydwivedi75/gnn-lspe)  
Vijay Prakash Dwivedi, Anh Tuan Luu, Thomas Laurent, Yoshua Bengio, Xavier Bresson  
*ICLR* **2022**  

- [Attention is All You Need](https://arxiv.org/abs/1706.03762) + [GitHub Repo (archived)](https://github.com/tensorflow/tensor2tensor)  
Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, and Illia Polosukhin  
*NeurIPS* **2017**  
&ensp; The one, the only...  Original transformer paper  

- [Adversarial Autoencoders](https://arxiv.org/abs/1511.05644) - No official implementation available  
Alireza Makhzani, Jonathon Shlens, Navdeep Jaitly, Ian Goodfellow, and Brendan Frey  
*ArXiv Preprint* **2016**  

- [PointerNets](https://papers.nips.cc/paper_files/paper/2015/hash/29921001f2f04bd3baee84a12e98098f-Abstract.html)  
Oriol Vinyals, Meire Fortunato, and Navdeep Jaitly  
*NeurIPS* **2015**  


# Chemistry

## Quick References

[NMR Impurity Chart(Organometallics)](https://pubs.acs.org/doi/full/10.1021/om100106e)  
[The Big NMR Impurity Chart (OPR&D)](https://pubs.acs.org/doi/full/10.1021/acs.oprd.5b00417)  


# My papers

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

- [The elusive relationship between structure and colour emission in beetle luciferases](https://www.nature.com/articles/s41570-020-00238-1)  
César Carrasco-López, **Nathan M. Lui**, Stefan Schramm, and Panče Naumov  
*Nature Reviews Chemistry* **2021**, *5* (1), 4  

- [Thermochemiluminescent peroxide crystals](https://www.nature.com/articles/s41467-019-08816-8)  
Stefan Schramm, Durga Prasad Karothu, **Nathan M. Lui**, Patrick Commins, Ejaz Ahmed, Luca Catalano, Liang Li, James Weston, Taro Moriwaki, Kyril M. Solntsev, and Panče Naumov  
*Nature Communications* **2019**, *10* (1), 997  

- [pH-Dependent fluorescence from firefly oxyluciferin in agarose thin films](https://doi.org/10.1039/C8NJ05469J)  
**Nathan M. Lui**, Stefan Schramm, and Panče Naumov  
*New Journal of Chemistry* **2019**, *43* (3), 1122  

- [Beetle luciferases with naturally red-and blue-shifted emission](https://www.life-science-alliance.org/content/1/4/e201800072)  
César Carrasco-López, Juliana C Ferreira, **Nathan M. Lui**, Stefan Schramm, Romain Berraud-Pache, Isabelle Navizet, Santosh Panjikar, Panče Naumov, Wael M. Rabeh  
*Life Science Alliance* **2018**, *1* (4), e201800072  
