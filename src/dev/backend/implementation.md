# Implementation

<!-- TOC -->

- [Implementation](#implementation)
  - [General](#general)
  - [Best practices](#best-practices)
    - [Performance](#performance)
  - [Next steps](#next-steps)
    - [Elo](#elo)
    - [Authentication](#authentication)
    - [Permissions](#permissions)
    - [Architecture](#architecture)
    - [Database](#database)
      - [Models](#models)

<!-- /TOC -->

## General

- Routing: <https://laravel.com/docs/10.x/routing>
- Controller: <https://laravel.com/docs/10.x/controllers>
- Authentication: <https://laravel.com/docs/10.x/sanctum>
- ORM: <https://laravel.com/docs/10.x/eloquent>

## Best practices

- <https://github.com/alexeymezenin/laravel-best-practices>

### Performance

- [ ] <https://kinsta.com/blog/laravel-performance/>
- [ ] <https://newrelic.com/blog/best-practices/improve-laravel-performance>
- [ ] <https://www.cloudways.com/blog/laravel-performance-optimization/>
- [ ] <https://serversforhackers.com/laravel-perf/eager-loading>

## Next steps

- [ ] implement Elo calculation
- [ ] implement `review` system and `ada` funtionality
- [ ] create `drafts` table and implement `draft` functionality
- [ ] implement API Endpoints for `Players`, `Teams`, `Sets`, `Tournaments`,
      `Search`, and `Leaderboads`
  - [ ] <https://laravel.com/docs/10.x/eloquent-resources>
- [ ] check <https://github.com/nette/utils> for functionality

### Elo

- [ ] implement Elo calculation algorithm
- [ ] implement Elo caching mechanism

### Authentication

- Discord: <https://socialiteproviders.com/Discord/>
  - [x] Config Setup
  - [ ] Acquire Client ID and Secret
  - [x] Add Redirect URL
  - [x] `return Socialite::driver('discord')->redirect();`
- Steam: <https://socialiteproviders.com/Steam/>
  - [x] Config Setup
  - [ ] Acquire Client ID and Secret
  - [x] Add Redirect URL
  - [x] `return Socialite::driver('discord')->redirect();`
- Twitch: <https://socialiteproviders.com/Twitch/>
  - [x] Config Setup
  - [ ] Acquire Client ID and Secret
  - [x] Add Redirect URL
  - [x] `return Socialite::driver('discord')->redirect();`
- Github: <https://socialiteproviders.com/Github/> (Socialite Base)
  - [x] Config Setup
  - [ ] Acquire Client ID and Secret
  - [x] Add Redirect URL
  - [x] `return Socialite::driver('discord')->redirect();`
- possible others
  - Google: <https://socialiteproviders.com/Google/> (Socialite Base)

### Permissions

- <https://web.archive.org/web/20230605041826/https://www.honeybadger.io/blog/user-roles-permissions-in-laravel/>

### Architecture

- create overview/bird's eye

### Database

- [ ] Check ER diagram
- [x] Create 'news' table + model + controller
- [x] Check models
- [x] Create migration script from old schema to new one
- [ ] Optimize queries:
      <https://omarbarbosa.com/posts/optimization-of-eloquent-queries-to-reduce-memory-usage>
- [x] create legacy->new database mapping
- [x] finish design of new database schema
- [x] generate new models from database
  - [x] check if the relations are correct
- [x] implement repository pattern via interfaces
- [x] migrate data from legacy to the new database schema
  - [x] use `command` and `seeder` setup

#### Models

- [x] implement metadata for ArdPlayer
- [x] implement metadata for player/team import
  - [x] check how to get all metadata for an `ArdPlayer`
- [x] move `Player::aliases` to `Player::metadata->alias`
- [x] move `Player::other_socials` to `Player::metadata->socials`
