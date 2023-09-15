#dbms #research #projectReport #todo 

## To-Do:

- [x] Sale Invoice Generate->Drafting ->Save invoice
- [ ] Show updated Drug in stock
- [x] Show all saleinvoices from admin.
- [ ] Requirement Collection and analysis.
### Abstract

The main aim of this paper are the design and implementation of a pharmaceutical inventory database management system. The system was implemented by creating a database containing information about the stored medicines in the inventory, customers making transactions with pharmaceutical trading company, medical suppliers, employees, payments etc. The database was connected to the main application using php. The proposed system should help in manag inginventory operations which include adding/updating employees’ information,
preparing sale and purchase invoices, generating reports, adding/updating customers and suppliers, checking expired medicines in order to be disposed. The system can be used to facilitate smooth workflow of sale and purchase operations and bring the advantages of having efficient control with minimal efforts.

**Final Version**
This paper focuses on designing and implementing a pharmaceutical inventory database management system. The system incorporates a comprehensive database encompassing information about stored medicines, employees, customer transactions, suppliers and more, with integration into the main application using PHP. The proposed system should help in inventory operations including employee management, invoice generation, reporting, customer and supplier management, and identifying expired medicines. Ultimately, the system aims to improve efficiency in sales and purchase workflows, offering effective control with minimal administrative effort.

### Introduction
#### paper 02
1. Introduction
Inventory management is one of the essential problems in almost every company. Before computer age and integration, paper solutions were used as inventory management tools. If there is no automated system available, these solutions may cause a lot of paperwork and usually lead to mistakes as the workload increases since it deals with more than hundreds of medications. The company needs to use a new technology to keep track of all its transactions and day-to-day operations to achieve its business goals by introducing a computer-based system. Designing and Implementing such a system is possible but there is preliminary work such as studying the operational environment and needs of the company, identifying the requirements, determining software tools, designing system database and developing the user interface application (Taner Arsan, 2013).
For the company, it is important to ensure that there is sufficient quantity of medications to serve the needs of the customers. In addition, careful inventory management can increase the company earnings. A badly managed inventory may have more loss through medications expiring, incorrect accounting and inappropriately recorded returns than a well-managed inventory (Katie Ingersoll, 2015).
In order to provide an overview of previous work, some researchers presented by various authors are reviewed:
(Toshio Awaya et al., 2005) developed a control system application named Artima which allows inventory tasks to be faster and more efficient in real world. The medicines used in the hospital (where the system is applied) were automatically fixed and arranged in sold -packages and ordered from each wholesaer every day. This system can search the quantities available and expiration date of each drug in the purchase and delivery records. They find that the system
#### My version
1. In today's rapidly evolving pharmaceutical industry, efficient inventory management stands as a cornerstone for the success of pharmaceutical businesses. The pharmaceutical sector is characterized by its dynamic nature, with constant demands for new products, strict regulatory requirements, and the imperative to ensure product safety and efficacy. In this context, the effective tracking and management of pharmaceutical inventory play a pivotal role in maintaining the delicate balance between supply and demand, ultimately impacting patient care and organizational success.

The project at hand, "MediTracker: A Pharmaceutical Inventory Management System," emerges as a response to the pressing need for modernized and streamlined inventory control solutions in the pharmaceutical landscape. This paper delineates the design, implementation, and impact assessment of MediTracker, an innovative and comprehensive pharmaceutical inventory database management system.
2. Inventory management is a critical concern for most companies, and in the past, paper-based solutions were used, leading to paperwork and errors as the workload increased, particularly when dealing with numerous medications. To address these challenges and achieve business objectives, companies are increasingly adopting computer-based inventory management systems. Implementing such a system involves preliminary steps such as assessing the operational environment, identifying requirements, selecting software tools, designing the system's database, and developing the user interface.

Effective inventory management is crucial for ensuring an adequate supply of medications to meet customer needs and maximizing company earnings. Poorly managed inventory can result in losses due to expired medications, inaccurate accounting, and mishandled returns.

Previous research by various authors offers insights into inventory management:
- Toshio Awaya et al. (2005) developed Artima, a control system application that enhances the efficiency of inventory tasks. It automatically organizes medicines in hospitals into saleable packages and manages daily orders from wholesalers. This system also tracks available quantities and expiration dates of drugs in purchase and delivery records.

(Note: The summary captures the key points of the introduction, but it is advisable to continue summarizing the remaining sections for a comprehensive overview of the paper.)
#### Final Version-
In today's rapidly evolving pharmaceutical industry, efficient inventory management stands as a cornerstone for the success of pharmaceutical businesses. The pharmaceutical sector is characterized by its dynamic nature, with constant demands for new products, strict regulatory requirements, and the imperative to ensure product safety and efficacy. In the past, paper-based solutions were used, leading to paperwork and errors as the workload increased, particularly when dealing with numerous medications. To address these challenges and achieve business objectives, companies can adopt computer-based inventory management systems. Implementing such a system involves preliminary steps such as assessing the operational environment, identifying requirements, selecting software tools, designing the system's database, and developing the user interface. 

The project at hand, "MediTracker: A Pharmaceutical Inventory Management System," emerges as a response to the pressing need for modernized and streamlined inventory control solutions in the pharmaceutical landscape. This paper delineates the design, implementation, and impact assessment of MediTracker, an innovative and comprehensive pharmaceutical inventory database management system.

### objectives
The intended system aims to accomplish the following objectives:
- Add/update system users and pharmacy employees.
- Create sale and purchase invoices efficiently.
- Generate various reports as needed.
- Monitor and manage customer payments.
- Identify expired medicines for proper disposal.

### Database of  choice
In this project, we have decided to use a relational database management system (RDBMS). The relational database model serves as the foundation for many widely utilized databases. RDBMS is frequently selected as the preferred option for storing data in newly created databases, including financial records, manufacturing and logistics data, personnel records, and various other applications (Thomas M. Connolly, 2014). The specific RDBMS chosen for this project is MySQL.
### Logical database design





