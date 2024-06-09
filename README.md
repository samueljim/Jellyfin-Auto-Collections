# Jellyfin Auto Collections

A tool to automatically make and update [jellyfin](https://jellyfin.org) collections based on internet lists such as IMDb and letterboxd.

```
Getting collections list...

found /r/TrueFilm Canon (1000 films) 015dee24c79dacfa80300afb7577fc37
************************************************

Can't find A Trip to the Moon
Can't find The Birth of a Nation
Can't find Intolerance: Love&#039;s Struggle Throughout the Ages
Can't find A Man There Was
Can't find The Cabinet of Dr. Caligari
Added Big Buck Bunny cc561c8b1d5da3a080cdb61ebe44d1a7
Added Big Buck Bunny 2 0515533b716e8fe76d3b630f9b9b6d51
Can't find Nosferatu
Can't find Dr. Mabuse, the Gambler
Can't find Häxan
Added Big Buck Bunny 3 9a6b8002ef8f12a0611e92f5104d8b8e
Can't find Sherlock, Jr.
Can't find Greed
Can't find The Last Laugh
Can't find Battleship Potemkin
Added Big Buck Bunny 5 98690cc73413b12593988687ee737a27
Can't find Ménilmontant
...
```

![pic-selected-220609-1405-13](https://user-images.githubusercontent.com/13795113/172853971-8b5ab33b-58a9-4073-8a28-c471e9710cdc.png)

## Supported List Sources

- IMDB Charts - e.g. [Top 250 Movies](https://imdb.com/chart/top), [Top Box Office](https://imdb.com/chart/boxoffice)
- IMDB Lists - e.g. [Top 100 Greatest Movie of All time](https://imdb.com/list/ls055592025)
- Letterboxd - e.g. [Movies everyone should watch at least once...](https://letterboxd.com/fcbarcelona/list/movies-everyone-should-watch-at-least-once)
- mdblist - e.g. [Top Movies of the week](https://mdblist.com/lists/garycrawfordgc/top-movies-of-the-week)
- They Shoot Pictures, Don't They - [The 1,000 Greatest Films](https://www.theyshootpictures.com/gf1000_all1000films_table.php)

Please feel free to send pull requests with more!

## Usage

First, copy `config.yaml.example` to `config.yaml` and change the values for your specific jellyfin instance.

### Bare Metal

Make sure you have Python 3 and pip installed.

Install the requirements with `pip install -r requirements.txt`.

Then run `python main.py`.

### Docker

The easiest way to get going is to use the provided `docker-compose.yml` configuration. Whatever directory you end up mapping to the config directory needs to contain your updated `config.yaml` file.

#### Configuration Options

| Environment Variable           | Description                                                                                                  |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| JELLYFIN_SERVER_URL            | The URL of your Jellyfin instance                                                                            |
| JELLYFIN_API_KEY               | Generated API Key                                                                                            |
| JELLYFIN_USER_ID               | UserID from the URL of your Profile in Jellyfin                                                              |
| CRONTAB                        | The interval the scripts will be run on in crontab syntax. Blank to disable scheduling.                      |
| TZ                             | Timezone the interval will be run in. No effect is scheduling is disabled.                                   |
