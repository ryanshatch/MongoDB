<hr>

<h2><b>MongoDB Dashboard GUI   |  Austin Animal Center Outcomes</b><br><br></h2>

The MongoDB Dashboard is a web application developed to support the organization in managing and analyzing data related to animal shelters and rescue operations. 
<br>
> `Austin Animal Center's 2020 Outcomes` was used to build this applications database.<br> 

This Dashboard helps the users to be able to interact with data stored in the MongoDB. It also helps to visualize the queries and parsed data by using data filtering, pie charts, and geolocation mapping.
<br>
All built on the Dash framework, the GUI was designed to be easy for the user to use, maintain, and even add more functionality and develop ontop of the current programs GUI Dashboard.

<!-- --- -->
<hr>

### 1. **Core Functionality**

- **Interactive Data Table**: Users can `view, filter, and interact with data` from the MongoDB database within a dynamic table format.
- **Geolocation Mapping**: The dashboard features `a map that shows the location` of a selected animal that is based on the data that is shown in the table.<br>
  > Water Rescue, Mountain Rescue, Disaster, or Individual Tracking.
- **Data Visualization**: `A pie chart` that dynamically updates based on the filtered or selected data, and displays the distribution of the animal breeds with percentages.

### **GUI Interaction Examples:**

- [Screenshot 1: Water Rescue](Water_Rescue.JPG)
- [Screenshot 2: Mountain or Wilderness Rescue](Mountain_or_Wilderness_Rescue.JPG)
- [Screenshot 3: Disaster or Individual Tracking](Individual_Tracking_to_Find_A_Black_Lab.JPG)
- [Screenshot 4: Reset all to unfiltered](GUI.JPG)

<!-- --- -->
<hr>

### 2. **Tools Used and Justification**

#### **1. MongoDB:**
   - **Why MongoDB?**
     - MongoDB was chosen for its flexibility and scalability as the data model for this project. Its document-based NoSQL structure is very effective for parsing through large amounts of semi-structured data, which worked flawlessly for managing the animal records in this project. MongoDB also can be powerful when utilizing other languages to help parse data. For example, with Python you can fluently integrate the MongoDB connections by using the PyMongo library. This design allowed for not only a very efficient and flexible data model with tailored operations and functions, but also a very easy method to connect graphically to the data using the Dash framework.
   - **Key Features:**
     - **Flexible Schema**: MongoDB's schema-less design helps to easily add and modify fields without the need for any complex migrations.
     - **Aggregation Framework**: MongoDB's aggregation pipeline supports advanced data analysis directly within the database, which reduces the need for any additional data processing in Python.

#### **2. Dash Framework:**
   - **Why Dash?**
     - Dash was picked for building the web application because it works well when intigrated with Python, making it easier to create data-driven web apps with less time spent coding and development. It also handles the structure for both the view and controller parts of the app, using helpful components like `html`, `dcc`, and `dash_table` that make adding interactive features more straightforward.
   - **Key Features:**
     - **Python Integration**: Dash helps developers to build entire applications using only Python, which in turn gets rid of the need for many additional frontend languages like JavaScript.
     - **Component Library**: Dash offers a fairly rich library full of pre-built components like graphs, tables, and maps- all of which are easy to customize.
     - **Reactivity**: Dash's callback system supports automatic updates to the web application in response to users inputs or any data changes.

#### **3. Additional Tools:**
   - **Pandas**: I used Pandas for handling and transforming data. It provided me with powerful structures like DataFrames, which in turn helped to make it much easier to filter, sort, and adjust the data.
   - **Plotly**: This was integrated with Dash to create interactive and dynamic charts, like the pie chart used in this project.
   - **Dash Leaflet**: This tool added geo-location mapping functionality, which added an interactive map that displays right within the GUI/ Dash application.
   - **JupyterDash**: Using JupyterDash made it easier to develop the dashboard within a Jupyter notebook, which in the end was very helpful to streamline the process of iteration and testing.

<!-- --- -->
<hr>

### 3. **Project Steps**

1. **Data Import and Database Setup**:
   - Imported animal data into MongoDB using the `mongoimport` tool.
   - Developed the CRUD module and configured the `AnimalShelter` class to interact with MongoDB which holds the methods for reading, parsing, and querying the data.

2. **Dashboard Development**:
   - Designed the dashboard layout using Dash components, including the data table, pie chart, and map.
   - Developed callback functions to handle user inputs and dynamically update the data table, pie chart, and map accordingly.

