# Open Standards for WordPress in Healthcare

<br />

```
Disclaimer: Code review of the WordPress code base and/or other security measures, such as vulnerability assessment and
penetration testing, should be done to ensure security of sensitive and privacy-related applications, like healthcare
applications. If the data controller or covered entity does not have direct access or control of the application source
code, application server or data management server, the data controller or covered entity must have a data processing
or business associate agreement with the data processor or business associate.
```

<br />

The Open Standards for WordPress in Healthcare aims to standardize application development in healthcare using WordPress content management system as application development platform. These standards go beyond the use of the content management system as a tool for creating informational or brochure-type websites or blogging, and extends to mission critical operation applications.

The standards focus on WordPress application development where there are multiple users with varying access level permissions to different types of content. Use of these open standards can be extended beyond the field of nursing – to other fields of healthcare service.


## Scope

The Open Standards for WordPress in Healthcare focuses on four (4) main aspects of application development – data management, data presentation, security and user access levels. The standards will guide healthcare professionals on how they will define, store and manipulate data in the database; how these stored data can be presented using codes or plugins; allowing limited user access to the dashboard and admin bar for security; and how to provide user access privileges using the default settings.

<br />

```
Title: Open Standards for WordPress in Healthcare
Version: v1.1
Initial Publication: March 14, 2018
Revised Publication: March 25, 2021
``` 

<br />

### Section 1. <em>Custom Post Type</em> - Data shall be defined as a custom post type. 

Most, if not all, healthcare web applications are database-driven applications. Database design usually dictates that data entries of different types should be stored in different tables to give structure and improve query performance. As an example, there should be one table for the list of patients and custom fields, a separate table for clinic or hospital visits, and another table for doctors or care providers and associated attributes.

WordPress was initially designed and developed as a blogging platform. Thus, every data entry revolves around posts. The integration of custom post types in WordPress core gave flexibility to support not just posts and pages, but other entities as well, such as patients, hospital or clinic visits, care providers, and the likes. To maintain compatibility, these data entries are stored and defined in the same table – the posts table.

If the data concerned is a news update, a blog post, or an entry of that nature, it can be defined as a post type of “Post” . However, medical information that is not considered a news update or blog post should not be defined as a post type of “Post” and categorized using taxonomies. These entries should be registered as custom post types.

<br />

### Section 2. <em>Custom Fields</em> - Custom data fields shall be defined as post meta fields.
  
Instead of creating additional table columns in the posts table, WordPress utilizes the postmeta table to extend data fields using metadata or custom fields, such as age, sex, date of admission, reason for admission, physician, and the likes. These metadata point to a particular post entry which is defined by the custom post type – patient, visit, or doctor for example.

There are methods and plugins that would allow the inclusion of custom fields as separate columns in a custom table, instead of the postmeta table. Though the accepted WordPress development ecosystem favors the use of the postmeta table to extend attributes and store entry fields through metadata, storing custom fields in a separate table for each custom post type may improve query performance and speed, and ease in creating reports using the stored data. One drawback with this data structure though is that the system being developed may work with plugins compatible with custom post types (as long as data is still defined as a custom post type), but not integrate well with plugins that map custom fields as metadata in the postmeta table.

<br />

### Section 3. <em>Access Level</em> - Default or custom user roles and capabilities shall be used to grant data access.
 
As a platform initially created for blogging, the WordPress admin dashboard was designed for the interaction between contributors/authors and editors/publishers. The administrative area revolves around content creation, editing and publishing. For security reasons and to have a smooth user experience that extends outside the realm of blogging, ideally, all data entry and modification by regular users should be done in the front-end. There are plugins available to achieve this functionality. Advanced developers can also use custom codes to lock these administrative features for administrator access only. If the project calls for regular user access to the administrative area, such as when modifying profile settings, only limited access should be allowed to avoid potential security issues.

The developer has the option to manually code the form layout in the front-end, or use plugins to create submission forms and edit fields. The decision of whether to use manual coding or plugins to restrict or limit regular users from accessing the dashboard, admin bar, and other administrative interface features depends on project management and security measures instituted.

For security reasons and to adhere to default WordPress settings and installation, users, roles or user groups, access levels and capabilities should be based on default WordPress settings.

User attributes can be extended using custom fields. Roles can be created and extended, with capabilities added or removed. These roles need to be in the default settings and not dependent on third-party plugins using different database structure. It may be possible though for plugins to have their own set of roles or groups, but these have to be synchronized with the default WordPress roles to adhere to this standard.

<br />

### Section 4. <em>Application Programming Interface (API)</em> - Default Representational State Transfer (REST) API shall be used for system interoperability.

Healthcare systems connecting to a WordPress-based health IT system should use the default or built-in REST API to communicate with the WordPress-based system. There is the option though to use a more standardized approach, like HL7 FHIR. However, the JavaScript Object Notation (JSON) format of information exchange provided for by WordPress-based systems can be considered a JSON-based standard for interoperability.

<br />

### Section 5. <em>Modular Extensibility</em> - Modular extensibility of features and functionalities shall be done through plugins.

Adding features and functionalities to WordPress-based healthcare applications should not involve modifying WordPress core files or configurations. Instead, plugins should be created to further expand the features and functionalities of these applications.

<br />

## Collaborators

### v1.0

Raymund John Ang - Project Lead, Open-NIS; Registered Nurse, Pennsylvania, USA

Jai Ganesh Udayasankaran - Member, Governing Committee, AeHIN; Senior Manager, Health Care Information Technology and Telehealth Sri Sathya Sai Central Trust, India

Hussein Catanyag - Clinical Instructor, College of Nursing, Manila Tytana Colleges (Manila Doctor’s College of Nursing), Philippines

Dr. Mean Reatanak Sambath - Executive Director, Partnership for Better Health, Cambodia

Dr. Pornchai Chanyagorn - Faculty of Engineering, Mahidol University, Thailand

<br />

## References

Brazell, A. (2011). WordPress Bible (2nd ed.). Indianapolis, IN: Wiley Publishing Inc.

Lefebvre, Y. (2012). WordPress Plugin Development Cookbook. Birmingham, UK: Packt Publishing.

Messenlehner, B., & Coleman, J. (2014). Building Web Apps with WordPress: WordPress as an Application Framework. Sebastopol, CA: O’Reilly Media Inc.

McGonigle, D., & Mastrian, K. G. (2017). Nursing Informatics and the Foundation of Knowledge (4th ed.). Burlington, MA: Jones & Bartlett Learning.

McLean, A. (2015). Open-source software. Canadian Journal of Nursing Informatics, 10(3).

Onishi, A. (2014). Pro WordPress Theme Development. New York, NY: Apress.

Ratnayake, R. N. (2017). WordPress Web Application Development (3rd ed.). Birmingham, UK: Packt Publishing.

Williams, B., Damstra, D., & Stern, H. (2015). Professional WordPress: Design and Development (3rd ed.). Indianapolis, IN: John Wiley & Sons, Inc.
