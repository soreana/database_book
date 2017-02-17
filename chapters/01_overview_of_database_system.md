# Overview of Database System

## Definitions

* **Database** : 

    is collection of data, typically describing the activities of one or more related organizations.

* **DBMS** : 

    or database management system, is software designed to assist in maintaining and utilizing large collections of data.
    
* **Level Of Abstraction** : 

    The gap between how users think of their data and how the data is ultimately stored is bridged through several 
    levels of abstraction supported by the DBMS.
    
    
* **Schema** : 

    A description of data in terms of a data model is called a schema. In the relational model, the schema for a 
    relation specifies its name, the name of each field (or attribute or column), and the type of each field.
    
    * **Conceptual Schema** :
    
        The conceptual schema (sometimes called the logical schema) describes the stored data in terms of the data model 
        of the DBMS. In a relational DBMS, the conceptual schema describes all relations that are stored in the database.
        For example in university DBMS, relations contain information about entities, such as students and faculty, and 
        about relationships, such as students enrollment in courses.
    
    * **Physical Schema** :
    
        The physical schema specifies additional storage details. Essentially, the physical schema summarizes how the 
        relations described in the conceptual schema are actually stored on secondary storage devices such as disks and 
        tapes. A sample physical schema for the university database follows:
        
        - Store all relations as unsorted files of records.
        
        - Create indexes \coloredtext{red}{TODO reference to it's definition} on the first column of the Students, Faculty, and Courses relations, the sal column of Faculty, and the capacity column of Rooms.
        
    * **External Schema**
    
        External schemas, which usually are also in terms of the data model of the DBMS, allow data access to be customized
        (and authorized) at the level of individual users or groups of users.
         
        Any given database has exactly one conceptual schema and one physical schema because it has just one set of stored 
        relations, but it may have several external schemas, each tailored to a particular group of users.
        
        Each external schema consists of a collection of one or more views and relations from the conceptual schema.
        
        A view is conceptually a relation, but the records in a view are not stored in the DBMS. Rather, they are computed 
        using a definition for the view, in terms of relations stored in the DBMS. 
        
        A user can treat a view just like a relation and ask questions about the records in the view.
    

* **Record** : 

    Each row in the Students relation is a record that describes a student.

|**sid** | **name** | **login** | **age** | **gpa** |
|--------|----------|-----------|---------|---------|
| 53666 | منگول | mangul@shangulabad.com | 18 | 3.5 |
| 53686 | شنگول | shangul@shangulabad.com | 17 | 3.2 |
| 53662 | حبه انگور‍ | habbeAngura@shangulabad.com | 13 | 2.8 |
| 53659 | مامان بزی | mamanBozi@shangulabad.com | 24 | 3.9 |
| 53646 | بابا بزی | babaBozi@shangulabad.com | 28 | 1.4 |


* **Integrity Constraints** : 

    Integrity constraints, which are conditions that the records in a relation must satisfy.

* **Data Model** : 

    A data model is a collection of high-level data description constructs that hide many low-level storage details. 
    A DBMS allows a user to define the data to be stored in terms of a data model.
    
* **Semantic Data Model** :

    A semantic data model is a more abstract, high-level data model that makes it easier for a user to come up with a 
    good initial description of the data in an enterprise. These models contain a wide variety of constructs that help 
    describe a real application scenario. A DBMS is not intended to support all these constructs directly; it is 
    typically built around a data model with just a few bi:1Sic constructs, such as the relational model. A database 
    design in terms of a semantic model serves as a useful starting point and is subsequently translated into a database 
    design in terms of the data model the DBMS actually supports.
    A widely used semantic data model called the entity-relationship (ER) model allows us to pictorially denote entities 
    and the relationships among them.
    
* **Relation**:

    relation, which can be thought of as a set of records.

* **Data Definition Language**:

    or DDL is used to define the external and conceptual schemas.
    
* **
    
## Files vs DBMS

We can try to manage the data by storing it in operating system files. This approach has many drawbacks, including the 
following:

* We probably do not have 500 GB of main memory to hold all the data. We must therefore store data in a storage device 
such as a disk or tape and bring relevant parts into main memory for processing as needed.

* Even if we have 500 GB of main memory, on computer systems with 32-bit addressing, we cannot refer directly to more 
than about 4 GB of data. We have to program some method of identifying all data items.

* We have to write special programs to answer each question a user may want to ask about the data. These programs are 
likely to be complex because of the large volume of data to be searched.

* We must protect the data from inconsistent changes made by different users accessing the data concurrently. If 
applications must address the details of such concurrent access, this adds greatly to their complexity.

* We must ensure that data is restored to a consistent state if the system crashes while changes are being made.

* Operating systems provide only a password mechanism for security. This is not sufficiently flexible to enforce security 
policies in which different users have permission to access different subsets of the data.

## Advantage of DBMS

* **Use DBMS when you care about** :
    * **Data Independence**: 
    
        Application programs should not, ideally, be exposed to details of data representation and storage, The DBMS 
        provides an abstract view of the data that hides such details.
        
    * **Efficient Data Access**:
    
        A DBMS utilizes a variety of sophisticated techniques to store and retrieve data efficiently. This feature is 
        especially important if the data is stored on external storage devices.

    * **Data Integrity and Security**:
    
        If data is always accessed through the DBMS, the DBMS can enforce integrity constraints. For example, before 
        inserting salary information for an employee, the DBMS can check that the department budget is not exceeded. 
        Also, it can enforce access controls that govern what data is visible to different classes of users.
        
    * **Data Administration**:
    
        When several users share the data, centralizing the administration of data can offer significant improvements. 
        Experienced professionals who understand the nature of the data being managed, and how different groups of users 
        use it, can be responsible for organizing the data representation to minimize redundancy and for fine-tuning the 
        storage of the data to make retrieval efficient.

    * **Concurrent Access and Crash Recovery**:
    
        A DBMS schedules concur- rent accesses to the data in such a manner that users can think of the data as being 
        accessed by only one user at a time. Further, the DBMS protects users from the effects of system failures.
    
    * **Reduced Application Development Time**:
    
        Clearly, the DBMS sup- ports important functions that are common to many applications accessing data in the DBMS. 
        This, in conjunction with the high-level interface to the data, facilitates quick application development. DBMS 
        applications are also likely to be more robust than similar stand-alone applications because many important tasks 
        are handled by the DBMS (and do not have to be debugged and tested in the application).
        
* **Don't use DBMS when** :

    * performance may not be adequate for your specialized applications.
    
    * your application may need to manipulate the data in ways not supported by the query language.




## I don't know where put these :)

* Information about the conceptual, external, and physical schemas is stored in the system catalogs

* While the data model of the DBMS hides many details, it is nonetheless closer to how the DBMS stores data than to how 
 a user thinks about the underlying enterprise. A semantic data model is a more abstract, high-level data model that 
 makes it easier for a user to come up with a good initial description of the data in an enterprise. These models contain
 a wide variety of constructs that help describe a real application scenario. A DBMS is not intended to support all these
 constructs directly; it is typically built around a data model with just a few bi:1Sic constructs, such as the 
 relational model. A database design in terms of a semantic model serves as a useful starting point and is subsequently
 translated into a database design in terms of the data model the DBMS actually supports.

* A widely used semantic data model called the entity-relationship (ER) model allows us to pictorially denote entities 
and the relationships among them.
