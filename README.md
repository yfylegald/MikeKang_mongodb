# Report of airbnb-mongodb-analysis

## The origin of data set
The data set is AirBnB listings data in Seattle, Washington, United States, and is downloaded from this URL: <br>
http://data.insideairbnb.com/united-states/dc/washington-dc/2023-03-19/data/listings.csv.gz <br>
The original data file was in CSV format. <br>

## Some of the raw data from the original data file
```js
id,listing_url,scrape_id,last_scraped,source,name,description,neighborhood_overview,picture_url,host_id,host_url,host_name,host_since,host_location,host_about,host_response_time,host_response_rate,host_acceptance_rate,host_is_superhost,host_thumbnail_url,host_picture_url,host_neighbourhood,host_listings_count,host_total_listings_count,host_verifications,host_has_profile_pic,host_identity_verified,neighbourhood,neighbourhood_cleansed,neighbourhood_group_cleansed,latitude,longitude,property_type,room_type,accommodates,bathrooms,bathrooms_text,bedrooms,beds,amenities,price,minimum_nights,maximum_nights,minimum_minimum_nights,maximum_minimum_nights,minimum_maximum_nights,maximum_maximum_nights,minimum_nights_avg_ntm,maximum_nights_avg_ntm,calendar_updated,has_availability,availability_30,availability_60,availability_90,availability_365,calendar_last_scraped,number_of_reviews,number_of_reviews_ltm,number_of_reviews_l30d,first_review,last_review,review_scores_rating,review_scores_accuracy,review_scores_cleanliness,review_scores_checkin,review_scores_communication,review_scores_location,review_scores_value,license,instant_bookable,calculated_host_listings_count,calculated_host_listings_count_entire_homes,calculated_host_listings_count_private_rooms,calculated_host_listings_count_shared_rooms,reviews_per_month
22229408,https://www.airbnb.com/rooms/22229408,20230319041206,2023-03-19,previous scrape,"Explorer's Paradise: Near Train, Bus & Bike Share","Welcome to your perfect urban escape in the Nation’s Capital! Only .4 miles (10 min walk) from the Metro train & Capital Bikeshare, and a 10 min Metro ride to major DC attractions, this oasis has all you need to enjoy a weekend or extended stay. Perfect space for singles and couples.<br /><br /><b>Guest access</b><br />This remodeled home has 2 stories of space to enjoy when staying here for your visit in the DC area. Guests have own private room that includes: queen bed with high quality bed linens/blankets, ceiling fan, private closet with hamper and ample clothes hangers, luggage rack, and full-length mirror. Adjacent to the guest room is a completely remodeled bathroom, just for use by guests, furnished with plush towels and hair dryer. Bedroom and bathroom are on the upper story of the home. The other shared areas that are accessible to our guests, include a quaint front porch, that is perfect for unwinding in the evening, and a calm and comfortable living /dining room.<br /><br /","My home is located in the Edgewood neighborhood of DC. Upon first glance, some people see it as a bit rough around the edges, but the business owners and neighbors are all very friendly. The neighborhood was once the estate of Salmon P. Chase: statesman, abolitionist and jurist. The neighborhood arose with the establishment of the Metropolitan Branch Line of the C&O Railroad in 1873. This line now includes the Metropolitan Branch Trail (a biking and walking trail) and the red line of the metro (subway). Within a few blocks are grocery stores, dry cleaners, drug stores, etc. There are many nearby options for eating and shopping.<br />Directly at the Rhode Island Metro Station, you will find a CVS, Home Depot, major grocery store, TJ Maxx, a wonderful nail salon and sit-down and fast casual restaurants, including Salathai, Chipotle, and Carolina Kitchen among other options.<br /><br />A 15-min walk in one direction takes to you the heart of Bloomingdale, where you will find great places ",https://a0.muscache.com/pictures/8e49b7bc-a851-4e46-a8b6-76ea88c96124.jpg,120875011,https://www.airbnb.com/users/show/120875011,J. P.,2017-03-15,"Washington, DC","",N/A,N/A,N/A,f,https://a0.muscache.com/im/pictures/user/ba485797-0a7c-4867-acce-9f3dd3cd5511.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/ba485797-0a7c-4867-acce-9f3dd3cd5511.jpg?aki_policy=profile_x_medium,Edgewood,1,2,"['email', 'phone']",t,f,"Washington, District of Columbia, United States","Edgewood, Bloomingdale, Truxton Circle, Eckington",,38.92217,-77.00045,Private room in townhouse,Private room,2,,1 private bath,1,1,"[""Essentials"", ""Shampoo"", ""Air conditioning"", ""Hair dryer"", ""TV"", ""Wifi"", ""Lockbox"", ""Heating"", ""Carbon monoxide alarm"", ""Iron"", ""Self check-in"", ""Smoke alarm"", ""Free street parking""]",$20.00,31,150,31,31,150,150,31.0,150.0,,t,0,0,0,0,2023-03-19,20,0,0,2018-01-11,2021-06-30,4.85,4.65,4.9,4.95,4.85,4.75,4.75,,f,1,0,1,0,0.32
46951758,https://www.airbnb.com/rooms/46951758,20230319041206,2023-03-19,city scrape,Boutique Style Home - Rooftop w/Breathtaking Views,"Explore or get settled in this artsy modern row home in DC in close proximity to Starbucks, Anacostia Metro, Busboys and Poets, and the Anacostia River and Park. This uniquely decorated home is perched upon one of the highest points in DC and features oak hardwood floors, oversized custom windows, modern furniture, and a stunningly finished rooftop deck. Experience all DC has to offer as you unwind atop this sleek row home and enjoy the clear/crisp views of our Nation's Capital.<br /><br /><b>The space</b><br />The house was built with custom moldings, hardwood floors, and lots of character. The panoramic rooftop view of DC, Virginia, and Maryland is remarkable and pairs well with wine or whiskey.<br /><br /><b>Guest access</b><br />N/A<br /><br /><b>Other things to note</b><br />There is one reserved parking space for the property. For additional vehicles, there is available street parking located outside of the community.<br /><br /><b>License number</b><br />Hosted License: 50072422","Food & Drinks: Starbucks, Mama's Pizza, Busboy and Poets, Bluejacket, Due South, Dockside, TaKorean, Ice Cream Jubilee, Whaley’s District Winery, Sushi Hachi, CAVA<br /><br />Entertainment: Nationals Park, Audi Field, Anacostia River, The Fridge, Canal Park, Trapeze School, The Yard, Park District, Wharf, VIDA Fitness, Anthem<br /><br />Shopping: Harris Teeter, Whole Foods Market, CVS Pharmacy, Lululemon, Willow, Unleashed by Petco, Conte’s Bike Shop",https://a0.muscache.com/pictures/miso/Hosting-46951758/original/e0245daa-ace9-4560-aeed-2e2a5ab97dc6.jpeg,55133178,https://www.airbnb.com/users/show/55133178,Quinton,2016-01-18,"Washington, DC","",within an hour,100%,100%,f,https://a0.muscache.com/im/pictures/user/267e0ae0-63d1-44cc-84e5-43e18c006fd6.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/267e0ae0-63d1-44cc-84e5-43e18c006fd6.jpg?aki_policy=profile_x_medium,Southeast Washington,1,2,"['email', 'phone']",t,t,"Washington, District of Columbia, United States",Historic Anacostia,,38.8634,-76.99187,Entire townhouse,Entire home/apt,8,,2.5 baths,3,3,"[""Bathtub"", ""Ethernet connection"", ""Hammock"", ""Air conditioning"", ""Private entrance"", ""Baking sheet"", ""Long term stays allowed"", ""TV"", ""Sun loungers"", ""BBQ grill: charcoal, gas"", ""Books and reading material"", ""Carbon monoxide alarm"", ""Room-darkening shades"", ""Clothing storage"", ""Laundromat nearby"", ""Bed linens"", ""Smoke alarm"", ""Outdoor dining area"", ""Free street parking"", ""Microwave"", ""Shampoo"", ""Waterfront"", ""Hair dryer"", ""First aid kit"", ""Stainless steel oven"", ""Barbecue utensils"", ""Cooking basics"", ""Dishwasher"", ""Outdoor furniture"", ""Extra pillows and blankets"", ""Dedicated workspace"", ""Refrigerator"", ""Cleaning products"", ""Hot water"", ""Free parking on premises"", ""Hangers"", ""Dishes and silverware"", ""Freezer"", ""Heating"", ""Lockbox"", ""Washer"", ""Ceiling fan"", ""Dining table"", ""Fire extinguisher"", ""Essentials"", ""Kitchen"", ""Pack \u2019n play/Travel crib - always at the listing"", ""City skyline view"", ""Security cameras on property"", ""Wifi"", ""Dryer"", ""Iron"", ""Self check-in"", ""Coffee maker: Keurig coffee machine"", ""Private patio or balcony"", ""Stove"", ""Coffee""]",$185.00,2,1125,2,2,1125,1125,2.0,1125.0,,t,10,27,53,306,2023-03-19,51,33,2,2020-12-20,2023-03-05,4.73,4.82,4.61,4.86,4.82,4.51,4.8,"Hosted License: 5007242201002380
Unhosted License: 5007262201002381",f,1,1,0,0,1.87
580379638076900630,https://www.airbnb.com/rooms/580379638076900630,20230319041206,2023-03-19,city scrape,Sojourn | Penthouse | Private Outdoor Space | Free Parking,"Boutique building in one of DC's best neighborhoods. Corner penthouse spacious 2 bed / 2 bath unit with over 1,150 sf of living space with bonus 200sf rooftop terrace (great outdoor space) and 1 underground parking space.  Beautiful kitchen with granite counters, cherry cabinets, Viking appliances, gas cooking with eat-in style with seating for four. Hardwood floors throughout.  Nicely apportioned bedrooms. Bathrooms with granite vanities. Dual vanity in main bathroom and with frameless glass shower enclosure. Custom roller shades, 2 Walk-in Closets, and in unit washer and dryer. Fully appointed kitchen, king bed, two twin beds that we can convert into a king, feather pillows, feather duvets, SevenFold towels and Lather soaps. Building includes Gym/Weight room, secure building access.<br /><br /><b>The space</b><br />All Sojourn cleaners are certified in cleaning practices based on guidelines from The World Health Organization, Center for Disease Control and Prevention, US Occupational","Dupont Circle stands out as a cosmopolitan jewel in DC’s distinctive collection of neighborhoods. With a famous traffic circle and fountain at its center, the Dupont Circle neighborhood has been a vital DC community since the late 19th century, and continues to be a hot spot for residents and visitors of all ages. Getting there is easy. Take the Metro to the Red Line stop, ride the Dupont Circle-Georgetown-Rosslyn DC Circulator bus route, use Capital Bikeshare or walk.",https://a0.muscache.com/pictures/prohost-api/Hosting-580379638076900630/original/501ea353-ed31-4bca-aeeb-930d37beb253.jpeg,39930655,https://www.airbnb.com/users/show/39930655,Team,2015-07-29,"Washington, DC","Hi, I'm Nicole, the co-founder of Sojourn.  At Sojourn, we understand how being away from home and routine can be disruptive to your being, which is why we have made our raison d’etre about making your temporary stay seamless and fluid. We are, at our core, about hospitality! A Sojourn space is carefully curated, thoughtfully designed, complete with beautiful and comfortable furniture. You will find fully equipped kitchens, superior quality mattresses, high quality linens and luxury towels. We have built Sojourn around understanding your unique needs and expectations. We can and will cater our services to ensure that you have everything you need to settle in and enjoy your Sojourn.

",within an hour,99%,100%,f,https://a0.muscache.com/im/pictures/user/adc0efa0-2e36-4aa0-9352-79ced76e02f8.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/adc0efa0-2e36-4aa0-9352-79ced76e02f8.jpg?aki_policy=profile_x_medium,Dupont Circle,251,289,"['email', 'phone']",t,t,"Washington, District of Columbia, United States","Dupont Circle, Connecticut Avenue/K Street",,38.90705,-77.04237,Entire rental unit,Entire home/apt,4,,2 baths,2,2,"[""Bathtub"", ""Air conditioning"", ""Private entrance"", ""Long term stays allowed"", ""Carbon monoxide alarm"", ""Room-darkening shades"", ""Bed linens"", ""Smoke alarm"", ""Microwave"", ""Shampoo"", ""Hair dryer"", ""First aid kit"", ""Cooking basics"", ""Dishwasher"", ""Keypad"", ""TV with standard cable"", ""Extra pillows and blankets"", ""Dedicated workspace"", ""Refrigerator"", ""Oven"", ""Free parking on premises"", ""Pack \u2019n play/Travel crib"", ""Hangers"", ""Dishes and silverware"", ""Patio or balcony"", ""Heating"", ""Washer"", ""Coffee maker"", ""Luggage dropoff allowed"", ""Fire extinguisher"", ""Essentials"", ""Kitchen"", ""High chair"", ""Wifi"", ""Dryer"", ""Iron"", ""Self check-in"", ""Stove"", ""Gym""]",$221.00,181,365,181,181,365,365,181.0,365.0,,t,18,48,78,353,2023-03-19,0,0,0,,,,,,,,,,,f,173,154,13,5,
594971943284098653,https://www.airbnb.com/rooms/594971943284098653,20230319041206,2023-03-19,city scrape,Quaint 1-bedroom apartment with outdoor Patio,"Welcome to the center of DC. Half-way between the Convention Center and U-Street, you'll have plenty of options for bars and restaurants at your doorstep.<br /><br />Never too far from anything, you won't need a vehicle to get around the city if you stay here.<br /><br />Grocery Store, Restuarants, Bars, even a wonderful local church are all in walking distance.<br /><br />If you want to live like a real Washingtonian, come stay with us!<br /><br /><b>License number</b><br />Hosted License: 5007242201002106<br />Unhosted License: 5007262201002107",,https://a0.muscache.com/pictures/5746a258-d2f7-4a8e-91dd-7d0ec50fe9b7.jpg,351398058,https://www.airbnb.com/users/show/351398058,Ladi,2020-06-22,"Washington, DC","",within an hour,100%,100%,t,https://a0.muscache.com/im/pictures/user/c497c4e7-221f-41b7-b503-08d0c535f1c9.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/c497c4e7-221f-41b7-b503-08d0c535f1c9.jpg?aki_policy=profile_x_medium,Northwest Washington,3,4,"['email', 'phone']",t,t,,"Shaw, Logan Circle",,38.91032,-77.0204,Entire guest suite,Entire home/apt,3,,1 bath,1,2,"[""Fire extinguisher"", ""Kitchen"", ""Air conditioning"", ""First aid kit"", ""Wifi"", ""Carbon monoxide alarm"", ""Smoke alarm"", ""Outdoor dining area""]",$142.00,1,1125,1,1,1125,1125,1.0,1125.0,,t,1,1,1,162,2023-03-19,11,11,4,2022-06-19,2023-03-08,4.82,4.82,4.36,4.91,5.0,4.73,4.73,"Hosted License: 5007242201002106
Unhosted License: 5007262201002107",t,3,2,1,0,1.20
54371126,https://www.airbnb.com/rooms/54371126,20230319041206,2023-03-19,city scrape,Waterfront Two Bedroom Apartment In a Brand New Building,"Located in Washington in the District of Columbia region, the Apartment features accommodation with free WiFi. Each unit offers a fully equipped kitchen, a flat-screen TV with FREE NETFLIX, a living room with a sofa, a private bathroom and a washing machine.<br /><br /><b>The space</b><br />Some units feature a seating area and/or a terrace. Guests can make use of the hot tub and fitness centre. Guests can also relax in the garden, beside the outdoor swimming pool, or in the shared lounge area. 2 minutes walk to the Metro Station and Waterfront<br /><br />“We manage multiple apartments in this building and neighborhood. You will be allotted one of the many apartment at this address. It maybe be possible that the photos are not a exact match since the layout of various apartments is different. However the size, area, facilities and amenities of all apartment is the same. By reserving this property, the guest agrees that they are acceptable to the fact that photos may not exactly match t",,https://a0.muscache.com/pictures/prohost-api/Hosting-54371126/original/028b9285-535c-4f2e-9c24-a78da21302f4.jpeg,395672427,https://www.airbnb.com/users/show/395672427,RedAwning,2021-04-05,"Emeryville, CA","Hosted by RedAwning Vacation Rentals

Welcome to RedAwning, a whole new way to travel. We make staying in a unique home or apartment easier than staying at a hotel. By partnering with local homeowners throughout North America, we provide you with the largest collection of vacation homes in the most destinations.  Every stay includes our experienced 24/7 customer assistance by text, chat, email and phone, and access to all your travel details via our free mobile app. We offer consistent terms and flexible cancellation policies, and we include accidental damage protection for every stay with no security deposits and a best rate guarantee. Wherever you want to go, RedAwning is here to make your journey easier!",N/A,N/A,N/A,f,https://a0.muscache.com/im/pictures/user/c330a930-2b49-4c86-87a2-43b488ebb57e.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/c330a930-2b49-4c86-87a2-43b488ebb57e.jpg?aki_policy=profile_x_medium,Mid-Beach,1408,2586,"['email', 'phone']",t,f,,"Southwest Employment Area, Southwest/Waterfront, Fort McNair, Buzzard Point",,38.876301,-77.014702,Entire rental unit,Entire home/apt,5,,2 baths,2,3,"[""Bathtub"", ""Pool"", ""Air conditioning"", ""Private entrance"", ""TV"", ""Carbon monoxide alarm"", ""Elevator"", ""Toaster"", ""Bed linens"", ""Smoke alarm"", ""Microwave"", ""Shampoo"", ""Hair dryer"", ""Pets allowed"", ""Cooking basics"", ""Dishwasher"", ""Refrigerator"", ""Oven"", ""Dishes and silverware"", ""Heating"", ""Washer"", ""Coffee maker"", ""Hot tub"", ""BBQ grill"", ""Fire extinguisher"", ""Essentials"", ""Kitchen"", ""Wifi"", ""Dryer"", ""Iron"", ""Gym""]",$398.00,1,365,1,3,3,365,1.3,306.5,,t,5,15,35,72,2023-03-19,1,1,0,2023-01-16,2023-01-16,5.0,5.0,5.0,5.0,5.0,5.0,5.0,Unhosted License: 5007242100000024,t,7,7,0,0,0.48
46428174,https://www.airbnb.com/rooms/46428174,20230319041206,2023-03-19,city scrape,Central DC Shaw Condo | Longterm Furnished,"Historic Shaw Rowhouse in the heart of Washington, DC. This bright and airy one bedroom, one bathroom apartment is just steps from Mt Vernon 7-St Metro Station, DC Convention Center, dog park, recreational parks, and all the restaurants/nightlife on K Street and downtown.<br /><br />Perfect for nurses, interns, students, relocation, and corporate travelers in the center of the city. The apartment has a desk to accommodate our work from home environment.<br /><br /><b>The space</b><br />Available for bookings over 31 nights. Pay $0 in DC lodging tax on bookings over 91 nights<br /><br />Building & Amenities Summary:<br />- Rowhouse condo<br />- Entire first floor with a private outdoor patio<br />- Equipped with smart locks for speedy self check-in and access<br />- Equipped with ultra-fast wifi internet<br />- In-unit washer and dryer<br />- Fully furnished; kitchen with stainless steel appliances<br />- Coffee maker<br />- A desk to accommodate work from home environment<br /><br />• ","Steeped in history but firmly rooted in the now, Shaw / Mt Vernon charms visitors and locals alike. Elegant row homes and the city’s hottest restaurants and bars. Everything you need--from specialty shops and grocers to a gym and coffee shop--is a pleasant stroll away.",https://a0.muscache.com/pictures/b24a2e32-3bf9-45e4-b576-ce9ff2d3bc6d.jpg,9680354,https://www.airbnb.com/users/show/9680354,Adam,2013-10-28,"Washington, DC","Business consultant. Former Air Force officer. Enjoy traveling, working out and spending time with friends.
",within an hour,100%,100%,t,https://a0.muscache.com/im/pictures/user/fd2d1102-8f83-4adf-bfb4-ded94b0ff3e1.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/fd2d1102-8f83-4adf-bfb4-ded94b0ff3e1.jpg?aki_policy=profile_x_medium,Northwest Washington,13,16,"['email', 'phone']",t,t,"Washington, District of Columbia, United States","Shaw, Logan Circle",,38.907686640730354,-77.01615416263996,Entire guest suite,Entire home/apt,2,,1 bath,1,1,"[""Bathtub"", ""Air conditioning"", ""Private entrance"", ""Baking sheet"", ""Long term stays allowed"", ""TV"", ""Carbon monoxide alarm"", ""Room-darkening shades"", ""Clothing storage"", ""Toaster"", ""Bed linens"", ""Smoke alarm"", ""Outdoor dining area"", ""Microwave"", ""Shampoo"", ""Paid parking garage off premises"", ""Hair dryer"", ""Pets allowed"", ""First aid kit"", ""Shower gel"", ""Cooking basics"", ""Dishwasher"", ""Conditioner"", ""Outdoor furniture"", ""Keypad"", ""Extra pillows and blankets"", ""Dedicated workspace"", ""Refrigerator"", ""Cleaning products"", ""Hot water"", ""Oven"", ""Body soap"", ""Hangers"", ""Dishes and silverware"", ""Freezer"", ""Heating"", ""Shared patio or balcony"", ""Washer"", ""Coffee maker"", ""Backyard"", ""Luggage dropoff allowed"", ""Fire extinguisher"", ""Essentials"", ""Kitchen"", ""Security cameras on property"", ""Wifi"", ""Dryer"", ""Iron"", ""Self check-in"", ""Stove"", ""Laundromat nearby""]",$89.00,31,1125,31,120,1125,1125,88.0,1125.0,,t,0,0,10,235,2023-03-19,38,8,0,2021-02-28,2022-10-23,4.82,4.79,4.87,5.0,5.0,4.92,4.79,Hosted License: 5007242201001021,t,13,13,0,0,1.52
40341225,https://www.airbnb.com/rooms/40341225,20230319041206,2023-03-19,city scrape,"Curated Two Story, Two Bedroom Row House","Enjoy this spacious unit within this 2-story row house. Two bedrooms, four beds, an open concept living room/kitchen, and inviting interiors make this a place you will want to call home again.<br /><br />- fully equipped kitchen<br />- high-speed 5GHz WIFI <br />- contactless self-check-in<br />- family-friendly amenities (baby crib, high chair, covered outlets) <br /><br />PARTIES, GATHERINGS, AND NOISY GUESTS ARE STRICTLY PROHIBITED. Fines will be charged for noise violations. Max occupancy 7.<br /><br /><b>The space</b><br />The master bedroom features a King bed, on-suite bathroom, and generous closet space with Elfa closet system. The master bathroom features a stand-up shower and expansive vanity with his-and-hers sinks.<br /><br />The second bedroom features two full-size beds, a dresser, large closet, and an on-suite bathroom. This bathroom features a tub/shower combo and his-and-hers sinks.<br /><br />Expansive wall-to-wall windows in both bedrooms funnel loads of natural ligh","Situated in Edgewood along the Rhode Island Avenue corridor we enjoy proximity to Trinity University (0.6 miles), Catholic University (1 mile) and are minutes to the national mall (2.6 miles) and historic monuments downtown.",https://a0.muscache.com/pictures/66d47cec-b115-4cca-906f-1323ef854ade.jpg,32935630,https://www.airbnb.com/users/show/32935630,Lauren,2015-05-08,"Washington, DC",I enjoy curating welcoming spaces for travelers and ensuring guests have great stays!,within an hour,100%,93%,t,https://a0.muscache.com/im/pictures/user/77c9819e-4f63-4636-82aa-c69cc315c74c.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/77c9819e-4f63-4636-82aa-c69cc315c74c.jpg?aki_policy=profile_x_medium,Edgewood,5,9,"['email', 'phone']",t,t,"Washington, District of Columbia, United States","Edgewood, Bloomingdale, Truxton Circle, Eckington",,38.92354,-77.00366,Entire townhouse,Entire home/apt,7,,2.5 baths,2,4,"[""Bathtub"", ""Clothing storage: closet and dresser"", ""Air conditioning"", ""Private entrance"", ""Baking sheet"", ""TV"", ""Books and reading material"", ""Carbon monoxide alarm"", ""Room-darkening shades"", ""Bed linens"", ""Smoke alarm"", ""Free street parking"", ""Crib"", ""Microwave"", ""Shampoo"", ""Hair dryer"", ""Outlet covers"", ""First aid kit"", ""Pets allowed"", ""Barbecue utensils"", ""Shower gel"", ""Cooking basics"", ""Children\u2019s books and toys"", ""Dishwasher"", ""Extra pillows and blankets"", ""Refrigerator"", ""Cleaning products"", ""Hot water"", ""Oven"", ""Free parking on premises"", ""Body soap"", ""Hangers"", ""Dishes and silverware"", ""Patio or balcony"", ""Heating"", ""Smart lock"", ""Coffee maker"", ""Board games"", ""Fire extinguisher"", ""Essentials"", ""Kitchen"", ""High chair"", ""Safe"", ""Exercise equipment: free weights, yoga mat"", ""Wifi"", ""Iron"", ""Self check-in"", ""Stove""]",$198.00,31,180,31,31,1125,1125,31.0,1125.0,,t,5,14,27,84,2023-03-19,45,21,0,2020-01-20,2022-10-09,4.76,4.8,4.76,4.91,4.98,4.78,4.76,,f,2,2,0,0,1.17
46004444,https://www.airbnb.com/rooms/46004444,20230319041206,2023-03-19,city scrape,"Yours Truly DC, 2 Bedroom Master Suite","Our hotel in Northwest DC invites you to make yourself at home. From the moment you put down your bags, we want you to feel settled. Here you'll find a hotel built and programmed like a house - kitchen and all. This space is yours, truly.<br /><br />This is listing includes 2 of our adjoining suites: King Suite and Premium King or Premium Double Queen (let us know which one you prefer). It comes with 2 bedrooms, 1 living room, and 2.5 bathrooms. There's a sofa bed in the living room.<br /><br /><b>The space</b><br />With pet-friendly rooms available, you can plan the perfect getaway with a comfortable stay at our hotel near the White House, National Mall, Smithsonian Museums and Georgetown.<br /><br /><b>Guest access</b><br />- Mercy Me ""a Sorta-South American"" Restaurant & Cafe<br />- 24/7 Gym<br />- Living Room & Outdoor Patio Access<br />- El Donut Shoppe Record Store<br /><br /><b>Other things to note</b><br />Guests must provide a government-issued ID and a valid credit card upon ",,https://a0.muscache.com/pictures/c93e3e91-1932-46b5-9a55-27c09304b298.jpg,268577141,https://www.airbnb.com/users/show/268577141,Yours Truly,2019-06-14,"Washington, DC","Yours Truly, Y(our) House
Our hotel in Northwest DC invites you to make yourself at home. From the moment you put down your bags, we want you to feel settled. Here you'll find a hotel built and programmed like a house - kitchen and all. So do what you like and we're here for your needs. This space is yours, truly.

Find us on (Hidden by Airbnb) : @yourstrulyhotel",N/A,N/A,80%,f,https://a0.muscache.com/im/pictures/user/a5c112b9-ef8f-43af-aadc-46ab8dd47d2b.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/a5c112b9-ef8f-43af-aadc-46ab8dd47d2b.jpg?aki_policy=profile_x_medium,Downtown/Penn Quarter,10,10,"['email', 'phone']",t,t,,"West End, Foggy Bottom, GWU",,38.90575,-77.04831,Room in boutique hotel,Private room,6,,2.5 shared baths,2,4,"[""Essentials"", ""Building staff"", ""Crib"", ""Lock on bedroom door"", ""Shampoo"", ""Air conditioning"", ""Hair dryer"", ""Pets allowed"", ""TV"", ""Wifi"", ""Private living room"", ""Hangers"", ""Heating"", ""Iron"", ""Self check-in"", ""Gym""]",$750.00,31,1125,31,31,1125,1125,31.0,1125.0,,t,30,60,90,365,2023-03-19,8,1,0,2020-11-08,2022-05-16,4.75,4.5,4.5,4.88,4.88,5.0,4.38,,t,10,0,10,0,0.28
48010456,https://www.airbnb.com/rooms/48010456,20230319041206,2023-03-19,city scrape,"Completely Private, 1BD&1BA, near Catholic Univ.","Modern and updated upstairs unit in a  quite neighborhood. The spacious corner house provides the perfect balance of city living and suburbia.<br /><br />Easy access to all DC attractions, close to Catholic University,  Metro & recreation center.<br /><br />Kitchen is fully loaded with all major appliances, dishwasher and dishware.<br /><br />No washer and dryer. No shared amenties. Free Street parking. <br />Absolutley No Parties & No Pets. Fee applies. <br /><br />Basement unit (2BD, 2BA) available for rental separately.<br /><br /><b>License number</b><br />Hosted License: 5007242201001848",,https://a0.muscache.com/pictures/ae29592d-ecf9-4889-9150-536ec52edcb9.jpg,384301691,https://www.airbnb.com/users/show/384301691,Zecarias,2021-01-12,,"",within an hour,100%,100%,f,https://a0.muscache.com/im/pictures/user/c8952bea-b26b-401c-b9bd-54dc2854c232.jpg?aki_policy=profile_small,https://a0.muscache.com/im/pictures/user/c8952bea-b26b-401c-b9bd-54dc2854c232.jpg?aki_policy=profile_x_medium,Northeast Washington,2,2,"['email', 'phone']",t,t,,"North Michigan Park, Michigan Park, University Heights",,38.94091,-76.9733,Entire home,Entire home/apt,5,,1 bath,1,1,"[""Bathtub"", ""Single level home"", ""Air conditioning"", ""Private entrance"", ""Long term stays allowed"", ""TV"", ""Private backyard"", ""Carbon monoxide alarm"", ""Smoke alarm"", ""Free street parking"", ""Crib"", ""Microwave"", ""Shampoo"", ""Hair dryer"", ""Stainless steel oven"", ""Shower gel"", ""Cooking basics"", ""Dishwasher"", ""Extra pillows and blankets"", ""Clothing storage: closet"", ""Dedicated workspace"", ""Refrigerator"", ""Hot water"", ""Free parking on premises"", ""Dishes and silverware"", ""Freezer"", ""Lockbox"", ""Heating"", ""Gas stove"", ""Coffee maker"", ""Fire extinguisher"", ""Essentials"", ""Kitchen"", ""Safe"", ""Wifi"", ""Iron"", ""Wine glasses"", ""Self check-in"", ""Coffee""]",$138.00,3,300,3,3,1125,1125,3.0,1125.0,,t,2,32,62,337,2023-03-19,18,10,0,2021-02-15,2022-11-08,4.78,4.78,4.94,4.67,4.83,4.78,4.61,Hosted License: 5007242201001848,f,2,2,0,0,0.71
```

