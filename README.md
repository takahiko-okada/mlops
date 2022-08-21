# MLOps

The purpose of MLOps is to solve the challenges in Machine Learning related projects. 

## ML usecases

- New product/capability
- Automation/assistance of existing manual tasks
- Replacement of existing ML system

## Life Cycle of Production ML project

1. Scoping
   1. Define Project
      1. Decide on key metrics
         1. Model Accuracy
         2. Latency
         3. Throughput(QPS, query-per-second)
         4. Cloud/Edge/Browser computing?
            1. Cloud
               1. flexible computing power
            2. Edge
               1. Lower latency
               2. Offline-processing (network-incident-proof)
         5. Real-time/Batch
         6. Logging
         7. Securiy
         8. Privacy
            1. e.g. patient record
      2. Estimate required resources and timeline

2. Data
   1. Defining the data and establishing the baseline
   2. Labeling & Organizing the data
      1. Data label consistency
         1. e.g. Audio transcribtion
            1. Um, today's weather/Um...today's weather/today's weather?
            2. Volume normalization
            3. silence before/after each audio clip?
   3. Validating the data
3. Modeling, Model Development
   1. Two types of AI/ML development
      1. Model centric (tends to be research and academia)
      2. Data centric (tends to be production system)
   2. Challenges in model development
      1. Doing well on training data set
      2. Doing well on dev/test data set
      3. Doing well on business metrics/project goals
   3. Inputs
      1. Code (algorithm/model)
      2. Hyperparameters
      3. Data
   * In Research/Academia, adjusting code/hyperparameters is reletively emphasized. 
   * In production system, focus is more on the data
- 
   2. Performing error analysis
      1. 
1. Deployment
   1. Deploying the model to production
      1. Gradual ramp up of traffice
      2. Rollback possibility
         1. ML System Deployment patterns
            1. Shadow deployment possiblity
               1. gradual replacement of manual process, by implementing ML system in parallel
               2. e.g 
You’ve built a new system for making loan approval decisions. For now, its output is not used in any decision making process, and a human loan officer is solely responsible for deciding what loans to approve. But the system’s output is logged for analysis.
            2. Canary deployment
               1. Small portion of a single process to be done by the ML system to avoid significant negative impact
            3. Blue-green deployment
               1. Old(Blue) New(Green)
               2. Let Blue version running and switch traffics to Green version (Gradual or all at once)
               3. quick rollback to previous version by keeping the Blue version 
      3. Recommended way is to gradually automate manuall process. Full automation to be reached after a certain maturity level is reached.
2. Monitoring
   1. Spotting data/concept drift
      1. e.g. Audio recognition ML project
         1. Users gets older and the voice changes => emotion detection may become inaccurate
   2. Spotting issues in data pipeline
   3. Pipeline monitoring
      1. if there are multiple ML models deployed as micro-service, then the output of ML model 1 affects the output of ML model 2 
   4. Methods
      1. Use Dashboard (most common)
        1. Software Metrics
            1. e.g. Traffic load monitoring
        2. Input metrics
           1. e.g. avg. audio length, image brightness, number of missing values
        3. Output metrics
           1. e.g. frequency of recognition error, inaccurate recommendation

3. Maintaining
   1. improving/fixing the model based on the new data coming in from the production environment 


## "ML Infrastructure"
- Configuration
- Data Collection
- Feature Extraction
- Data Verification
- Machine Resource Management
- ML Code
- Analysis Tools
- Process Management Tools
- Serving Infrastructure
- Monitoring

Ref. D.Sculley et al NIPS 205: Hidden Technical Debt in Machine Learning Systems

### Data Drift

is in short, input data distribution change (tendency changes)

https://towardsdatascience.com/machine-learning-in-production-why-you-should-care-about-data-and-concept-drift-d96d0bc907fb
https://christophergs.com/machine%20learning/2020/03/14/how-to-monitor-machine-learning-models/
https://youtu.be/06-AZXmwHjo

https://youtu.be/06-AZXmwHjo
http://arxiv.org/abs/2011.09926
https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf

### Concept Drift
X -> Y changes. The underlying theory changes.

e.g.  
- Light in a room changed, so that the photos taken are overall brighter, which hides the scratches on the objects. 



### ML Meta data

- Data Provenance


### Model Fairness

### Explainability issues


### "POC to Production Gap"
