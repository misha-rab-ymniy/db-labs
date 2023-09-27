# Topic: cinema

<!-- ## Functional Requirements
* User authorization. 
* User Management (CRUD).
* The role system (USER, ADMIN).
* Logging user actions.
* Films managment
* Halls managment
* Films_schedule managment 
* Non-authorized user see film schedule, films
* Authorized user(USER) Non-authorized + buy tickets, see profile
* Authorized user(ADMIN) CRUD with all entities-->

## Entities
1. "film"
    * "film_id" BIGINT PRIMARY KEY NOT NULL
    * "title" VARCHAR(255)
    * "release_date" DATE
    * "country" VARCHAR(255)
    * "duration" INTERVAL
    * "description" TEXT
    * "rating" REAL 
    CHECK rating >= 0 and rating <= 10
2. "cinema_hall"
    * "cinema_hall_id" BIGINT PRIMARY KEY NOT NULL
    * "capacity" INT NOT NULL
    * "hall_name" VARCHAR(255)
    * "cinema_id" BIGINT NOT NULL, -> cinema
3. "film_schedule"
    * "schedule_id" BIGINT RPIMARY KEY NOT NULL
    * "film_id" BIGINT NOT NULL, -> film
    * "hall_id" BIGINT NOT NULL, -> hall
    * "start_time" DATE 
    * "value" BIGINT NOT NULL
4. "ticket"
    * "ticket_id" BIGINT PRIMARY KEY NOT NULL
    * "user_id" BIGINT NOT NULL, -> user
    * "date_of_purchase" DATE
    * "schedule_id" BIGINT NOT NULL, -> film_schedule
    * "seat_id" BIGINT NOT NULL, -> seat
5. "film_genres"
    * "film_id" BIGINT NOT NULL, -> film
    * "genre_id" BIGINT NOT NULL, -> genres
6. "genre"
    * "genres_id" BIGINT PRIMARY KEY NOT NULL
    * "name" VARCHAR(255)
7. "cinema"
    * "cinema_id" BIGINT PRIMARY KEY NOT NULL
    * "name" VARCHAR(255)
    * "location" VARCHAR(255)
8. "user"
    * "user_id" BIGINT PRIMARY KEY NOT NULL
    * "username" VARCHAR(255)
    * "email" VARCHAR(255)
    * "role_id" BIGINT NOT NULL, -> role
9. "role"
    * "role_id" BIGINT PRIMARY KEY NOT NULL
    * "name" VARCHAR(255)
10. "review"
    * "review_id" BIGINT PRIMARY KEY NOT NULL
    * "film_id" BIGINT NOT NULL, -> film
    * "user_id" BIGINT NOT NULL, -> user
    * "text" VARCHAR(255)
11. "seat"
    * "seat_id" BIGINT PRIMARY KEY NOT NULL
    * "hall_id" BIGINT NOT NULL, -> cinema_hall
    * "seat_number" BIGINT NOT NULL
    * "row_number" BIGINT NOT NULL

![db_cinema](https://github.com/misha-rab-ymniy/db-labs/assets/93446693/84ea7260-ee77-43a5-a925-d75f21e94b04)