## Analysis
1. show exactly two documents from the listings collection in any order <br>
The code used to perform it: <br>
```js
db.listings.find().limit(2);
```
The results:<br>
```js
{ "_id" : ObjectId("64407bd124ed49838647ed1e"), "id" : NumberLong("594971943284098653"), "listing_url" : "https://www.airbnb.com/rooms/594971943284098653", "scrape_id" : NumberLong("20230319041206"), "last_scraped" : "2023-03-19", "source" : "city scrape", "name" : "Quaint 1-bedroom apartment with outdoor Patio", "description" : "Welcome to the center of DC. Half-way between the Convention Center and U-Street, you'll have plenty of options for bars and restaurants at your doorstep.<br /><br />Never too far from anything, you won't need a vehicle to get around the city if you stay here.<br /><br />Grocery Store, Restuarants, Bars, even a wonderful local church are all in walking distance.<br /><br />If you want to live like a real Washingtonian, come stay with us!<br /><br /><b>License number</b><br />Hosted License: 5007242201002106<br />Unhosted License: 5007262201002107", "neighborhood_overview" : "", "picture_url" : "https://a0.muscache.com/pictures/5746a258-d2f7-4a8e-91dd-7d0ec50fe9b7.jpg", "host_id" : 351398058, "host_url" : "https://www.airbnb.com/users/show/351398058", "host_name" : "Ladi", "host_since" : "2020-06-22", "host_location" : "Washington, DC", "host_about" : "", "host_response_time" : "within an hour", "host_response_rate" : "100%", "host_acceptance_rate" : "100%", "host_is_superhost" : "t", "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/user/c497c4e7-221f-41b7-b503-08d0c535f1c9.jpg?aki_policy=profile_small", "host_picture_url" : "https://a0.muscache.com/im/pictures/user/c497c4e7-221f-41b7-b503-08d0c535f1c9.jpg?aki_policy=profile_x_medium", "host_neighbourhood" : "Northwest Washington", "host_listings_count" : 3, "host_total_listings_count" : 4, "host_verifications" : "['email', 'phone']", "host_has_profile_pic" : "t", "host_identity_verified" : "t", "neighbourhood" : "", "neighbourhood_cleansed" : "Shaw, Logan Circle", "neighbourhood_group_cleansed" : "", "latitude" : 38.91032, "longitude" : -77.0204, "property_type" : "Entire guest suite", "room_type" : "Entire home/apt", "accommodates" : 3, "bathrooms" : "", "bathrooms_text" : "1 bath", "bedrooms" : 1, "beds" : 2, "amenities" : "[\"Fire extinguisher\", \"Kitchen\", \"Air conditioning\", \"First aid kit\", \"Wifi\", \"Carbon monoxide alarm\", \"Smoke alarm\", \"Outdoor dining area\"]", "price" : "$142.00", "minimum_nights" : 1, "maximum_nights" : 1125, "minimum_minimum_nights" : 1, "maximum_minimum_nights" : 1, "minimum_maximum_nights" : 1125, "maximum_maximum_nights" : 1125, "minimum_nights_avg_ntm" : 1, "maximum_nights_avg_ntm" : 1125, "calendar_updated" : "", "has_availability" : "t", "availability_30" : 1, "availability_60" : 1, "availability_90" : 1, "availability_365" : 162, "calendar_last_scraped" : "2023-03-19", "number_of_reviews" : 11, "number_of_reviews_ltm" : 11, "number_of_reviews_l30d" : 4, "first_review" : "2022-06-19", "last_review" : "2023-03-08", "review_scores_rating" : 4.82, "review_scores_accuracy" : 4.82, "review_scores_cleanliness" : 4.36, "review_scores_checkin" : 4.91, "review_scores_communication" : 5, "review_scores_location" : 4.73, "review_scores_value" : 4.73, "license" : "Hosted License: 5007242201002106\nUnhosted License: 5007262201002107", "instant_bookable" : "t", "calculated_host_listings_count" : 3, "calculated_host_listings_count_entire_homes" : 2, "calculated_host_listings_count_private_rooms" : 1, "calculated_host_listings_count_shared_rooms" : 0, "reviews_per_month" : 1.2 }
{ "_id" : ObjectId("64407bd124ed49838647ed1b"), "id" : 22229408, "listing_url" : "https://www.airbnb.com/rooms/22229408", "scrape_id" : NumberLong("20230319041206"), "last_scraped" : "2023-03-19", "source" : "previous scrape", "name" : "Explorer's Paradise: Near Train, Bus & Bike Share", "description" : "Welcome to your perfect urban escape in the Nation’s Capital! Only .4 miles (10 min walk) from the Metro train & Capital Bikeshare, and a 10 min Metro ride to major DC attractions, this oasis has all you need to enjoy a weekend or extended stay. Perfect space for singles and couples.<br /><br /><b>Guest access</b><br />This remodeled home has 2 stories of space to enjoy when staying here for your visit in the DC area. Guests have own private room that includes: queen bed with high quality bed linens/blankets, ceiling fan, private closet with hamper and ample clothes hangers, luggage rack, and full-length mirror. Adjacent to the guest room is a completely remodeled bathroom, just for use by guests, furnished with plush towels and hair dryer. Bedroom and bathroom are on the upper story of the home. The other shared areas that are accessible to our guests, include a quaint front porch, that is perfect for unwinding in the evening, and a calm and comfortable living /dining room.<br /><br /", "neighborhood_overview" : "My home is located in the Edgewood neighborhood of DC. Upon first glance, some people see it as a bit rough around the edges, but the business owners and neighbors are all very friendly. The neighborhood was once the estate of Salmon P. Chase: statesman, abolitionist and jurist. The neighborhood arose with the establishment of the Metropolitan Branch Line of the C&O Railroad in 1873. This line now includes the Metropolitan Branch Trail (a biking and walking trail) and the red line of the metro (subway). Within a few blocks are grocery stores, dry cleaners, drug stores, etc. There are many nearby options for eating and shopping.<br />Directly at the Rhode Island Metro Station, you will find a CVS, Home Depot, major grocery store, TJ Maxx, a wonderful nail salon and sit-down and fast casual restaurants, including Salathai, Chipotle, and Carolina Kitchen among other options.<br /><br />A 15-min walk in one direction takes to you the heart of Bloomingdale, where you will find great places ", "picture_url" : "https://a0.muscache.com/pictures/8e49b7bc-a851-4e46-a8b6-76ea88c96124.jpg", "host_id" : 120875011, "host_url" : "https://www.airbnb.com/users/show/120875011", "host_name" : "J. P.", "host_since" : "2017-03-15", "host_location" : "Washington, DC", "host_about" : "", "host_response_time" : "N/A", "host_response_rate" : "N/A", "host_acceptance_rate" : "N/A", "host_is_superhost" : "f", "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/user/ba485797-0a7c-4867-acce-9f3dd3cd5511.jpg?aki_policy=profile_small", "host_picture_url" : "https://a0.muscache.com/im/pictures/user/ba485797-0a7c-4867-acce-9f3dd3cd5511.jpg?aki_policy=profile_x_medium", "host_neighbourhood" : "Edgewood", "host_listings_count" : 1, "host_total_listings_count" : 2, "host_verifications" : "['email', 'phone']", "host_has_profile_pic" : "t", "host_identity_verified" : "f", "neighbourhood" : "Washington, District of Columbia, United States", "neighbourhood_cleansed" : "Edgewood, Bloomingdale, Truxton Circle, Eckington", "neighbourhood_group_cleansed" : "", "latitude" : 38.92217, "longitude" : -77.00045, "property_type" : "Private room in townhouse", "room_type" : "Private room", "accommodates" : 2, "bathrooms" : "", "bathrooms_text" : "1 private bath", "bedrooms" : 1, "beds" : 1, "amenities" : "[\"Essentials\", \"Shampoo\", \"Air conditioning\", \"Hair dryer\", \"TV\", \"Wifi\", \"Lockbox\", \"Heating\", \"Carbon monoxide alarm\", \"Iron\", \"Self check-in\", \"Smoke alarm\", \"Free street parking\"]", "price" : "$20.00", "minimum_nights" : 31, "maximum_nights" : 150, "minimum_minimum_nights" : 31, "maximum_minimum_nights" : 31, "minimum_maximum_nights" : 150, "maximum_maximum_nights" : 150, "minimum_nights_avg_ntm" : 31, "maximum_nights_avg_ntm" : 150, "calendar_updated" : "", "has_availability" : "t", "availability_30" : 0, "availability_60" : 0, "availability_90" : 0, "availability_365" : 0, "calendar_last_scraped" : "2023-03-19", "number_of_reviews" : 20, "number_of_reviews_ltm" : 0, "number_of_reviews_l30d" : 0, "first_review" : "2018-01-11", "last_review" : "2021-06-30", "review_scores_rating" : 4.85, "review_scores_accuracy" : 4.65, "review_scores_cleanliness" : 4.9, "review_scores_checkin" : 4.95, "review_scores_communication" : 4.85, "review_scores_location" : 4.75, "review_scores_value" : 4.75, "license" : "", "instant_bookable" : "f", "calculated_host_listings_count" : 1, "calculated_host_listings_count_entire_homes" : 0, "calculated_host_listings_count_private_rooms" : 1, "calculated_host_listings_count_shared_rooms" : 0, "reviews_per_month" : 0.32 }
```

