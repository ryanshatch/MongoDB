<hr>

<h1 align="center">MongoDB Dashboard GUI</h1>

<hr>

<p>The MongoDB Dashboard is a web application developed to support the organization in managing and analyzing data related to animal shelters and rescue operations.</p>

<blockquote>The data from the `Austin Animal Centers Outcomes For 2020` was used to build the AAC database.</blockquote>
<!-- <br> -->

---


<p>This Dashboard helps the users to be able to interact with data stored in the MongoDB. It also helps to visualize the queries and parsed data by using data filtering, pie charts, and geolocation mapping.
<br>
All built on the Dash framework, the GUI was designed to be easy for the user to use, maintain, and even add more functionality and develop on top of the current program's GUI Dashboard.
</p>

<hr>

<h2 align="center">Core Functionality:</h2>

<ul>
    <li><strong>Interactive Data Table</strong>: Users can <code>view, filter, and interact with data</code> from the MongoDB database within a dynamic table format.</li>
    <li><strong>Geolocation Mapping</strong>: The dashboard features <code>a map that shows the location</code> of a selected animal based on the data shown in the table.
    <br>
    <blockquote>Water Rescue, Mountain Rescue, Disaster, or Individual Tracking.<blockquote></li>
    <li><strong>Data Visualization</strong>: <code>A pie chart</code> that dynamically updates based on the filtered or selected data, displaying the distribution of the animal breeds with percentages.</li>
</ul>
<p align="center">
<h3>GUI Interaction Examples:</h3>
<p align="center">
<ul>
    <li><a href="https://github.com/ryanshatch/MongoDB/blob/main/Images%20and%20Outputs/Water_Rescue.JPG">Screenshot 1: Water Rescue</a></li>
    <li><a href="https://github.com/ryanshatch/MongoDB/blob/main/Images%20and%20Outputs/Mountain_or_Wilderness_Rescue.JPG">Screenshot 2: Mountain or Wilderness Rescue</a></li>
    <li><a href="https://github.com/ryanshatch/MongoDB/blob/main/Images%20and%20Outputs/Individual_Tracking_to_Find_A_Black_Lab.JPG">Screenshot 3: Disaster or Individual Tracking</a></li>
    <li><a href="https://github.com/ryanshatch/MongoDB/blob/main/Images%20and%20Outputs/GUI.JPG">Screenshot 4: Reset all to unfiltered</a></li>
</ul>

<hr>

<h2 align="center">Tools Used and Justification:</h2>

<h4>1. MongoDB:</h4>
<ul>
    <li><strong>Why MongoDB?</strong></li>
    <ul>
        <li>MongoDB was chosen for its flexibility and scalability as the data model for this project. Its document-based NoSQL structure is very effective for parsing through large amounts of semi-structured data, which worked flawlessly for managing the animal records in this project.</li>
        <li>MongoDB also can be powerful when utilizing other languages to help parse data. For example, with Python you can fluently integrate the MongoDB connections by using the PyMongo library.</li>
        <li>This design allowed for not only a very efficient and flexible data model with tailored operations and functions, but also a very easy method to connect graphically to the data using the Dash framework.</li>
    </ul>
    <li><strong>Key Features:</strong></li>
    <ul>
        <li>Flexible Schema: MongoDB's schema-less design helps to easily add and modify fields without the need for any complex migrations.</li>
        <li>Aggregation Framework: MongoDB's aggregation pipeline supports advanced data analysis directly within the database, which reduces the need for any additional data processing in Python.</li>
    </ul>
</ul>

