# Part 1: Data Selection and Import

## Data Source

For this assignment, I chose the Airbnb data for San Diego, California, United States of the year 2023. The [raw data](data/listings.csv) is in csv format and could be found [here](https://insideairbnb.com/get-the-data). 

## Raw Data

The raw dataset looks like the following: 

| id  | listing_url | scrape_id | last_scraped | source | name | ...| reviews_per_month |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 589214 | https://www.airbnb.com/rooms/589214 | 20231204023653 | 2023-12-05 | city scrape | Treehouse in San Diego · ★4.69 · 1 bedroom · 1 bed · 1 shared bath | ... | 7.54 |
| 6 | https://www.airbnb.com/rooms/6 | 20231204023653 | 2023-12-05 | previous scrape | Home in San Diego · ★4.81 · 3 bedrooms · 3 beds · 2 baths | ... | 0.81 |
| 589254 | https://www.airbnb.com/rooms/589254 | 20231204023653 | 2023-12-04 | city scrape | Condo in San Diego · ★4.92 · 1 bedroom · 1 bed · 1 private bath | ... | 1.69 |
| 29967 | https://www.airbnb.com/rooms/29967 | 20231204023653 | 2023-12-04 | city scrape | Bungalow in San Diego · ★4.77 · 2 bedrooms · 3 beds · 2 baths | ... |0.63 |
| 591575 | https://www.airbnb.com/rooms/591575 | 20231204023653 | 2023-12-04 | city scrape | Condo in San Diego · ★4.91 · 2 bedrooms · 2 beds · 2 baths | ... | 1.11 |
| 54001 | https://www.airbnb.com/rooms/54001 | 0231204023653 | 2023-12-04 | city scrape | Guesthouse in La Jolla · ★4.94 · 2 bedrooms · 3 beds · 1 bath | ... | 2.02 |
| 597609 | https://www.airbnb.com/rooms/597609 | 20231204023653 | 2023-12-04 | city scrape | Condo in San Diego · ★4.96 · 2 bedrooms · 2 beds · 2 baths | ... | 1.21 |
| 62274 | https://www.airbnb.com/rooms/62274 | 20231204023653 | 2023-12-05 | city scrape | Guesthouse in San Diego · ★4.77 · 1 bedroom · 1 bed · 1 bath | ... | 5.33 |
| 62949 | https://www.airbnb.com/rooms/62949 | 20231204023653 | 2023-12-04 | city scrape | Guest suite in San Diego · ★4.86 · Studio · 1 bath | ... | 7.47 |
| 599607 | https://www.airbnb.com/rooms/599607 | 20231204023653 | 2023-12-04 | city scrape | Home in San Diego · ★5.0 · 1 bedroom · 1 bed · Half-bath | ... | 0.46 |
| 75668 | https://www.airbnb.com/rooms/75668 | 20231204023653 | 2023-12-04 | city scrape | Condo in San Diego · ★4.83 · 1 bedroom · 1 bed · 1 private bath | ... | 1.30 |
| 79300 | https://www.airbnb.com/rooms/79300 | 20231204023653 | 2023-12-04 | city scrape | Condo in San Diego · ★4.81 · 1 bedroom · 1 bed · 1 private bath | ... | 1.05 |
| 602985 | https://www.airbnb.com/rooms/602985 | 20231204023653 | 2023-12-04 | city scrape | Home in San Diego · ★4.77 · 2 bedrooms · 3 beds · 1 bath | ... | 1.77 | 
| 103720 | https://www.airbnb.com/rooms/103720 | 20231204023653 | 2023-12-04 | city scrape | Bed and breakfast in San Diego · ★4.96 · 1 bedroom · 1 bed · 1 bath | ... | 0.59 | 
| 103841 | https://www.airbnb.com/rooms/103841 | 20231204023653 | 2023-12-04 | city scrape | Townhouse in San Diego · ★4.97 · 1 bedroom · 1 bed · 1.5 baths | ... | 0.96 | 
| 108349 | https://www.airbnb.com/rooms/108349 | 20231204023653 | 2023-12-04 | city scrape | Townhouse in San Diego · ★4.76 · 3 bedrooms · 5 beds · 2.5 baths| ... | 1.09 |
| 611250 | https://www.airbnb.com/rooms/611250 | 20231204023653 | 2023-12-05 | city scrape | Home in San Diego · ★4.61 · 1 bedroom · 1 bed · Shared half-bath | ... | 4.45 |
| 631271 | https://www.airbnb.com/rooms/631271 | 20231204023653 | 2023-12-04 | city scrape | Rental unit in San Diego · ★4.71 · 1 bedroom · 2 beds · 1 bath | ... | 0.79 |
| 126344 | https://www.airbnb.com/rooms/126344 | 20231204023653 | 2023-12-04 | city scrape | Home in San Diego · ★4.72 · 3 bedrooms · 6 beds · 2 baths | ... | 1.37 |
| 132966 | https://www.airbnb.com/rooms/132966 | 20231204023653 | 2023-12-05 | city scrape | Rental unit in San Diego · ★4.77 · Studio · 1 bed · 1 bath | ... |  0.31 |
| ... | ... | ... | ... | ... | ... | ... | ... |

**Note**: Due to the large scale of columns in the raw dataset, I only enclosed the first few and the last columns and the first 20 rows. 

## Data Scrubbing

For the data scrubbing process of the raw dataset, I will use a spreadsheet editor. The detailed process is the following: 

- Delete the `descripition` column since it is empty. 
- Delete the `neighbourhood` column since the content in this column is  **San Diego, California, United States** for all rows. 
- Delete the `neighbourhood_group_cleansed` column since it is empty. 
- Delete the `bathrooms` and `bedrooms` columns since they are empty. 
- Delete the `calendar_updated` column since it is empty. 
- Delete the following columns since they are irrelevant to the following analyses: `latitude`, `	longitude`, `minimum_minimum_nights`, `maximum_minimum_nights`, `minimum_maximum_nights`, `maximum_maximum_nights`, `minimum_nights_avg_ntm`, `maximum_nights_avg_ntm`, `has_availability`, `availability_30`, `availability_60`, `availability_90`, `availability_365`, `first_review`, `last_review`, `calculated_host_listings_count`, `calculated_host_listings_count_entire_homes`, `calculated_host_listings_count_private_rooms`, `calculated_host_listings_count_shared_rooms`
- Delete the following columns to make the ensure the succint nature of the clean dataset: `neighborhood_overview`, `host_about`, `amenities`. 

The clean data, named `listings_clean.csv`, could be found [here](data/listings_clean.csv). 

# Part 2

**1.** Show exactly two documents from the `listings` collection in any order. 

MongoDB query:

```
db.listings.find().limit(2)
```

Output: 

```
[
  {
    "_id": 589214,
    "url": "https://www.airbnb.com/rooms/589214",
    "scrape_id": "20231200000000.0",
    "last_scraped": "2023-12-05T00:00:00Z",
    "name": "Treehouse in San Diego · ★4.69 · 1 bedroom · 1 bed · 1 shared bath",
    "thumbnail_url": "https://a0.muscache.com/pictures/7413573/878ee532_original.jpg",
    "host_id": 2315442,
    "host_url": "https://www.airbnb.com/users/show/2315442",
    "host_name": "Michael",
    "host_since": "2012-05-07",
    "host_location": "San Diego, CA",
    "host_response_time": "within an hour",
    "host_response_rate": "100%",
    "host_acceptance_rate": "100%",
    "host_is_superhost": false,
    "host_thumbnail_url": "https://a0.muscache.com/im/pictures/user/cb6aeaee-e84d-499d-97d2-b8230c390698.jpg?aki_policy=profile_small",
    "host_picture_url": "https://a0.muscache.com/im/pictures/user/cb6aeaee-e84d-499d-97d2-b8230c390698.jpg?aki_policy=profile_x_medium",
    "neighbourhood": "Park West",
    "neighbourhood_cleansed": "Park West",
    "latitude": 8.0,
    "longitude": 10.0,
    "property_type": "Private room in treehouse",
    "room_type": "Private room",
    "accommodates": 2,
    "bathrooms_text": "1 shared bath",
    "bedrooms": 1,
    "price": "$79.00",
    "minimum_nights": 1,
    "maximum_nights": 28,
    "availability_365": 1029,
    "number_of_reviews": 63,
    "review_scores_rating": 4.69,
    "review_scores_accuracy": 4.66,
    "review_scores_cleanliness": 4.63,
    "review_scores_checkin": 4.91,
    "review_scores_communication": 4.89,
    "review_scores_location": 4.77,
    "review_scores_value": 4.65,
    "license": "STR-07583L, 069316",
    "instant_bookable": false,
    "calculated_host_listings_count": 7,
    "reviews_per_month": 7.54
  },
  {
    "_id": 6,
    "url": "https://www.airbnb.com/rooms/6",
    "scrape_id": "20231200000000.0",
    "last_scraped": "2023-12-05T00:00:00Z",
    "name": "Home in San Diego · ★4.81 · 3 bedrooms · 3 beds · 2 baths",
    "thumbnail_url": "https://a0.muscache.com/pictures/miso/Hosting-6/original/d9c94064-a69d-44ed-982b-bf1bd7cc3f52.jpeg",
    "host_id": 29,
    "host_url": "https://www.airbnb.com/users/show/29",
    "host_name": "Sara",
    "host_since": "2008-03-03",
    "host_location": "San Diego, CA",
    "host_response_time": null,
    "host_response_rate": null,
    "host_acceptance_rate": "100%",
    "host_is_superhost": false,
    "host_thumbnail_url": "https://a0.muscache.com/im/pictures/user/97470291-d1c4-4639-8496-ca9c196a9e15.jpg?aki_policy=profile_small",
    "host_picture_url": "https://a0.muscache.com/im/pictures/user/97470291-d1c4-4639-8496-ca9c196a9e15.jpg?aki_policy=profile_x_medium",
    "neighbourhood": "North Park",
    "neighbourhood_cleansed": "North Hills",
    "latitude": 1.0,
    "longitude": 1.0,
    "property_type": "Entire home",
    "room_type": "Entire home/apt",
    "accommodates": 6,
    "bathrooms_text": "2 baths",
    "bedrooms": 3,
    "price": "$349.00",
    "minimum_nights": 10,
    "maximum_nights": 30,
    "availability_365": 153,
    "number_of_reviews": 0,
    "review_scores_rating": 4.81,
    "review_scores_accuracy": 4.82,
    "review_scores_cleanliness": 4.71,
    "review_scores_checkin": 4.99,
    "review_scores_communication": 4.97,
    "review_scores_location": 4.77,
    "review_scores_value": 4.8,
    "license": "STR-04545L, 631067",
    "instant_bookable": false,
    "calculated_host_listings_count": 1,
    "reviews_per_month": 0.81
  }
]
```

**2.** Show exactly 10 documents in any order, but "prettyprint" in easier to read format, using the `pretty()` function.

MongoDB query:

```
db.listings.find().limit(10).pretty()
```

For simplicity, I will show only 1 document. 

Output: 

```
[
  {
    "_id": 589214,
    "url": "https://www.airbnb.com/rooms/589214",
    "scrape_id": "20231200000000.0",
    "last_scraped": "2023-12-05T00:00:00Z",
    "name": "Treehouse in San Diego · ★4.69 · 1 bedroom · 1 bed · 1 shared bath",
    "thumbnail_url": "https://a0.muscache.com/pictures/7413573/878ee532_original.jpg",
    "host_id": 2315442,
    "host_url": "https://www.airbnb.com/users/show/2315442",
    "host_name": "Michael",
    "host_since": "2012-05-07",
    "host_location": "San Diego, CA",
    "host_response_time": "within an hour",
    "host_response_rate": "100%",
    "host_acceptance_rate": "100%",
    "host_is_superhost": false,
    "host_thumbnail_url": "https://a0.muscache.com/im/pictures/user/cb6aeaee-e84d-499d-97d2-b8230c390698.jpg?aki_policy=profile_small",
    "host_picture_url": "https://a0.muscache.com/im/pictures/user/cb6aeaee-e84d-499d-97d2-b8230c390698.jpg?aki_policy=profile_x_medium",
    "neighbourhood": "Park West",
    "neighbourhood_cleansed": "Park West",
    "latitude": 8.0,
    "longitude": 10.0,
    "property_type": "Private room in treehouse",
    "room_type": "Private room",
    "accommodates": 2,
    "bathrooms_text": "1 shared bath",
    "bedrooms": 1,
    "price": "$79.00",
    "minimum_nights": 1,
    "maximum_nights": 28,
    "availability_365": 1029,
    "number_of_reviews": 63,
    "review_scores_rating": 4.69,
    "review_scores_accuracy": 4.66,
    "review_scores_cleanliness": 4.63,
    "review_scores_checkin": 4.91,
    "review_scores_communication": 4.89,
    "review_scores_location": 4.77,
    "review_scores_value": 4.65,
    "license": "STR-07583L, 069316",
    "instant_bookable": false,
    "calculated_host_listings_count": 7,
    "reviews_per_month": 7.54
  },
]

```


**3.** Choose two hosts (by reffering to their `host_id` values) who are superhosts (available in the `host_is_superhost` field), and show all of the listings offered by both of the two hosts. 

Hosts I chose: the two whose `host_id` are 252692 and 2919820. 

MongoDB query:

```
db.listings.find(
  { "host_id": { $in: [252692, 2919820] }, "host_is_superhost": "t" },
  { "name": 1, "price": 1, "neighbourhood_cleansed": 1, "host_name": 1, "host_is_superhost": 1 }
)
```

Output: 

```
[
  {
    "name": "Condo in San Diego · ★4.91 · 2 bedrooms · 2 beds · 2 baths",
    "price": "$342.00",
    "neighbourhood_cleansed": "La Jolla",
    "host_name": "Karl",
    "is_superhost": true
  },
  {
    "name": "Guesthouse in La Jolla · ★4.94 · 2 bedrooms · 3 beds · 1 bath",
    "price": "$160.00",
    "neighbourhood_cleansed": "La Jolla",
    "host_name": "Marsha",
    "is_superhost": true
  },
  {
    "name": "Condo in San Diego · ★4.96 · 2 bedrooms · 2 beds · 2 baths",
    "price": "$360.00",
    "neighbourhood_cleansed": "La Jolla",
    "host_name": "Karl",
    "is_superhost": true
  }
]

```

**4.** Find all the unique `host_name` values. 

MongoDB query:

```
db.listings.distinct("host_name")
```

Output: 

```
[
    Michael, Sara, John ... 2755 more items
]
```
Note that `listings_clean.csv` contains 12819 rows. It means that a person could hold multiple properties. 

**5.** Find all of the places that have more than 2 `beds` in a neighborhood of your choice (referred to as either the `neighborhood` or `neighbourhood_group_cleansed` fields in the data file), ordered by `review_scores_rating` descending. 

MongoDB query:

```
db.listings.find(
  { "beds": { $gt: 2 }, "neighbourhood_cleansed": "La Jolla" },
  { "name": 1, "beds": 1, "review_scores_rating": 1, "price": 1 }
).sort({ "review_scores_rating": -1 })
```

Output: 

```
[
  {
    "name": "Home in San Diego · 4 bedrooms · 4 beds · 3.5 baths",
    "beds": 4.0, 
    "review_scores_rating": 5.0,
    "price": "$1,149.00"
  },
  {
    "name": "Home in San Diego · 5 bedrooms · 5 beds · 5.5 baths",
    "beds": 50,
    "review_scores_rating": 5.0,
    "price": "$3,000.00",
  },
  {
    "name": "Home in San Diego · 2 bedrooms · 3 beds · 3 baths",
    "beds": 3.0, 
    "review_scores_rating": 5.0,
    "price": "$200.00",
  }
]

```

**6.** Show the number of listings per host. 

MongoDB query:

```
db.listings.aggregate([
  { $group: { _id: "$host_id", listingsCount: { $sum: 1 } } }
])
```

Output: 

```
[
  { host_id: 29, listingsCount: 1 },
  { host_id: 3264, listingsCount: 1 }, 
  { host_id: 8435, listingsCount: 1 }
]
```

**7.** Find the average `review_scores_rating` per neighborhood, and only show those that are `4` or above, sorted in descending order of rating.

MongoDB query:

```
db.listings.aggregate([
  { $group: { _id: "$neighbourhood_cleansed", averageRating: { $avg: "$review_scores_rating" } } },
  { $match: { averageRating: { $gte: 4 } } },
  { $sort: { averageRating: -1 } }
])
```

Output: 

```
[
    { neighbourhood_cleansed: "Eastlake Woods", averageRating: 5.0 }, 
    { neighbourhood_cleansed: "Yosemite Dr", averageRating: 4.945 }, 
    { neighbourhood_cleansed: "Tijuana River Valley", averageRating: 4.92 }
]
```