2. show exactly 10 documents in any order, but "prettyprint" in easier to read format, using the pretty() function. <br>
The code used to perform it: <br>
```js
db.listings.find().limit(10).pretty();
```
The first 3 results: <br>
```js
{
        "_id" : ObjectId("64407bd124ed49838647ed1e"),
        "id" : NumberLong("594971943284098653"),
        "listing_url" : "https://www.airbnb.com/rooms/594971943284098653",
        "scrape_id" : NumberLong("20230319041206"),
        "last_scraped" : "2023-03-19",
        "source" : "city scrape",
        "name" : "Quaint 1-bedroom apartment with outdoor Patio",
        "description" : "Welcome to the center of DC. Half-way between the Convention Center and U-Street, you'll have plenty of options for bars and restaurants at your doorstep.<br /><br />Never too far from anything, you won't need a vehicle to get around the city if you stay here.<br /><br />Grocery Store, Restuarants, Bars, even a wonderful local church are all in walking distance.<br /><br />If you want to live like a real Washingtonian, come stay with us!<br /><br /><b>License number</b><br />Hosted License: 5007242201002106<br />Unhosted License: 5007262201002107",
        "neighborhood_overview" : "",
        "picture_url" : "https://a0.muscache.com/pictures/5746a258-d2f7-4a8e-91dd-7d0ec50fe9b7.jpg",
        "host_id" : 351398058,
        "host_url" : "https://www.airbnb.com/users/show/351398058",
        "host_name" : "Ladi",
        "host_since" : "2020-06-22",
        "host_location" : "Washington, DC",
        "host_about" : "",
        "host_response_time" : "within an hour",
        "host_response_rate" : "100%",
        "host_acceptance_rate" : "100%",
        "host_is_superhost" : "t",
        "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/user/c497c4e7-221f-41b7-b503-08d0c535f1c9.jpg?aki_policy=profile_small",
        "host_picture_url" : "https://a0.muscache.com/im/pictures/user/c497c4e7-221f-41b7-b503-08d0c535f1c9.jpg?aki_policy=profile_x_medium",
        "host_neighbourhood" : "Northwest Washington",
        "host_listings_count" : 3,
        "host_total_listings_count" : 4,
        "host_verifications" : "['email', 'phone']",
        "host_has_profile_pic" : "t",
        "host_identity_verified" : "t",
        "neighbourhood" : "",
        "neighbourhood_cleansed" : "Shaw, Logan Circle",
        "neighbourhood_group_cleansed" : "",
        "latitude" : 38.91032,
        "longitude" : -77.0204,
        "property_type" : "Entire guest suite",
        "room_type" : "Entire home/apt",
        "accommodates" : 3,
        "bathrooms" : "",
        "bathrooms_text" : "1 bath",
        "bedrooms" : 1,
        "beds" : 2,
        "amenities" : "[\"Fire extinguisher\", \"Kitchen\", \"Air conditioning\", \"First aid kit\", \"Wifi\", \"Carbon monoxide alarm\", \"Smoke alarm\", \"Outdoor dining area\"]",
        "price" : "$142.00",
        "minimum_nights" : 1,
        "maximum_nights" : 1125,
        "minimum_minimum_nights" : 1,
        "maximum_minimum_nights" : 1,
        "minimum_maximum_nights" : 1125,
        "maximum_maximum_nights" : 1125,
        "minimum_nights_avg_ntm" : 1,
        "maximum_nights_avg_ntm" : 1125,
        "calendar_updated" : "",
        "has_availability" : "t",
        "availability_30" : 1,
        "availability_60" : 1,
        "availability_90" : 1,
        "availability_365" : 162,
        "calendar_last_scraped" : "2023-03-19",
        "number_of_reviews" : 11,
        "number_of_reviews_ltm" : 11,
        "number_of_reviews_l30d" : 4,
        "first_review" : "2022-06-19",
        "last_review" : "2023-03-08",
        "review_scores_rating" : 4.82,
        "review_scores_accuracy" : 4.82,
        "review_scores_cleanliness" : 4.36,
        "review_scores_checkin" : 4.91,
        "review_scores_communication" : 5,
        "review_scores_location" : 4.73,
        "review_scores_value" : 4.73,
        "license" : "Hosted License: 5007242201002106\nUnhosted License: 5007262201002107",
        "instant_bookable" : "t",
        "calculated_host_listings_count" : 3,
        "calculated_host_listings_count_entire_homes" : 2,
        "calculated_host_listings_count_private_rooms" : 1,
        "calculated_host_listings_count_shared_rooms" : 0,
        "reviews_per_month" : 1.2
}
{
        "_id" : ObjectId("64407bd124ed49838647ed1b"),
        "id" : 22229408,
        "listing_url" : "https://www.airbnb.com/rooms/22229408",
        "scrape_id" : NumberLong("20230319041206"),
        "last_scraped" : "2023-03-19",
        "source" : "previous scrape",
        "name" : "Explorer's Paradise: Near Train, Bus & Bike Share",
        "description" : "Welcome to your perfect urban escape in the Nation’s Capital! Only .4 miles (10 min walk) from the Metro train & Capital Bikeshare, and a 10 min Metro ride to major DC attractions, this oasis has all you need to enjoy a weekend or extended stay. Perfect space for singles and couples.<br /><br /><b>Guest access</b><br />This remodeled home has 2 stories of space to enjoy when staying here for your visit in the DC area. Guests have own private room that includes: queen bed with high quality bed linens/blankets, ceiling fan, private closet with hamper and ample clothes hangers, luggage rack, and full-length mirror. Adjacent to the guest room is a completely remodeled bathroom, just for use by guests, furnished with plush towels and hair dryer. Bedroom and bathroom are on the upper story of the home. The other shared areas that are accessible to our guests, include a quaint front porch, that is perfect for unwinding in the evening, and a calm and comfortable living /dining room.<br /><br /",
        "neighborhood_overview" : "My home is located in the Edgewood neighborhood of DC. Upon first glance, some people see it as a bit rough around the edges, but the business owners and neighbors are all very friendly. The neighborhood was once the estate of Salmon P. Chase: statesman, abolitionist and jurist. The neighborhood arose with the establishment of the Metropolitan Branch Line of the C&O Railroad in 1873. This line now includes the Metropolitan Branch Trail (a biking and walking trail) and the red line of the metro (subway). Within a few blocks are grocery stores, dry cleaners, drug stores, etc. There are many nearby options for eating and shopping.<br />Directly at the Rhode Island Metro Station, you will find a CVS, Home Depot, major grocery store, TJ Maxx, a wonderful nail salon and sit-down and fast casual restaurants, including Salathai, Chipotle, and Carolina Kitchen among other options.<br /><br />A 15-min walk in one direction takes to you the heart of Bloomingdale, where you will find great places ",
        "picture_url" : "https://a0.muscache.com/pictures/8e49b7bc-a851-4e46-a8b6-76ea88c96124.jpg",
        "host_id" : 120875011,
        "host_url" : "https://www.airbnb.com/users/show/120875011",
        "host_name" : "J. P.",
        "host_since" : "2017-03-15",
        "host_location" : "Washington, DC",
        "host_about" : "",
        "host_response_time" : "N/A",
        "host_response_rate" : "N/A",
        "host_acceptance_rate" : "N/A",
        "host_is_superhost" : "f",
        "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/user/ba485797-0a7c-4867-acce-9f3dd3cd5511.jpg?aki_policy=profile_small",
        "host_picture_url" : "https://a0.muscache.com/im/pictures/user/ba485797-0a7c-4867-acce-9f3dd3cd5511.jpg?aki_policy=profile_x_medium",
        "host_neighbourhood" : "Edgewood",
        "host_listings_count" : 1,
        "host_total_listings_count" : 2,
        "host_verifications" : "['email', 'phone']",
        "host_has_profile_pic" : "t",
        "host_identity_verified" : "f",
        "neighbourhood" : "Washington, District of Columbia, United States",
        "neighbourhood_cleansed" : "Edgewood, Bloomingdale, Truxton Circle, Eckington",
        "neighbourhood_group_cleansed" : "",
        "latitude" : 38.92217,
        "longitude" : -77.00045,
        "property_type" : "Private room in townhouse",
        "room_type" : "Private room",
        "accommodates" : 2,
        "bathrooms" : "",
        "bathrooms_text" : "1 private bath",
        "bedrooms" : 1,
        "beds" : 1,
        "amenities" : "[\"Essentials\", \"Shampoo\", \"Air conditioning\", \"Hair dryer\", \"TV\", \"Wifi\", \"Lockbox\", \"Heating\", \"Carbon monoxide alarm\", \"Iron\", \"Self check-in\", \"Smoke alarm\", \"Free street parking\"]",
        "price" : "$20.00",
        "minimum_nights" : 31,
        "maximum_nights" : 150,
        "minimum_minimum_nights" : 31,
        "maximum_minimum_nights" : 31,
        "minimum_maximum_nights" : 150,
        "maximum_maximum_nights" : 150,
        "minimum_nights_avg_ntm" : 31,
        "maximum_nights_avg_ntm" : 150,
        "calendar_updated" : "",
        "has_availability" : "t",
        "availability_30" : 0,
        "availability_60" : 0,
        "availability_90" : 0,
        "availability_365" : 0,
        "calendar_last_scraped" : "2023-03-19",
        "number_of_reviews" : 20,
        "number_of_reviews_ltm" : 0,
        "number_of_reviews_l30d" : 0,
        "first_review" : "2018-01-11",
        "last_review" : "2021-06-30",
        "review_scores_rating" : 4.85,
        "review_scores_accuracy" : 4.65,
        "review_scores_cleanliness" : 4.9,
        "review_scores_checkin" : 4.95,
        "review_scores_communication" : 4.85,
        "review_scores_location" : 4.75,
        "review_scores_value" : 4.75,
        "license" : "",
        "instant_bookable" : "f",
        "calculated_host_listings_count" : 1,
        "calculated_host_listings_count_entire_homes" : 0,
        "calculated_host_listings_count_private_rooms" : 1,
        "calculated_host_listings_count_shared_rooms" : 0,
        "reviews_per_month" : 0.32
}
{
        "_id" : ObjectId("64407bd124ed49838647ed1c"),
        "id" : 46951758,
        "listing_url" : "https://www.airbnb.com/rooms/46951758",
        "scrape_id" : NumberLong("20230319041206"),
        "last_scraped" : "2023-03-19",
        "source" : "city scrape",
        "name" : "Boutique Style Home - Rooftop w/Breathtaking Views",
        "description" : "Explore or get settled in this artsy modern row home in DC in close proximity to Starbucks, Anacostia Metro, Busboys and Poets, and the Anacostia River and Park. This uniquely decorated home is perched upon one of the highest points in DC and features oak hardwood floors, oversized custom windows, modern furniture, and a stunningly finished rooftop deck. Experience all DC has to offer as you unwind atop this sleek row home and enjoy the clear/crisp views of our Nation's Capital.<br /><br /><b>The space</b><br />The house was built with custom moldings, hardwood floors, and lots of character. The panoramic rooftop view of DC, Virginia, and Maryland is remarkable and pairs well with wine or whiskey.<br /><br /><b>Guest access</b><br />N/A<br /><br /><b>Other things to note</b><br />There is one reserved parking space for the property. For additional vehicles, there is available street parking located outside of the community.<br /><br /><b>License number</b><br />Hosted License: 50072422",
        "neighborhood_overview" : "Food & Drinks: Starbucks, Mama's Pizza, Busboy and Poets, Bluejacket, Due South, Dockside, TaKorean, Ice Cream Jubilee, Whaley’s District Winery, Sushi Hachi, CAVA<br /><br />Entertainment: Nationals Park, Audi Field, Anacostia River, The Fridge, Canal Park, Trapeze School, The Yard, Park District, Wharf, VIDA Fitness, Anthem<br /><br />Shopping: Harris Teeter, Whole Foods Market, CVS Pharmacy, Lululemon, Willow, Unleashed by Petco, Conte’s Bike Shop",
        "picture_url" : "https://a0.muscache.com/pictures/miso/Hosting-46951758/original/e0245daa-ace9-4560-aeed-2e2a5ab97dc6.jpeg",
        "host_id" : 55133178,
        "host_url" : "https://www.airbnb.com/users/show/55133178",
        "host_name" : "Quinton",
        "host_since" : "2016-01-18",
        "host_location" : "Washington, DC",
        "host_about" : "",
        "host_response_time" : "within an hour",
        "host_response_rate" : "100%",
        "host_acceptance_rate" : "100%",
        "host_is_superhost" : "f",
        "host_thumbnail_url" : "https://a0.muscache.com/im/pictures/user/267e0ae0-63d1-44cc-84e5-43e18c006fd6.jpg?aki_policy=profile_small",
        "host_picture_url" : "https://a0.muscache.com/im/pictures/user/267e0ae0-63d1-44cc-84e5-43e18c006fd6.jpg?aki_policy=profile_x_medium",
        "host_neighbourhood" : "Southeast Washington",
        "host_listings_count" : 1,
        "host_total_listings_count" : 2,
        "host_verifications" : "['email', 'phone']",
        "host_has_profile_pic" : "t",
        "host_identity_verified" : "t",
        "neighbourhood" : "Washington, District of Columbia, United States",
        "neighbourhood_cleansed" : "Historic Anacostia",
        "neighbourhood_group_cleansed" : "",
        "latitude" : 38.8634,
        "longitude" : -76.99187,
        "property_type" : "Entire townhouse",
        "room_type" : "Entire home/apt",
        "accommodates" : 8,
        "bathrooms" : "",
        "bathrooms_text" : "2.5 baths",
        "bedrooms" : 3,
        "beds" : 3,
        "amenities" : "[\"Bathtub\", \"Ethernet connection\", \"Hammock\", \"Air conditioning\", \"Private entrance\", \"Baking sheet\", \"Long term stays allowed\", \"TV\", \"Sun loungers\", \"BBQ grill: charcoal, gas\", \"Books and reading material\", \"Carbon monoxide alarm\", \"Room-darkening shades\", \"Clothing storage\", \"Laundromat nearby\", \"Bed linens\", \"Smoke alarm\", \"Outdoor dining area\", \"Free street parking\", \"Microwave\", \"Shampoo\", \"Waterfront\", \"Hair dryer\", \"First aid kit\", \"Stainless steel oven\", \"Barbecue utensils\", \"Cooking basics\", \"Dishwasher\", \"Outdoor furniture\", \"Extra pillows and blankets\", \"Dedicated workspace\", \"Refrigerator\", \"Cleaning products\", \"Hot water\", \"Free parking on premises\", \"Hangers\", \"Dishes and silverware\", \"Freezer\", \"Heating\", \"Lockbox\", \"Washer\", \"Ceiling fan\", \"Dining table\", \"Fire extinguisher\", \"Essentials\", \"Kitchen\", \"Pack \\u2019n play/Travel crib - always at the listing\", \"City skyline view\", \"Security cameras on property\", \"Wifi\", \"Dryer\", \"Iron\", \"Self check-in\", \"Coffee maker: Keurig coffee machine\", \"Private patio or balcony\", \"Stove\", \"Coffee\"]",
        "price" : "$185.00",
        "minimum_nights" : 2,
        "maximum_nights" : 1125,
        "minimum_minimum_nights" : 2,
        "maximum_minimum_nights" : 2,
        "minimum_maximum_nights" : 1125,
        "maximum_maximum_nights" : 1125,
        "minimum_nights_avg_ntm" : 2,
        "maximum_nights_avg_ntm" : 1125,
        "calendar_updated" : "",
        "has_availability" : "t",
        "availability_30" : 10,
        "availability_60" : 27,
        "availability_90" : 53,
        "availability_365" : 306,
        "calendar_last_scraped" : "2023-03-19",
        "number_of_reviews" : 51,
        "number_of_reviews_ltm" : 33,
        "number_of_reviews_l30d" : 2,
        "first_review" : "2020-12-20",
        "last_review" : "2023-03-05",
        "review_scores_rating" : 4.73,
        "review_scores_accuracy" : 4.82,
        "review_scores_cleanliness" : 4.61,
        "review_scores_checkin" : 4.86,
        "review_scores_communication" : 4.82,
        "review_scores_location" : 4.51,
        "review_scores_value" : 4.8,
        "license" : "Hosted License: 5007242201002380\nUnhosted License: 5007262201002381",
        "instant_bookable" : "f",
        "calculated_host_listings_count" : 1,
        "calculated_host_listings_count_entire_homes" : 1,
        "calculated_host_listings_count_private_rooms" : 0,
        "calculated_host_listings_count_shared_rooms" : 0,
        "reviews_per_month" : 1.87
}
```

