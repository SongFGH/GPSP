# GPSP
This is the code and supplementary materials for the paper appeared in WWW2018, *GPSP: Graph Partition and Space Projection based approach for Heterogeneous Network Embedding*. 

The data and embeddings are aviable at https://drive.google.com/open?id=1PFp1E0O4I2LbitPo4_SV_0VP5hs2Z5gp.

## Specification
### GPSP-code
- SubFolder preprocessing : preprocessing steps for the data
- SubFolder pte : implmentation of pte
- SubFolder space projection is the space projection step
- SubFolder node classification : codes for nodes classification 
- SubFolder node clustering  : codes for nodes clustering 
- SubFolder visulization : codes for modifying data for the embedding projector
### img
- Algorithm and visulazation images

## Development Environment
- OS: Ubuntu 16.04 LTS
- Language: Python 3.5.2
- CPU: Intel® Core™ i7-5820K CPU @ 3.30GHz × 12 
- RAM: 32GB
- Libraries:
    - numpy 1.13.1
    - pandas 0.21.1
    - NLTK 3.2.5
    - scikit-learn 0.18.1
## Algorithm
- The followings are the summary of GPSP algorithm

![alt text][a1]

[a1]: https://github.com/Ange1o/GPSP/raw/master/img/algorithm1.png "Algorithm 1"


![alt text][a2]

[a2]: https://github.com/Ange1o/GPSP/raw/master/img/algorithm2.png "Algorithm 2"

![alt text][a3]

[a3]: https://github.com/Ange1o/GPSP/raw/master/img/algorithm3.png "Algorithm 3"


## Experimental Details



### Visulization using Tensorflow Projector (2D t-sne)