3. **Testing and Debugging**:
   - Tested the dashboard to make sure that all components function correctly, which included data filtering, chart updates, and the map rendering.
   - Resolved issues related to data visualization, making sure that the pie chart displays data clearly for the user by adding more priority to the styling and layout of the components used in the graphical user interface.

4. **Deployment**:
   - The last step was to redeploy the dashboard and run a final test to double check that everything was working as I expected. I checked the performance of the application, along with its MongoDB integration and the graphical outputs, to make sure everything functioned smoothly in the production environment. 
      > *Note:* verifying that the dashboard fully utilized the CRUD functions from my Python module was critical for the final deployment to be fully functional.

<!-- --- -->
<hr>

### 4. **Challenges and Solutions**

1. **Pie Chart Display Issues**:
   - **Challenge**: The pie chart initially appeared cluttered, with extremely small sections and overlapping labels. It also had a 3D blur effect for any of the animals that were not in the top 5 breeds which made it hard to read and understand the data in the chart.
   - **Solution**: I carefully adjusted the chart size and label font size using Plotly’s layout options, and used the `fig.update_traces` and `fig.update_layout` methods to enhance the pie chart’s readability. 
     > *Note:* Subtle or simple changes to the UI always make a big difference on the final result.

2. **Database Connection Errors**:
   - **Challenge**: I experienced connection issues with MongoDB, especially during the early development stages in the Apporto environment.
   - **Solution**: Verified that the MongoDB server was running and accessible, and double checked the users and the permissions to make sure that the connection was properly configured. I ended up re-adding the user 'aacuser' and gave it the correct permissions to the 'AAC' database, which resolved the connection issues.

3. **Data Filtering Logic**:
   - **Challenge**: It was fairly complicated to correctly implement the data filtering logic to dynamically update the data table, pie chart, and map based on user inputs.
   - **Solution**: I used MongoDB’s aggregation framework to run advanced queries, allowing the dashboard to filter data based on the criteria selected by users.

<!-- --- -->
<hr>

### 5. **Resources**

#### **Data For Database:**
- **Data Set: Austin Animal Center Outcomes Spreadsheet**: [aac_shelter_outcomes.csv](aac_shelter_outcomes.csv)
  <!-- - Reference: Austin Animal Center. (2020). Austin Animal Center Outcomes [Data set]. City of Austin, Texas Open Data Portal. https://doi.org/10.26000/025.000001 -->
  ---