3. choose two hosts (by reffering to their host_id values) who are superhosts (available in the host_is_superhost field), and show all of the listings offered by both of the two hosts <br>
only show the name, price, neighbourhood, host_name, and host_is_superhost for each result <br>
The code used to perform it: <br>
```js
//choose two hosts by this
db.listings.find({"host_is_superhost": "t"}, {host_id: 1}).limit(2);
//get the listings offered by both of the two hosts
db.listings.find(
    {host_id: {"$in" : [351398058, 9680354]}},
    {_id: 0, name: 1, price: 1, neighbourhood: 1, host_name: 1, host_is_superhost: 1}
).pretty();
```
The first 3 results: <br>
```js
{
        "name" : "Quaint 1-bedroom apartment with outdoor Patio",
        "host_name" : "Ladi",
        "host_is_superhost" : "t",
        "neighbourhood" : "",
        "price" : "$142.00"
}
{
        "name" : "Central DC Shaw Condo | Longterm Furnished",
        "host_name" : "Adam",
        "host_is_superhost" : "t",
        "neighbourhood" : "Washington, District of Columbia, United States",
        "price" : "$89.00"
}
{
        "name" : "1 BR Colonial Unit in the Heart of DuPont",
        "host_name" : "Ladi",
        "host_is_superhost" : "t",
        "neighbourhood" : "",
        "price" : "$100.00"
}
```

