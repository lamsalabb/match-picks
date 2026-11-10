# Match Picks

A football score-prediction game built with Spring Boot. Users sign up, predict the exact score of upcoming fixtures by staking virtual coins, and get double their stake back when the prediction is right. No real money is involved.

## Features

- Registration with email OTP verification and form login (Spring Security)
- Role-based access for `USER` and `ADMIN`, backed by users and roles stored in MySQL
- Upcoming fixtures for the current matchday pulled from an external football data API
- Place a score prediction on a fixture and review your prediction history
- Automatic settlement: predictions are checked and coins paid out after the match ends
- Admin pages to list and update users
- League standings page

## Tech stack

Java 21, Spring Boot 3.4, Spring MVC, Spring Security 6, Spring Data JPA (Hibernate), Thymeleaf, MySQL, Maven

## Project layout

```
src/main/java/.../footballapp
  config/       security configuration
  controller/   MVC controllers (home, predictions, admin, login, users)
  entity/       JPA entities (User, Role, Bet)
  repository/   Spring Data repositories
  service/      prediction settlement, users, email OTP
src/main/resources/templates   Thymeleaf views
sql-scripts/                   database and table setup
```

## Run locally

1. Create the database and tables with the scripts in `sql-scripts/`.
2. Set your own datasource and mail credentials in `src/main/resources/application.properties` (or pass them as environment variables). Do not commit real credentials.
3. Start the app:

```
./mvnw spring-boot:run
```

4. Open http://localhost:8080