<h4>2. Dash Framework:</h4>
<ul>
    <li><strong>Why Dash?</strong></li>
    <ul>
        <li>Dash was picked for building the web application because it works well when integrated with Python, making it easier to create data-driven web apps with less time spent coding and development.</li>
        <li>It also handles the structure for both the view and controller parts of the app, using helpful components like <code>html</code>, <code>dcc</code>, and <code>dash_table</code> that make adding interactive features more straightforward.</li>
    </ul>
    <li><strong>Key Features:</strong></li>
    <ul>
        <li>Python Integration: Dash helps developers to build entire applications using only Python, which in turn gets rid of the need for many additional frontend languages like JavaScript.</li>
        <li>Component Library: Dash offers a fairly rich library full of pre-built components like graphs, tables, and maps - all of which are easy to customize.</li>
        <li>Reactivity: Dash's callback system supports automatic updates to the web application in response to users' inputs or any data changes.</li>
    </ul>
</ul>

<h4>3. Additional Tools:</h4>
<ul>
    <li><strong>Pandas:</strong> I used Pandas for handling and transforming data. It provided me with powerful structures like DataFrames, which in turn helped to make it much easier to filter, sort, and adjust the data.</li>
    <li><strong>Plotly:</strong> This was integrated with Dash to create interactive and dynamic charts, like the pie chart used in this project.</li>
    <li><strong>Dash Leaflet:</strong> This tool added geo-location mapping functionality, which added an interactive map that displays right within the GUI/Dash application.</li>
    <li><strong>JupyterDash:</strong> Using JupyterDash made it easier to develop the dashboard within a Jupyter notebook, which in the end was very helpful to streamline the process of iteration and testing.</li>
</ul>

<hr>

<h2 align="center">Project Steps:</h2>

<ol>
    <li><strong>Data Import and Database Setup:</strong></li>
    <ul>
        <li>Imported animal data into MongoDB using the <code>mongoimport</code> tool.</li>
        <li>Developed the CRUD module and configured the <code>AnimalShelter</code> class to interact with MongoDB which holds the methods for reading, parsing, and querying the data.</li>
    </ul>
    <li><strong>Dashboard Development:</strong></li>
    <ul>
        <li>Designed the dashboard layout using Dash components, including the data table, pie chart, and map.</li>
        <li>Developed callback functions to handle user inputs and dynamically update the data table, pie chart, and map accordingly.</li>
    </ul>
    <li><strong>Testing and Debugging:</strong></li>
    <ul>
        <li>Tested the dashboard to make sure that all components function correctly, which included data filtering, chart updates, and the map rendering.</li>
        <li>Resolved issues related to data visualization, making sure that the pie chart displays data clearly for the user by adding more priority to the styling and layout of the components used in the graphical user interface.</li>
    </ul>
    <li><strong>Deployment:</strong></li>
    <ul>
        <li>The last step was to redeploy the dashboard and run a final test to double-check that everything was working as expected. I checked the performance of the application, along with its MongoDB integration and the graphical outputs, to make sure everything functioned smoothly in the production environment.</li>
        <blockquote><i><b>Note: verifying that the dashboard fully utilized the CRUD functions from my Python module was critical for the final deployment to be fully functional.</i></b></blockquote>
    </ul>
</ol>

<hr>

<h2 align="center">Challenges and Solutions:</h2>

<ol>
    <li><strong>Pie Chart Display Issues:</strong></li>
    <ul>
        <li><strong>Challenge:</strong> The pie chart initially appeared cluttered, with extremely small sections and overlapping labels. It also had a 3D blur effect for any of the animals that were not in the top 5 breeds, making it hard to read and understand the data in the chart.</li>
        <li><strong>Solution:</strong> I carefully adjusted the chart size and label font size using Plotly’s layout options, and used the <code>fig.update_traces</code> and <code>fig.update_layout</code> methods to enhance the pie chart’s readability.</li>
        <blockquote><i><b>Note: Subtle or simple changes to the UI always make a big difference on the final result.</i></b><blockquote>
    </ul>
    <li><strong>Database Connection Errors:</strong></li>
    <ul>
        <li><strong>Challenge:</strong> I experienced connection issues with MongoDB, especially during the early development stages in the Apporto environment.</li>
        <li><strong>Solution:</strong> Verified that the MongoDB server was running and accessible, and double-checked the users and the permissions to make sure that the connection was properly configured. I ended up re-adding the user 'aacuser' and gave it the correct permissions to the 'AAC' database, which resolved the connection issues.</li>
    </ul>
    <li><strong>Data Filtering Logic:</strong></li>
    <ul>
        <li><strong>Challenge:</strong> It was fairly complicated to correctly implement the data filtering logic to dynamically update the data table, pie chart, and map based on user inputs.</li>
        <li><strong>Solution:</strong> I used MongoDB’s aggregation framework to run advanced queries, allowing the dashboard to filter data based on the criteria selected by users.</li>
    </ul>