4. find all the unique host_name values <br>
The distinct function was used to find the unique host_name values with "host_name" as the argument. <br>
The code used to perform it: <br>
```js
db.listings.distinct("host_name");
```
The first 3 results in the array: <br>
```js
[
        "A. Lynn",
        "AKA White House",
        "AKink",
]
```

5. find all of the places that have more than 2 beds in a neighborhood of your choice (referred to as either the neighborhood or <br>
neighbourhood_group_cleansed fields in the data file), ordered by review_scores_rating descending <br>
The code used to perform it: <br>
```js
//choose two neighborhood by this
db.listings.distinct("neighbourhood_cleansed");
//find all of the places that have more than 2 beds in the neighborhood Historic Anacostia
db.listings.find(
    {$and: [
            {"neighbourhood_cleansed": "Historic Anacostia"},
            {"beds": {$gt: 2}}
           ]},
    {_id: 0, name: 1, beds: 1, review_scores_rating: 1, price: 1}
).sort({review_scores_rating: -1}).pretty();
```
The first 3 results: <br>
```js
{
        "name" : "Posh, high end luxury in the heart of D.C!",
        "beds" : 3,
        "price" : "$396.00",
        "review_scores_rating" : 5
}
{
        "name" : "Contemporary 3 level townhome close to everything!",
        "beds" : 4,
        "price" : "$130.00",
        "review_scores_rating" : 5
}
{
        "name" : "Trendy Home +Private Parking+ 5 min walk to Metro",
        "beds" : 3,
        "price" : "$218.00",
        "review_scores_rating" : 4.9
}
```

