# SAP RAP Hotel Management Application

Welcome to the **SAP RAP Hotel Management Application** repository! 

This project is an educational example of a complete transactional application built with the **ABAP RESTful Application Programming Model (RAP)**. It is designed to help students, junior developers, and SAP enthusiasts understand how to implement a complex **Managed Scenario** from scratch.

## Project Overview
The application simulates a backend system for a hotel chain. It allows users to manage hotels, rooms, customers, and reservations. By exploring this repository, you will see how SAP RAP separates the database layer, the business logic, and the user interface.

## Key Features
This project demonstrates several fundamental and advanced SAP RAP capabilities:

* **Managed Scenario with Draft:** Includes autosave functionality (Draft tables) for a seamless and safe user experience.
* **Hierarchical Data Model (Composition Tree):**
  * `Hotel` 
  * `Rooms` & `Reservations` 
  * `Clients` & `Guests` 
* **Business Logic (Behavior Pool):**
  * **Validations:** Automatically validates logical reservation dates, email formats, DNI/Passports, and phone numbers.
  * **Determinations:** Automatically sets default values (like default city or status) and mathematically calculates the `TotalPrice`.
  * **Actions:** Custom buttons to interact with the data, such as `acceptReservation`, `rejectReservation`, `deductDiscount` (with a popup parameter), `outOfService` for rooms, and a factory action to `copyHotel`.
  * **Side Effects:** Real-time UI refreshes without reloading the page (e.g., updating the total price immediately when a discount or room changes).
* **Fiori Elements UI:** Uses **Metadata Extensions (MDE)** to define facets, columns, search filters, and drop-downs, keeping the UI completely decoupled from the backend data model.

## Repository Structure
* **Database Layer:** Transparent tables for persistence (e.g., `ZHOTEL`, `ZROOMS`) and their corresponding draft tables (e.g., `ZHOTEL_D`).
* **Core Data Services (CDS):**
  * *Interface Views* (`ZR_HOTEL`) establishing the base data model and associations.
  * *Projection Views* (`ZC_HOTEL`) exposing the data specifically for the UI consumption.
* **Behavior Definitions & Implementations:** The `BDEF` files and ABAP Classes (`ZBP_`) containing all the transactional logic (CUD operations, early numbering, validations).
* **Business Services:** Service Definitions and OData V4 Service Bindings used to expose the app to SAP Fiori.

---

## How to Import This Project (Using Eclipse & abapGit)
To easily download and install this project into your SAP system, you need to use the **abapGit** plugin for Eclipse. Follow these steps:

1. **Install abapGit Plugin:** Ensure you have the abapGit plugin installed in your ABAP Development Tools (ADT) in Eclipse.
2. **Create a Target Package:** In ADT, create a new local ABAP package (e.g., `ZRAP_HOTEL`) where you want to store all the imported objects.
3. **Open the abapGit View:** Go to `Window` > `Show View` > `Other...`, search for **abapGit Repositories**, and open it.
4. **Link the Repository:** Click the **+** icon (*Link abapGit Repository*) in the abapGit view.
5. **Provide the URL:** Paste the URL of this GitHub repository.
6. **Assign to Package:** Enter the ABAP package you created in Step 2, select the main branch, and click *Next* and *Finish*.
7. **Pull the Code:** Right-click the newly linked repository in the abapGit view and select **Pull...** to download the solution implementation into your system.
8. **Activate:** Once the pull is complete, select all the imported development objects and activate them together (`Ctrl+Shift+F3`).

Feel free to explore the code, copy snippets, and use it to build your own SAP RAP applications!

Happy coding and learning!