</ol>

<hr>

<h2 align="center">Resources:</h2>

<h4>Data For Database:</h4>

<ul>
    <li><strong>Data Set:</strong> Austin Animal Center Outcomes Spreadsheet</li>
    <ul>
        <li><a href="aac_shelter_outcomes.csv">aac_shelter_outcomes.csv</a></li>
    </ul>

<h4>Python Guides:</h4>
<ul>
    <li><a href="https://go.oreilly.com/SNHU/library/view/head-first-python/9781491919521/">Head First Python</a></li>
    <li><a href="https://www.python.org/dev/peps/pep-0008/">Style Guide for Python Code</a></li>
</ul>

<h4>Documentation:</h4>
<ul>
    <li><a href="https://docs.mongodb.com/">MongoDB Documentation</a></li>
    <li><a href="https://dash.plotly.com/">Dash Documentation</a></li>
    <li><a href="https://plotly.com/python/">Plotly Documentation</a></li>
    <li><a href="https://pymongo.readthedocs.io/">PyMongo Documentation</a></li>
</ul>

<hr>

<h3 align="center">Queries and Terminal Outputs For Data Indexing and Authentication For A New User:</h3>

<hr>

<pre>
  
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
test> use AAC
switched to db AAC
AAC>
AAC> db.animals.createIndex({ breed: 1 });
breed_1
AAC> db.animals.find({ breed: "Labrador Retriever" }).explain("executionStats");
{
  explainVersion: '1',
  queryPlanner: {
    namespace: 'AAC.animals',
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
    '$db': 'AAC'
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
AAC> 

AAC> db.animals.createIndex({ breed: 1, outcome_type: 1 });
breed_1_outcome_type_1
AAC> db.animals.find({ breed: "Labrador Retriever", outcome_type: "Transfer" }).explain("executionStats");
{
  explainVersion: '1',
  queryPlanner: {
    namespace: 'AAC.animals',
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
    '$db': 'AAC'
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
AAC> clear
ReferenceError: clear is not defined
AAC> 
AAC> 
AAC> use admin
switched to db admin
admin> db.createUser({
...   user: "aacuser",
...   pwd: "aaN5N2WuMYe-DAQeAsiIWEeZUmNRi0bN_BEgm1luiymMwqkPAbPZxc-Oz37Am97lUCX92jP9e9xtaPErKsK35HthXvAIlbIbFpX1VBG-2GqK9uD4MBH-jU_u6gkUUu65GHdaj_yZF03J43zMwmS7sTBktWdXbMTX_EbHllZJEW7Om10C2IkOj9wwogZDjioFMq4f-mvxcJQyjkT-_E6V5Ng-3ZH0wA3y45",
...   roles: [{ role: "readWrite", db: "AAC" }]
... })
{ ok: 1 }
admin> exit
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
------
test> use AAC
switched to db AAC
AAC> db.runCommand({connectionStatus: 1})
{
  authInfo: {
    authenticatedUsers: [ { user: 'aacuser', db: 'admin' } ],
    authenticatedUserRoles: [ { role: 'readWrite', db: 'AAC' } ]
  },
  ok: 1
}
AAC>
```
</pre>
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
