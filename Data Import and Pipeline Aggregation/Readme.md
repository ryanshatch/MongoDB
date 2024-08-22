<h2>Advanced Querying with MongoDB In Order To Formulate An Aggrigation Pipeline</h2>

```bash
(base) ryanhatch_snhu@nv-snhu8-l01:~$ mongoimport --host nv-desktop-services.apporto.com --port 31692 --username root --password 86FmoAzWpZ --authenticationDatabase admin --db companies --collection research --file /usr/local/datasets/companies.json
2024-08-21T07:49:20.215+0000	connected to: mongodb://nv-desktop-services.apporto.com:31692/
2024-08-21T07:49:23.167+0000	18801 document(s) imported successfully. 0 document(s) failed to import.
(base) ryanhatch_snhu@nv-snhu8-l01:~$
(base) ryanhatch_snhu@nv-snhu8-l01:~$ mongosh
Current Mongosh Log ID:	66c5a00ed1ca0085acd7e08f
Connecting to:		mongodb://<credentials>@nv-desktop-services.apporto.com:31692/?directConnection=true&appName=mongosh+1.8.0
Using MongoDB:		6.0.13
Using Mongosh:		1.8.0

For mongosh info see: https://docs.mongodb.com/mongodb-shell/

------
   The server generated these startup warnings when booting
   2024-08-21T07:47:21.773+00:00: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine. See http://dochub.mongodb.org/core/prodnotes-filesystem
   2024-08-21T07:47:23.902+00:00: Failed to read /sys/kernel/mm/transparent_hugepage/defrag
   2024-08-21T07:47:23.902+00:00: vm.max_map_count is too low
------

test> show dbs
AAC          5.54 MiB
admin      148.00 KiB
city        10.50 MiB
companies   31.11 MiB
config     108.00 KiB
enron        7.55 MiB
local       88.00 KiB
test        16.00 KiB
test> use companies
switched to db companies
companies> db.research.find({"name" : "AdventNet"})
[
  {
    _id: ObjectId("52cdef7c4bab8bd675297d8b"),
    name: 'AdventNet',
    permalink: 'abc3',
    crunchbase_url: 'http://www.crunchbase.com/company/adventnet',
    homepage_url: 'http://adventnet.com',
    blog_url: '',
    blog_feed_url: '',
    twitter_username: 'manageengine',
    category_code: 'enterprise',
    number_of_employees: 600,
    founded_year: 1996,
    deadpooled_year: 2,
    tag_list: '',
    alias_list: 'Zoho ManageEngine ',
    email_address: 'pr@adventnet.com',
    phone_number: '925-924-9500',
    description: 'Server Management Software',
    created_at: ISODate("2007-05-25T19:24:22.000Z"),
    updated_at: 'Wed Oct 31 18:26:09 UTC 2012',
    overview: '<p>AdventNet is now <a href="/company/zoho-manageengine" title="Zoho ManageEngine" rel="nofollow">Zoho ManageEngine</a>.</p>\n' +
      '\n' +
      '<p>Founded in 1996, AdventNet has served a diverse range of enterprise IT, networking and telecom customers.</p>\n' +
      '\n' +
      '<p>AdventNet supplies server and network management software.</p>',
    image: {
      available_sizes: [
        [
          [ 150, 55 ],
          'assets/images/resized/0001/9732/19732v1-max-150x150.png'
        ],
        [
          [ 150, 55 ],
          'assets/images/resized/0001/9732/19732v1-max-250x250.png'
        ],
        [
          [ 150, 55 ],
          'assets/images/resized/0001/9732/19732v1-max-450x450.png'
        ]
      ]
    },
    products: [],
    relationships: [
      {
        is_past: true,
        title: 'CEO and Co-Founder',
        person: {
          first_name: 'Sridhar',
          last_name: 'Vembu',
          permalink: 'sridhar-vembu'
        }
      },
      {
        is_past: true,
        title: 'VP of Business Dev',
        person: {
          first_name: 'Neil',
          last_name: 'Butani',
          permalink: 'neil-butani'
        }
      },
      {
        is_past: true,
        title: 'Usabiliy Engineer',
        person: {
          first_name: 'Bharath',
          last_name: 'Balasubramanian',
          permalink: 'bharath-balasibramanian'
        }
      },
      {
        is_past: true,
        title: 'Director of Engineering',
        person: {
          first_name: 'Rajendran',
          last_name: 'Dandapani',
          permalink: 'rajendran-dandapani'
        }
      },
      {
        is_past: true,
        title: 'Market Analyst',
        person: {
          first_name: 'Aravind',
          last_name: 'Natarajan',
          permalink: 'aravind-natarajan'
        }
      },
      {
        is_past: true,
        title: 'Director of Product Management',
        person: {
          first_name: 'Hyther',
          last_name: 'Nizam',
          permalink: 'hyther-nizam'
        }
      },
      {
        is_past: true,
        title: 'Western Regional OEM Sales Manager',
        person: {
          first_name: 'Ian',
          last_name: 'Wenig',
          permalink: 'ian-wenig'
        }
      }
    ],
    competitions: [],
    providerships: [
      {
        title: 'DHFH',
        is_past: true,
        provider: { name: 'A Small Orange', permalink: 'a-small-orange' }
      }
    ],
    total_money_raised: '$0',
    funding_rounds: [],
    investments: [],
    acquisition: null,
    acquisitions: [],
    offices: [
      {
        description: 'Headquarters',
        address1: '4900 Hopyard Rd.',
        address2: 'Suite 310',
        zip_code: '94588',
        city: 'Pleasanton',
        state_code: 'CA',
        country_code: 'USA',
        latitude: 37.692934,
        longitude: -121.904945
      }
    ],
    milestones: [],
    video_embeds: [],
    screenshots: [
      {
        available_sizes: [
          [
            [ 150, 94 ],
            'assets/images/resized/0004/3400/43400v1-max-150x150.png'
          ],
          [
            [ 250, 156 ],
            'assets/images/resized/0004/3400/43400v1-max-250x250.png'
          ],
          [
            [ 450, 282 ],
            'assets/images/resized/0004/3400/43400v1-max-450x450.png'
          ]
        ],
        attribution: null
      }
    ],
    external_links: [],
    partners: []
  }
]
companies> db.research.find({"founded_year" : 1996}, {"name" : 1}).limit(10)
[
  { _id: ObjectId("52cdef7c4bab8bd675297d8b"), name: 'AdventNet' },
  { _id: ObjectId("52cdef7c4bab8bd675297e24"), name: 'RegOnline' },
  { _id: ObjectId("52cdef7c4bab8bd675297e42"), name: 'LiveWorld' },
  { _id: ObjectId("52cdef7c4bab8bd675297f26"), name: 'Shopzilla' },
  { _id: ObjectId("52cdef7c4bab8bd675297fca"), name: 'LinkShare' },
  { _id: ObjectId("52cdef7c4bab8bd675298032"), name: 'MSNBC' },
  { _id: ObjectId("52cdef7c4bab8bd6752980cf"), name: 'TheStreet' },
  { _id: ObjectId("52cdef7c4bab8bd6752980d0"), name: 'Omniture' },
  { _id: ObjectId("52cdef7c4bab8bd6752980df"), name: 'Blucora' },
  { _id: ObjectId("52cdef7c4bab8bd675298223"), name: 'Alexa' }
]
companies> db.research.find({"founded_year": {$gt: 2010}}, {"name": 1, "_id": 0}).sort({"name": 1}).limit(20)
[
  { name: '4shared' },
  { name: 'Advaliant' },
  { name: 'Advisor' },
  { name: 'Baveo' },
  { name: 'Bling Easy' },
  { name: 'Carfeine' },
  { name: 'CircleUp' },
  { name: 'Clowdy' },
  { name: 'CompareChecker' },
  { name: 'Cyphercor' },
  { name: 'DocASAP' },
  { name: 'Easel' },
  { name: 'EasyBib' },
  { name: 'Emotive Communications' },
  { name: 'FAT Media' },
  { name: 'FamilyDen' },
  { name: 'FirstString' },
  { name: 'Fixya' },
  { name: 'Fliggo' },
  { name: 'Fluc' }
]
Type "it" for more
companies> db.research.find({"offices.state": {$in: ["California", "Texas"]}}, {"name": 1, "number_of_employees": 1, "_id": 0})

companies>   .sort({"number_of_employees": -1})
Invalid REPL keyword
companies> db.research.find({"offices.state": {$in: ["California", "Texas"]}}, {"name": 1, "number_of_employees": 1, "_id": 0}).sort({"number_of_employees": -1}).limit(20)

companies> db.research.find({"offices.state": {$in: ["California", "Texas"]}}, {"name": 1, "number_of_employees": 1, "_id": 0}).sort({"number_of_employees": -1}).limit(20)

companies> db.research.find({"offices.state": {$in: ["California", "Texas"]}}, {"offices.state": 1, "name": 1, "_id": 0}).limit(5)

companies> db.research.find({"offices.state_code": {$in: ["CA", "TX"]}}, {"name": 1, "number_of_employees": 1, "_id": 0}).sort({"number_of_employees": -1}).limit(20)
[
  { name: 'PayPal', number_of_employees: 300000 },
  { name: 'Samsung Electronics', number_of_employees: 221726 },
  { name: 'Accenture', number_of_employees: 205000 },
  { name: 'Flextronics International', number_of_employees: 200000 },
  { name: 'Safeway', number_of_employees: 186000 },
  { name: 'Sony', number_of_employees: 180500 },
  { name: 'Intel', number_of_employees: 86300 },
  { name: 'Apple', number_of_employees: 80000 },
  { name: 'Dell', number_of_employees: 80000 },
  { name: 'ExxonMobil', number_of_employees: 76900 },
  { name: 'Affiliated Computer Services', number_of_employees: 74000 },
  { name: 'Cisco', number_of_employees: 63000 },
  { name: 'Sun Microsystems', number_of_employees: 33350 },
  { name: 'Texas Instruments', number_of_employees: 30175 },
  { name: 'Google', number_of_employees: 28000 },
  { name: 'The Walt Disney Company', number_of_employees: 25000 },
  { name: 'Avaya', number_of_employees: 18000 },
  { name: 'AMD', number_of_employees: 16420 },
  { name: 'Experian', number_of_employees: 15500 },
  { name: 'IQ Backoffice', number_of_employees: 15000 }
]
Type "it" for more
companies> db.research.aggregate([{ $unwind: "$offices" }, { $match: { "offices.country": "United States" } }, { $group: { _id: "$offices.state", totalOffices: { $sum: 1 } } }, { $sort: { totatotalOffices: -1 } }])

companies> db.research.aggregate([
...   { $unwind: "$offices" },
...   { $match: { "offices.country": "United States" } },
...   { $group: { _id: "$offices.state", totalOffices: { $sum: 1 } } },
...   { $sort: { totalOffices: -1 } }
... ])

companies> db.research.aggregate([
...   { $unwind: "$offices" },
...   { $match: { "offices.country": "United States" } },
...   { $group: { _id: "$offices.state", totalOffices: { $sum: 1 } } },
...   { $sort: { totalOffices: -1 } }
... ])

companies> db.research.find({ "offices.country": "United States" }, { "offices.state": 1, "_id": 0 }).limit(5)

companies> db.research.findOne({}, { offices: 1, _id: 0 })
{
  offices: [
    {
      description: 'Headquarters',
      address1: '4900 Hopyard Rd.',
      address2: 'Suite 310',
      zip_code: '94588',
      city: 'Pleasanton',
      state_code: 'CA',
      country_code: 'USA',
      latitude: 37.692934,
      longitude: -121.904945
    }
  ]
}
companies> db.research.aggregate([
...   { $unwind: "$offices" },
...   { $match: { "offices.country_code": "USA" } },
...   { $group: { _id: "$offices.state_code", totalOffices: { $sum: 1 } } },
...   { $sort: { totalOffices: -1 } }
... ])
[
  { _id: 'CA', totalOffices: 3903 },
  { _id: 'NY', totalOffices: 1084 },
  { _id: 'MA', totalOffices: 623 },
  { _id: 'TX', totalOffices: 500 },
  { _id: 'WA', totalOffices: 415 },
  { _id: 'FL', totalOffices: 349 },
  { _id: 'IL', totalOffices: 308 },
  { _id: 'VA', totalOffices: 256 },
  { _id: null, totalOffices: 252 },
  { _id: 'CO', totalOffices: 224 },
  { _id: 'PA', totalOffices: 223 },
  { _id: 'GA', totalOffices: 206 },
  { _id: 'NJ', totalOffices: 204 },
  { _id: 'MD', totalOffices: 142 },
  { _id: 'NC', totalOffices: 138 },
  { _id: 'AZ', totalOffices: 135 },
  { _id: 'OR', totalOffices: 106 },
  { _id: 'MI', totalOffices: 100 },
  { _id: 'OH', totalOffices: 99 },
  { _id: 'MN', totalOffices: 95 }
]
Type "it" for more
companies>
companies> it
[
  { _id: 'UT', totalOffices: 82 },
  { _id: 'DC', totalOffices: 82 },
  { _id: 'CT', totalOffices: 67 },
  { _id: 'TN', totalOffices: 57 },
  { _id: 'MO', totalOffices: 55 },
  { _id: 'NV', totalOffices: 52 },
  { _id: 'WI', totalOffices: 47 },
  { _id: 'IN', totalOffices: 46 },
  { _id: 'NH', totalOffices: 41 },
  { _id: 'SC', totalOffices: 30 },
  { _id: 'NE', totalOffices: 28 },
  { _id: 'DE', totalOffices: 27 },
  { _id: 'KY', totalOffices: 27 },
  { _id: 'AL', totalOffices: 26 },
  { _id: 'KS', totalOffices: 24 },
  { _id: 'OK', totalOffices: 20 },
  { _id: 'IA', totalOffices: 18 },
  { _id: 'VT', totalOffices: 18 },
  { _id: 'NM', totalOffices: 18 },
  { _id: 'ME', totalOffices: 17 }
]
Type "it" for more
companies> db.research.aggregate([
...   { $unwind: "$offices" },
...   { $match: { "offices.country_code": "USA" } },
...   { $group: { _id: "$offices.state_code", totalOffices: { $sum: 1 } } },
...   { $sort: { totalOffices: -1 } }
... ]).toArray()
[
  { _id: 'CA', totalOffices: 3903 },
  { _id: 'NY', totalOffices: 1084 },
  { _id: 'MA', totalOffices: 623 },
  { _id: 'TX', totalOffices: 500 },
  { _id: 'WA', totalOffices: 415 },
  { _id: 'FL', totalOffices: 349 },
  { _id: 'IL', totalOffices: 308 },
  { _id: 'VA', totalOffices: 256 },
  { _id: null, totalOffices: 252 },
  { _id: 'CO', totalOffices: 224 },
  { _id: 'PA', totalOffices: 223 },
  { _id: 'GA', totalOffices: 206 },
  { _id: 'NJ', totalOffices: 204 },
  { _id: 'MD', totalOffices: 142 },
  { _id: 'NC', totalOffices: 138 },
  { _id: 'AZ', totalOffices: 135 },
  { _id: 'OR', totalOffices: 106 },
  { _id: 'MI', totalOffices: 100 },
  { _id: 'OH', totalOffices: 99 },
  { _id: 'MN', totalOffices: 95 },
  { _id: 'UT', totalOffices: 82 },
  { _id: 'DC', totalOffices: 82 },
  { _id: 'CT', totalOffices: 67 },
  { _id: 'TN', totalOffices: 57 },
  { _id: 'MO', totalOffices: 55 },
  { _id: 'NV', totalOffices: 52 },
  { _id: 'WI', totalOffices: 47 },
  { _id: 'IN', totalOffices: 46 },
  { _id: 'NH', totalOffices: 41 },
  { _id: 'SC', totalOffices: 30 },
  { _id: 'NE', totalOffices: 28 },
  { _id: 'DE', totalOffices: 27 },
  { _id: 'KY', totalOffices: 27 },
  { _id: 'AL', totalOffices: 26 },
  { _id: 'KS', totalOffices: 24 },
  { _id: 'OK', totalOffices: 20 },
  { _id: 'IA', totalOffices: 18 },
  { _id: 'VT', totalOffices: 18 },
  { _id: 'NM', totalOffices: 18 },
  { _id: 'ME', totalOffices: 17 },
  { _id: 'ID', totalOffices: 16 },
  { _id: 'RI', totalOffices: 13 },
  { _id: 'HI', totalOffices: 13 },
  { _id: 'AR', totalOffices: 12 },
  { _id: 'LA', totalOffices: 10 },
  { _id: 'MT', totalOffices: 7 },
  { _id: 'WY', totalOffices: 4 },
  { _id: 'MS', totalOffices: 3 },
  { _id: 'ND', totalOffices: 3 },
  { _id: 'WV', totalOffices: 3 },
  { _id: 'SD', totalOffices: 1 }
]
companies> 

companies> 

companies> 

```

<hr>
