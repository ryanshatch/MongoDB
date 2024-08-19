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

## Querys and Terminal Outputs:

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