- The learned embeddings are fed into [Tensorflow Projector](http://projector.tensorflow.org/) using t-sne.
- Below is the visulization of GPSP-DeepWalk.
- Eight groups are Computing Systems, Theoretical Computer Science, Computer Networks & Wireless Communication, Computer Graphics, Human Computer Interaction, Computational Linguistics, Computer Vision & Pattern Recognition, Databases & Information Systems.

![alt text][v1]

[v1]: https://github.com/Ange1o/GPSP/raw/master/img/gpspD.PNG "Embedding"

- GPSPL == GPSP-LINE
- GPSPD == GPSP-DeepWalk

### Multi-label classification results (Micro-F1)

|        Method        |    10%     |    20%     |    30%     |    40%     |    50%     |    60%     |    70%     |    80%     |    90%     |
| :------------------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
|       LINE-1st       |   0.7003   |   0.7069   |   0.7081   |   0.7087   |   0.7087   |   0.7084   |   0.7079   |   0.7087   |   0.7079   |
|       LINE-2nd       |   0.6436   |   0.6446   |   0.6457   |   0.6462   |   0.6463   |   0.6458   |   0.6456   |   0.6450   |   0.6470   |
|     LINE-1st+2nd     |   0.7062   |   0.7064   |   0.7067   |   0.7075   |   0.7074   |   0.7077   |   0.7062   |   0.7072   |   0.7075   |
|   GPSPL-author 1st   |   0.6390   |   0.6420   |   0.6430   |   0.6436   |   0.6439   |   0.6432   |   0.6426   |   0.6448   |   0.6455   |
|   GPSPL-author 2nd   |   0.6162   |   0.6179   |   0.6184   |   0.6186   |   0.6181   |   0.6181   |   0.6183   |   0.6199   |   0.6212   |
| GPSPL-author 1st+2nd |   0.6487   |   0.6509   |   0.6515   |   0.6519   |   0.6522   |   0.6515   |   0.6519   |   0.6534   |   0.6540   |
|   GPSPL-paper 1st    |   0.7118   |   0.7148   |   0.7136   |   0.7156   |   0.7167   |   0.7127   |   0.7219   |   0.7206   |   0.7227   |
|   GPSPL-paper 2nd    |   0.6532   |   0.6546   |   0.6553   |   0.6554   |   0.6546   |   0.6540   |   0.6552   |   0.6521   |   0.6565   |
| GPSPL-paper 1st+2nd  |   0.7235   |   0.7247   |   0.7247   |   0.7252   |   0.7256   |   0.7250   |   0.7262   |   0.7256   |   0.7267   |
|         PTE          |   0.7122   |   0.7125   |   0.7129   |   0.7135   |   0.7133   |   0.7138   |   0.7140   |   0.7135   |   0.7138   |
|     metapath2vec     |   0.6546   |   0.6547   |   0.6549   |   0.6550   |   0.6547   |   0.6551   |   0.6552   |   0.6537   |   0.6529   |
|    metapath2vec++    |   0.6692   |   0.6687   |   0.6681   |   0.6679   |   0.6676   |   0.6678   |   0.6677   |   0.6658   |   0.6651   |
|       Deepwalk       |   0.6992   |   0.6998   |   0.7010   |   0.7008   |   0.6992   |   0.6988   |   0.6986   |   0.6964   |   0.6988   |
|     GPSPD-author     |   0.5919   |   0.5936   |   0.5950   |   0.5968   |   0.5963   |   0.5993   |   0.5974   |   0.5995   |   0.5980   |
|     GPSPD-paper      |   0.7010   |   0.7011   |   0.7016   |   0.7019   |   0.7021   |   0.7020   |   0.7018   |   0.7023   |   0.7020   |
|        GPSPD         | **0.7275** | **0.7304** | **0.7318** | **0.7330** | **0.7324** | **0.7328** | **0.7320** | **0.7331** | **0.7318** |
|      GPSPL 1st       |   0.7344   |   0.7378   |   0.7397   |   0.7396   |   0.7391   |   0.7401   |   0.7410   |   0.7425   |   0.7388   |
|      GPSPL 2nd       |   0.7121   |   0.7128   |   0.7141   |   0.7130   |   0.7148   |   0.7146   |   0.7137   |   0.7145   |   0.7159   |
|    GPSPL 1st+2nd     | **0.7512** | **0.7540** | **0.7557** | **0.7564** | **0.7564** | **0.7558** | **0.7554** | **0.7574** | **0.7552** |

### Multi-label classification results (Macro-F1)

|        Method        |    10%     |    20%     |    30%     |    40%     |    50%     |    60%     |    70%     |    80%     |    90%     |
| :------------------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: | :--------: |
|       LINE-1st       |   0.6996   |   0.7050   |   0.7061   |   0.7069   |   0.7067   |   0.7062   |   0.7056   |   0.7063   |   0.7059   |
|       LINE-2nd       |   0.6389   |   0.6400   |   0.6413   |   0.6417   |   0.6419   |   0.6415   |   0.6409   |   0.6403   |   0.6426   |
|     LINE-1st+2nd     |   0.7032   |   0.7034   |   0.7036   |   0.7046   |   0.7043   |   0.7049   |   0.7035   |   0.7044   |   0.7036   |
|   GPSPL-author 1st   |   0.6399   |   0.6427   |   0.6434   |   0.6439   |   0.6438   |   0.6436   |   0.6424   |   0.6451   |   0.6451   |
|   GPSPL-author 2nd   |   0.6119   |   0.6136   |   0.6141   |   0.6143   |   0.6140   |   0.6138   |   0.6138   |   0.6162   |   0.6169   |
| GPSPL-author 1st+2nd |   0.6477   |   0.6498   |   0.6506   |   0.6507   |   0.6508   |   0.6501   |   0.6506   |   0.6529   |   0.6528   |
|   GPSPL-paper 1st    |   0.7087   |   0.7112   |   0.7099   |   0.7120   |   0.7130   |   0.7083   |   0.7198   |   0.7177   |   0.7211   |
|   GPSPL-paper 2nd    |   0.6557   |   0.6574   |   0.6580   |   0.6582   |   0.6571   |   0.6570   |   0.6578   |   0.6550   |   0.6591   |
| GPSPL-paper 1st+2nd  |   0.7212   |   0.7226   |   0.7226   |   0.7230   |   0.7231   |   0.7229   |   0.7243   |   0.7232   |   0.7251   |
|         PTE          |   0.7089   |   0.7093   |   0.7094   |   0.7098   |   0.7101   |   0.7104   |   0.7090   |   0.7099   |   0.7094   |
|     metapath2vec     |   0.6307   |   0.6310   |   0.6313   |   0.6317   |   0.6322   |   0.6325   |   0.6328   |   0.6313   |   0.6301   |
|    metapath2vec++    |   0.6478   |   0.6475   |   0.6473   |   0.6477   |   0.6478   |   0.6474   |   0.6473   |   0.6456   |   0.6445   |
|       Deepwalk       |   0.6964   |   0.6969   |   0.6982   |   0.6981   |   0.6965   |   0.6964   |   0.6963   |   0.6937   |   0.6961   |
|     GPSPD-author     |   0.5872   |   0.5887   |   0.5912   |   0.5922   |   0.5912   |   0.5977   |   0.5941   |   0.5971   |   0.5944   |
|     GPSPD-paper      |   0.7012   |   0.7015   |   0.7018   |   0.7020   |   0.7022   |   0.7021   |   0.7018   |   0.7023   |   0.7016   |
|        GPSPD         | **0.7253** | **0.7280** | **0.7290** | **0.7300** | **0.7298** | **0.7302** | **0.7295** | **0.7306** | **0.7289** |
|      GPSPL-1st       |   0.7318   |   0.7356   |   0.7369   |   0.7369   |   0.7361   |   0.7374   |   0.7388   |   0.7402   |   0.7364   |
|      GPSPL-2nd       |   0.7111   |   0.7117   |   0.7132   |   0.7119   |   0.7139   |   0.7137   |   0.7130   |   0.7136   |   0.7155   |
|    GPSPL-1st+2nd     | **0.7482** | **0.7513** | **0.7527** | **0.7534** | **0.7534** | **0.7529** | **0.7526** | **0.7544** | **0.7522** |

### Node clustering results (NMI)

|  Method(Proximity)  |  LINE  |  PTE   | GPSPL-author | GPSPL-paper |   GPSPL    | metapath2v | metapath2v++ | Deepwalk | GPSPD-author | GPSPD-paper |   GPSPD    |
| :-----------------: | :----: | :----: | :----------: | :---------: | :--------: | :--------: | :----------: | :------: | :----------: | :---------: | :--------: |
|  1-st order(local)  | 0.3015 |   NA   |    0.2609    |   0.0447    |   0.1049   |     NA     |      NA      |    NA    |      NA      |     NA      |     NA     |
| 2-nd order (global) | 0.2529 | 0.2634 |    0.2505    |   0.2403    | **0.3118** |   0.2403   |    0.2473    |  0.2873  |    0.1681    |   0.3392    | **0.3555** |
|    1st+2nd order    | 0.2516 |   NA   |    0.2607    |   0.1738    |   0.1894   |     NA     |      NA      |    NA    |      NA      |     NA      |     NA     |

