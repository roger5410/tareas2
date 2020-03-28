# Investigation

## Describe the different data analysis architectures.

### Hadoop / MapReduce

#### MAPREDUCE is a software framework and programming model used for processing huge amounts of data. MapReduce program work in two phases, namely, Map and Reduce. Map tasks deal with splitting and mapping of data while Reduce tasks shuffle and reduce the data.

#### Hadoop is an open source software framework for storing data and running applications on commercial hardware clusters. It provides massive storage for any type of data, enormous processing power and the ability to process virtually unlimited concurrent jobs or tasks.

### Bases de datos NoSQL

#### When we talk about NoSQL databases, also known as “Not only SQL”, we are referring to a wide class of data management systems (mechanisms for data storage and retrieval) that differ, in important respects, from the classic relationship model. between entities (or tables) existing in relational database management systems, the most prominent being that which does not use SQL as the main query language.

### SGBDR Extendidos

#### A relational database management system (RDBMS) is a program that allows you to create, update, and manage a relational database. Most commercial RDBMS use the structured query language (SQL) to access the database, although SQL was invented after the development of the relational model and is not necessary for its use, since they are an extended part of the systems. common.


## characteristics of a data center.

#### 1.Security: Data is the fundamental support of any business model in the modern era, so ensuring the security of information is one of the main priorities of companies. On the one hand, it is necessary to take into account the protection measures that will be implemented in the physical environment. In this sense, the access control measures (identification cards, biometrics, etc.) stand out so that only authorized personnel can contact the data center. On the other hand, it is essential to have protection tools such as data encryption. , either by hardware or by software, as well as security solutions against the loss of information and / or corruption in power failures.

#### 2. Cooling: Achieving an ideal temperature environment is also a very important point in order to obtain the best possible performance from the data center. Since it must be in continuous operation, it is essential to establish an optimal cooling system to avoid that high temperatures adversely affect the performance, efficiency and useful life of the components. In this scenario, it is necessary to emphasize that the refrigeration system should not only focus on reducing heat and maintaining optimal operating temperatures, but it should also control humidity levels.

#### 3. Storage Capacity: As larger amounts of data are being generated, companies demand storage solutions with higher capacities. Thanks to technological advancement, companies have at their disposal storage units (either conventional hard drives or solid state drives) that have increasingly higher capacities that allow this high volume of information to be stored without problems.

#### 4. Data transfer: Storage capacity is useless if it cannot be accessed quickly. In this sense, it is essential that the data transfer (in reading or writing) occurs quickly, since this way we promote accessibility to information. Likewise, it is essential that there is an optimal level of information transmission speed between the data center and the rest of the devices is optimal.


## Cloud and Fog data analysis features

#### Scalability and elasticity: your computing resources will not be limited to a static capacity. With this functionality of cloud platforms, your systems will adapt to the load they are being subjected to, so the storage or computing capacity of your application will not be exhausted.

#### Independence between device and location: Equipment and tedious data center rooms are no longer needed. Cloud computing is characterized by the provision of administration consoles and multiple work environments that can be accessed through a mobile device, your favorite code editor or on your computer, regardless of where you are. located.

#### Security: In cloud computing, security is just as good and can even outperform traditional systems. This is, in part, because providers are able to dedicate resources to solving security issues that many customers cannot afford to address. The cloud user is responsible for security at the application level. The cloud provider is responsible for physical security.

#### Cost: costs are greatly reduced. A cloud server converts capital expenditures into operating expenses, which results in lower barriers to entry, as the infrastructure is typically provided by a third party and does not have to be purchased once or for tasks. infrequent intensive computing.

#### Performance: performance is a key part of this technological model, since all the resources are available to optimize the final result. Multiple integrations are created so that the user is able to constantly monitor and implement corrections that allow obtaining even more capacity from the same resources.

#### Maintenance: In the case of cloud computing applications, this process is reduced to the allocation of trained personnel to handle monitoring services. The platform will take care of the rest, since the maintenance to the systems can be configured to happen automatically. This reduces implementation times resulting in a focus on software production.


## data engineering
#### its importance is crucial, since it is the phase in which we prepare the data for the subsequent phase, the analytical one. Data engineering comes to establish the standards that any company needs to have its data in a unified, clean and accessible way, responding to the requirements of each business.

## Define the concepts of data acquisition, management, process and administration.

### data management

#### Data management is the practice of collecting, maintaining and using data in a safe, efficient and cost-effective manner. The goal of data management is to help people, organizations, and connected objects optimize the use of data within the limits of policy and regulations so that they can make decisions and take actions that maximize the benefit to the data. organization. A robust data management strategy is more important than ever, as organizations increasingly rely on intangible assets to create value.

### data processing

#### Data processing occurs when data is collected and translated into usable information. Data scientists are often involved, alone or in teams, and it is important that the processing is done correctly so as not to adversely affect the final product or the results obtained from the data.

#### Processing begins with data in its raw form and converts it to a more readable format (graphics, documents, etc.), giving it the form and context necessary for computers to interpret and use by employees across an organization.

### Data acquisition

#### Acquiring the data is determining which of them are available. We must spare no effort in researching the appropriate data sources. We want to identify the appropriate data related to our problem and take advantage of all the data that is relevant to the analysis of the problem. Omitting only a small amount of important data can lead to incorrect conclusions.

## Describe the Lambda and Kappa architectures and Describe the layers of each architecture

### Lambda architecture

#### The Lambda Architecture represented by the Greek letter, appeared in 2012 and is attributed to Nathan Marz. He defined it based on his experience in distributed data processing systems during his time as an employee in the Backtype and Twitter companies, and is inspired by his article How to beat the CAP theorem.

#### Their goal was to have a robust fault-tolerant system, both human and hardware, that was linearly scalable and that allowed low-latency writes and reads.

#### The data entering the system is dispatched to both the batch layer and the speed layer. The batch layer writes the data to the master data set and prepares the batch views, passing them to the server layer. The latter is in charge of indexing the batch views so that it can respond to searches with very low latency. The problem is that the process of writing data and then indexing it is slow, so it is not available instantly; this is where the role of the speed layer comes into play; which is dedicated to exposing only the most recent data, without worrying about writing it to a permanent record. The result of any search can bring together data from both batch layer and velocity layer views.

### Kappa architecture

#### The idea is to handle both real-time data processing and continuous reprocessing in a single stream processing engine. That’s right, reprocessing occurs from the stream. This requires that the incoming data stream can be replayed (very quickly), either in its entirety or from a specific position. If there are any code changes, then a second stream process would replay all previous data through the latest real-time engine and replace the data stored in the serving layer.

#### This architecture attempts to simplify by only keeping one code base rather than manage one for each batch and speed layers in the Lambda Architecture. In addition, queries only need to look in a single serving location instead of going against batch and speed views.

#### The complication of this architecture mostly revolves around having to process this data in a stream, such as handling duplicate events, cross-referencing events or maintaining order- operations that are generally easier to do in batch processing.

## Contrast the advantages and disadvantages of each big data architecture with respect to incremental architectures.

#### Fully incremental architectures present problems such as compaction, high consistency of highly available data and lack of tolerance to human failures that require complex solutions, using the Lambda architecture achieves solutions with higher performance and avoiding complexity.

#### One of the problems of fully incremental architectures that can be solved without a total change of architecture is that of tolerance to human failure, this is achieved through the use of a store of immutable events, which we call fully incremental architecture with registration, this works for both synchronous and asynchronous architectures. Although human fault tolerance is fixed, the fully incremental architecture with registration fails to solve the other complexities or problems. The Lambda architecture presents a better solution to this type of problem.