6. show the number of listings per host <br>
The code used to perform it: <br>
```js
db.listings.aggregate([
    {
      $group: {
          _id: "$host_id",
          listings_num: {$sum: 1}
      }
    },
    {
        $project: {
            _id: 0,
            host_id: "$_id",
            listings_num: 1
        }
    }
]);
```
The first 3 results: <br>
```js
{ "listings_num" : 1, "host_id" : 505709550 }
{ "listings_num" : 1, "host_id" : 61291655 }
{ "listings_num" : 1, "host_id" : 273215323 }
```

7. find the average review_scores_rating per neighborhood, and only show the ones above a 95, sorted in descending order of rating <br>
The code used to perform it: <br>
```js
db.listings.aggregate([
    {
        $group : {
            _id : "$neighbourhood",
            avg_review_scores_rating : {$avg: "$review_scores_rating"}
        }
    },
    {
        $project: {
            _id: 0,
            neighbourhood_cleansed: "$_id",
            avg_review_scores_rating: 1
        }
    },
    { $match: {avg_review_scores_rating: { $gt: 4.75 }}},
    {$sort: {avg_review_scores_rating: -1}}
]).pretty();
```
The first 3 results: <br>
```js
{
        "avg_review_scores_rating" : 5,
        "neighbourhood_cleansed" : "Alexandria, Virginia, United States"
}
{
        "avg_review_scores_rating" : 4.92,
        "neighbourhood_cleansed" : " , United States"
}
{
        "avg_review_scores_rating" : 4.91,
        "neighbourhood_cleansed" : "Chevy Chase, Maryland, United States"
}
```
