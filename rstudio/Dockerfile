FROM 42n4/rstudio-dev:latest
RUN apt-get update && apt-get dist-upgrade -y  && apt-get install -y apt-utils
RUN apt-get install -y --no-install-recommends libssl-dev libssh2-1-dev zlib1g-dev
RUN install2.r  --deps TRUE \
    codetools   \
    devtools    \
    remotes     \
    e1071       \
    rpart       \
    rpart.plot  \
    lattice     \
    ipred       \
    cluster     \
    quadprog    \
    kernlab     \
    Matrix	\
    randomForest
RUN installGithub.r 42n4/dmr.data 42n4/dmr.util 42n4/dmr.claseval 42n4/dmr.stats 42n4/dmr.trans 42n4/dmr.linreg 42n4/dmr.regeval 42n4/dmr.dissim 42n4/dmr.dectree 42n4/dmr.linclas 42n4/dmr.disc 42n4/dmr.kcenters 42n4/dmr.cluseval
RUN installGithub.r 42n4/dmr.regtree 42n4/dmr.attrsel 42n4/dmr.ensemble 42n4/dmr.kernel 42n4/dmr.bayes 42n4/dmr.hierclus 42n4/dmr.miscost 42n4/dmr.rpartutil
RUN apt-get install -y --no-install-recommends default-jdk postgresql-9.6 postgresql-client-9.6 libmariadb-client-lgpl-dev postgresql-server-dev-9.6
RUN apt-get install -y --no-install-recommends libpcre3 libpcre3-dev lzma libbz2-dev liblzma-dev libicu-dev libmagick++-dev libpng-dev
#apt-get --yes --fix-broken install
RUN R CMD javareconf
RUN install2.r --deps TRUE \
    reshape	\
    sqldf	\
    dplyr	\
    party	\
    partykit	\
    rgl	 	\
    scatterplot3d\
    fpc		\
    pvclust	\
    dendextend	\
    nFactors	\
    FactoMineR	\
    RRF	    	\
    mclust	\
    gbm		\
    mda		\
    klaR	\
    tseries	\
    forecast	\
    sets	\
    arules	\
    doMC	\
    ranger	\
    TTR
RUN apt-get install -y tk8.5 libxml2-dev tk-dev
RUN installGithub.r 42n4/tkrplot
RUN install2.r --deps TRUE \
    ade4
RUN install2.r --deps TRUE \
    urca timeSeries fBasics
RUN installGithub.r 42n4/fUnitRoots
RUN apt-get install -y --no-install-recommends freeglut3 freeglut3-dev libglew-dev libglu1-mesa libglu1-mesa-dev libgl1-mesa-glx libgl1-mesa-dev
RUN install2.r --deps TRUE \
    rgl
RUN apt-get install -y --no-install-recommends texlive-luatex texlive-latex-base
RUN install2.r --deps TRUE \
    knitr filehash
RUN installGithub.r yihui/tikzDevice
RUN install2.r --deps TRUE \
    clusterGeneration	\
    nnet 	\
    neuralnet 	\
    RSNNS 	\
    rockchalk 	\
    fifer 	\
    h2o
#RUN installGithub.r topepo/caret/pkg/caret
RUN install2.r --deps TRUE \
    AppliedPredictiveModeling \ 
    fastAdaboost\
    rotationForest\
    rpartScore 	\
    adabag	\
    C50		\
    RWeka	\
    xgboost	\
    pROC	\
    DMwR	\
    ROSE	\
    Boruta	\
    Metrics 	\
    hydroGOF	\
    bartMachine \
    ada 	\
    bst		\
    deepboost	\
    evtree	\
    nodeHarvest	
RUN install2.r --deps TRUE \
    obliqueRF   \
    pbapply     \
    readbitmap  \
    Cairo       \
    downloader 
RUN installGithub.r dahtah/imager
RUN installGithub.r rstudio/reticulate
#RUN apt-get install -y --no-install-recommends libopencv-dev python-opencv
RUN apt-get install -y libopencv-dev python-opencv #netcdf hdf5
RUN installGithub.r swarm-lab/videoplayR
#RUN apt-get install -y python-rpy
#RUN installGithub.r gaborcsardi/pkgconfig
#RUN installGithub.r igraph/rigraph
RUN install2.r -r http://bioconductor.org/packages/3.5/bioc --deps TRUE \ 
    KEGGgraph \
    biomaRt
RUN install2.r --deps TRUE \
    mboost
RUN apt-get install -y python-numpy python-scipy python-matplotlib  python3-numpy python3-scipy python3-matplotlib
RUN apt-get install -y python3-opencv
RUN rm -rf /tmp/* \
#&& apt-get remove --purge -y $BUILDDEPS \
&& apt-get autoremove -y \
&& apt-get autoclean -y \
&& rm -rf /var/lib/apt/lists/*
## Clean up from R source install
#RUN cd / \
#  && BUILDDEPS="curl \
#    default-jdk \
#    libbz2-dev \
#    libcairo2-dev \
#    libcurl4-openssl-dev \
#    libpango1.0-dev \
#    libjpeg-dev \
#    libicu-dev \
#    libpcre3-dev \
#    libpng-dev \
#    libreadline-dev \
#    libtiff5-dev \
#    liblzma-dev \
#    libx11-dev \
#    libxt-dev \
#    perl \
#    subversion \
#    tcl8.5-dev \
#    tk8.5-dev \
#    texinfo \
#    texlive-fonts-extra \
#    texlive-extra-utils \
#    texlive-fonts-recommended \
#    texlive-latex-recommended \
#    x11proto-core-dev \
#    xauth \
#    xfonts-base \
#    xvfb \
#    zlib1g-dev" \
#latex for tikxdevice