#### **Python Guides:**
- **Head First Python**: [https://go.oreilly.com/SNHU/library/view/head-first-python/9781491919521/](https://go.oreilly.com/SNHU/library/view/head-first-python/9781491919521/)
- **Style Guide for Python Code**: [https://www.python.org/dev/peps/pep-0008/](https://www.python.org/dev/peps/pep-0008/)
  <!---->
  ---
#### **Documentation:**
- **MongoDB Documentation**: [https://docs.mongodb.com/](https://docs.mongodb.com/)
- **Dash Documentation**: [https://dash.plotly.com/](https://dash.plotly.com/)
- **Plotly Documentation**: [https://plotly.com/python/](https://plotly.com/python/)
- **PyMongo Documentation**: [https://pymongo.readthedocs.io/](https://pymongo.readthedocs.io/)

<!-- --- -->
<hr>

## Queries and Terminal Outputs For Data Indexing and Authentication For New User:

```bash
(base) ryanhatch_snhu@nv-snhu8-l01:~$ mongosh
Current Mongosh Log ID:	669a1a3d79ceedbef9fd753b
Connecting to:		mongodb://<credentials>@nv-desktop-services.apporto.com:31692/?directConnection=true&appName=mongosh+1.8.0
Using MongoDB:		6.0.13
Using Mongosh:		1.8.0

For mongosh info see: https://docs.mongodb.com/mongodb-shell/

------
   The server generated these startup warnings when booting
   2024-07-19T06:54:08.308+00:00: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine. See http://dochub.mongodb.org/core/prodnotes-filesystem
   2024-07-19T06:54:10.423+00:00: Failed to read /sys/kernel/mm/transparent_hugepage/defrag
   2024-07-19T06:54:10.423+00:00: vm.max_map_count is too low
------

test> show dbs
AAC       2.83 MiB
admin   100.00 KiB
city     10.50 MiB
config  108.00 KiB
enron     7.55 MiB
local    72.00 KiB
test> db.animals.createIndex({ breed: 1 });
breed_1
test> db.animals.find({ breed: "Labrador Retriever" }).explain("executionStats");
{
  explainVersion: '1',
  queryPlanner: {
    namespace: 'test.animals',
    indexFilterSet: false,
    parsedQuery: { breed: { '$eq': 'Labrador Retriever' } },
    queryHash: '17252B62',
    planCacheKey: '8F94FD79',
    maxIndexedOrSolutionsReached: false,
    maxIndexedAndSolutionsReached: false,
    maxScansToExplodeReached: false,
    winningPlan: {
      stage: 'FETCH',
      inputStage: {
        stage: 'IXSCAN',
        keyPattern: { breed: 1 },
        indexName: 'breed_1',
        isMultiKey: false,
        multiKeyPaths: { breed: [] },
        isUnique: false,
        isSparse: false,
        isPartial: false,
        indexVersion: 2,
        direction: 'forward',
        indexBounds: { breed: [ '["Labrador Retriever", "Labrador Retriever"]' ] }
      }
    },
    rejectedPlans: []
  },
  executionStats: {
    executionSuccess: true,
    nReturned: 0,
    executionTimeMillis: 0,
    totalKeysExamined: 0,
    totalDocsExamined: 0,
    executionStages: {
      stage: 'FETCH',
      nReturned: 0,
      executionTimeMillisEstimate: 0,
      works: 1,
      advanced: 0,
      needTime: 0,
      needYield: 0,
      saveState: 0,
      restoreState: 0,
      isEOF: 1,
      docsExamined: 0,
      alreadyHasObj: 0,
      inputStage: {
        stage: 'IXSCAN',
        nReturned: 0,
        executionTimeMillisEstimate: 0,
        works: 1,
        advanced: 0,
        needTime: 0,
        needYield: 0,
        saveState: 0,
        restoreState: 0,
        isEOF: 1,
        keyPattern: { breed: 1 },
        indexName: 'breed_1',
        isMultiKey: false,
        multiKeyPaths: { breed: [] },
        isUnique: false,
        isSparse: false,
        isPartial: false,
        indexVersion: 2,
        direction: 'forward',
        indexBounds: { breed: [ '["Labrador Retriever", "Labrador Retriever"]' ] },
        keysExamined: 0,
        seeks: 1,
        dupsTested: 0,
        dupsDropped: 0
      }
    }
  },
  command: {
    find: 'animals',
    filter: { breed: 'Labrador Retriever' },
    '$db': 'test'
  },
  serverInfo: {
    host: 'csdev-mongodb-85dc8bbc87-j9nrm',
    port: 27017,
    version: '6.0.13',
    gitVersion: '3b13907f9bdf6bd3264d67140d6c215d51bbd20c'
  },
  serverParameters: {
    internalQueryFacetBufferSizeBytes: 104857600,
    internalQueryFacetMaxOutputDocSizeBytes: 104857600,
    internalLookupStageIntermediateDocumentMaxSizeBytes: 104857600,
    internalDocumentSourceGroupMaxMemoryBytes: 104857600,
    internalQueryMaxBlockingSortMemoryUsageBytes: 104857600,
    internalQueryProhibitBlockingMergeOnMongoS: 0,
    internalQueryMaxAddToSetBytes: 104857600,
    internalDocumentSourceSetWindowFieldsMaxMemoryBytes: 104857600
  },
  ok: 1
}
test> 

test> db.animals.createIndex({ breed: 1, outcome_type: 1 });
breed_1_outcome_type_1
test> db.animals.find({ breed: "Labrador Retriever", outcome_type: "Transfer" }).explain("executionStats");
{
  explainVersion: '1',
  queryPlanner: {
    namespace: 'test.animals',
    indexFilterSet: false,
    parsedQuery: {
      '$and': [
        { breed: { '$eq': 'Labrador Retriever' } },
        { outcome_type: { '$eq': 'Transfer' } }
      ]
    },
    queryHash: 'E7C1F5D3',
    planCacheKey: '653FF755',
    maxIndexedOrSolutionsReached: false,
    maxIndexedAndSolutionsReached: false,
    maxScansToExplodeReached: false,
    winningPlan: {
      stage: 'FETCH',
      filter: { outcome_type: { '$eq': 'Transfer' } },
      inputStage: {
        stage: 'IXSCAN',
        keyPattern: { breed: 1 },
        indexName: 'breed_1',
        isMultiKey: false,
        multiKeyPaths: { breed: [] },
        isUnique: false,
        isSparse: false,
        isPartial: false,
        indexVersion: 2,
        direction: 'forward',
        indexBounds: { breed: [ '["Labrador Retriever", "Labrador Retriever"]' ] }
      }
    },
    rejectedPlans: [
      {
        stage: 'FETCH',
        inputStage: {
          stage: 'IXSCAN',
          keyPattern: { breed: 1, outcome_type: 1 },
          indexName: 'breed_1_outcome_type_1',
          isMultiKey: false,
          multiKeyPaths: { breed: [], outcome_type: [] },
          isUnique: false,
          isSparse: false,
          isPartial: false,
          indexVersion: 2,
          direction: 'forward',
          indexBounds: {
            breed: [ '["Labrador Retriever", "Labrador Retriever"]' ],
            outcome_type: [ '["Transfer", "Transfer"]' ]
          }
        }
      }
    ]
  },
  executionStats: {
    executionSuccess: true,
    nReturned: 0,
    executionTimeMillis: 0,
    totalKeysExamined: 0,
    totalDocsExamined: 0,
    executionStages: {
      stage: 'FETCH',
      filter: { outcome_type: { '$eq': 'Transfer' } },
      nReturned: 0,
      executionTimeMillisEstimate: 0,
      works: 2,
      advanced: 0,
      needTime: 0,
      needYield: 0,
      saveState: 0,
      restoreState: 0,
      isEOF: 1,
      docsExamined: 0,
      alreadyHasObj: 0,
      inputStage: {
        stage: 'IXSCAN',
        nReturned: 0,
        executionTimeMillisEstimate: 0,
        works: 1,
        advanced: 0,
        needTime: 0,
        needYield: 0,
        saveState: 0,
        restoreState: 0,
        isEOF: 1,
        keyPattern: { breed: 1 },
        indexName: 'breed_1',
        isMultiKey: false,
        multiKeyPaths: { breed: [] },
        isUnique: false,
        isSparse: false,
        isPartial: false,
        indexVersion: 2,
        direction: 'forward',
        indexBounds: { breed: [ '["Labrador Retriever", "Labrador Retriever"]' ] },
        keysExamined: 0,
        seeks: 1,
        dupsTested: 0,
        dupsDropped: 0
      }
    }
  },
  command: {
    find: 'animals',
    filter: { breed: 'Labrador Retriever', outcome_type: 'Transfer' },
    '$db': 'test'
  },
  serverInfo: {
    host: 'csdev-mongodb-85dc8bbc87-j9nrm',
    port: 27017,
    version: '6.0.13',
    gitVersion: '3b13907f9bdf6bd3264d67140d6c215d51bbd20c'
  },
  serverParameters: {
    internalQueryFacetBufferSizeBytes: 104857600,
    internalQueryFacetMaxOutputDocSizeBytes: 104857600,
    internalLookupStageIntermediateDocumentMaxSizeBytes: 104857600,
    internalDocumentSourceGroupMaxMemoryBytes: 104857600,
    internalQueryMaxBlockingSortMemoryUsageBytes: 104857600,
    internalQueryProhibitBlockingMergeOnMongoS: 0,
    internalQueryMaxAddToSetBytes: 104857600,
    internalDocumentSourceSetWindowFieldsMaxMemoryBytes: 104857600
  },
  ok: 1
}
test> clear
ReferenceError: clear is not defined
test> 

test> 

test> 

test> use admin
switched to db admin
admin> db.createUser({
...   user: "aacuser",
...   pwd: "aaN5N2WuMYe-DAQeAsiIWEeZUmNRi0bN_BEgm1luiymMwqkPAbPZxc-Oz37Am97lUCX92jP9e9xtaPErKsK35HthXvAIlbIbFpX1VBG-2GqK9uD4MBH-jU_u6gkUUu65GHdaj_yZF03J43zMwmS7sTBktWdXbMTX_EbHllZJEW7Om10C2IkOj9wwogZDjioFMq4f-mvxcJQyjkT-_E6V5Ng-3ZH0wA3y45",
...   roles: [{ role: "readWrite", db: "AAC" }]
... })
{ ok: 1 }
admin> 
(base) ryanhatch_snhu@nv-snhu8-l01:~$ export MONGO_USER="aacuser"
export MONGO_PASS="aaN5N2WuMYe-DAQeAsiIWEeZUmNRi0bN_BEgm1luiymMwqkPAbPZxc-Oz37Am97lUCX92jP9e9xtaPErKsK35HthXvAIlbIbFpX1VBG-2GqK9uD4MBH-jU_u6gkUUu65GHdaj_yZF03J43zMwmS7sTBktWdXbMTX_EbHllZJEW7Om10C2IkOj9wwogZDjioFMq4f-mvxcJQyjkT-_E6V5Ng-3ZH0wA3y45"
echo $MONGO_USER
echo $MONGO_PASS
aacuser
aaN5N2WuMYe-DAQeAsiIWEeZUmNRi0bN_BEgm1luiymMwqkPAbPZxc-Oz37Am97lUCX92jP9e9xtaPErKsK35HthXvAIlbIbFpX1VBG-2GqK9uD4MBH-jU_u6gkUUu65GHdaj_yZF03J43zMwmS7sTBktWdXbMTX_EbHllZJEW7Om10C2IkOj9wwogZDjioFMq4f-mvxcJQyjkT-_E6V5Ng-3ZH0wA3y45
(base) ryanhatch_snhu@nv-snhu8-l01:~$ mongosh
Current Mongosh Log ID:	669a326b16a3c2e119b9b57a
Connecting to:		mongodb://<credentials>@nv-desktop-services.apporto.com:31692/?directConnection=true&appName=mongosh+1.8.0
Using MongoDB:		6.0.13
Using Mongosh:		1.8.0

For mongosh info see: https://docs.mongodb.com/mongodb-shell/

test> db.runCommand({connectionStatus: 1})
{
  authInfo: {
    authenticatedUsers: [ { user: 'aacuser', db: 'admin' } ],
    authenticatedUserRoles: [ { role: 'readWrite', db: 'AAC' } ]
  },
  ok: 1
}
test>
```

<hr>
<p align="center">
<b><i>Please send me a message on Github, email, or text if you would like to decrypt any of the signed and encrypted archives.<br><br>This is a VERY quick and simple process; PLEASE do not hesitate to reach out.<br>I will provide you with everything needed to decrypt and verify all of the sig files from the signed archive.</b></i><br>
<hr></p>
<p align="center">
<i>This is a kind remember to always verify and double check the validity of a program before installing anything, via the given fingerprints and SHA256 Checksums are <b>ALWAYS</b> supposed to match.</i>
<br></p>
<hr>

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
Comment: User-ID:	ryanshatch <404@SHA-256.io>
Comment: Valid from:	6/5/2024 10:02 AM
Comment: Valid until:	7/5/2034 12:00 PM
Comment: Type:	255-bit EdDSA (secret key available)
Comment: Usage:	Signing, Encryption, Certifying User-IDs
Comment: Fingerprint:	5668E82AF338E8055DDC5C45A60912A538771BE8


mDMEZmBv/xYJKwYBBAHaRw8BAQdAxX25ugehwVFXO0RXXAjhqY/XT4t7h4MiexI5
qf9HOkO0G3J5YW5zaGF0Y2ggPDQwNEBTSEEtMjU2LmlvPoiZBBMWCgBBFiEEVmjo
KvM46AVd3FxFpgkSpTh3G+gFAmZgb/8CGwMFCRL2ToEFCwkIBwICIgIGFQoJCAsC
BBYCAwECHgcCF4AACgkQpgkSpTh3G+jmBgEAtBJJWSwEEPxtnIYELDBcnNZn5dgi
qRqjGKiG5fczRVMA/03OgXikM2BHle1sGXneIfVBmj9A/wKmW2NvzR8POOYNuDgE
ZmBv/xIKKwYBBAGXVQEFAQEHQPT/dy5ulGhJR76YA1eozuvL1lxrHdV8dqohwjbx
ZApLAwEIB4h+BBgWCgAmFiEEVmjoKvM46AVd3FxFpgkSpTh3G+gFAmZgb/8CGwwF
CRL2ToEACgkQpgkSpTh3G+hAKwD/djG0ybfufezgMLVDID0cULhLqfSCxX0vNzG/
6sYeS2gA/0FBWfNmkj2ZjhMmJIf55Xvc30737XUiauiB901nrVQD
=KnH6
-----END PGP PUBLIC KEY BLOCK-----
```

<hr>
