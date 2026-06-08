# Raamatukogu

Raamatukogu on veebirakendus raamatukogu haldamiseks. Kasutajad saavad registreeruda, sisse logida, otsida ja filtreerida raamatuid ning laenutada ja tagastada neid.

## Tehnoloogiad

* JavaScript – rakenduse loogika ja funktsionaalsus
* HTML – veebilehtede struktuur
* CSS – kasutajaliidese kujundus
* Docker – rakenduse käivitamine

## Käivitamine

1. Klooni projekt:

```
git clone https://github.com/KRAKENN8/raamatukogu-lab.git
cd raamatukogu-lab
```

2. Paigalda sõltuvused:

```
npm install
```

3. Käivita rakendus:

```
npm start
```

Rakendus on saadaval aadressil:

```
http://localhost:3000
```

## Testikasutajad

| Email | Parool |
|---------|---------|
| Test.User@test.com | testpassword123 |

## API endpointid

### Kasutajad

| Meetod | URL | Kirjeldus |
|--------|-----|-----------|
| POST | /api/users/signup | Uue kasutaja registreerimine |
| POST | /api/users/login | Kasutaja sisselogimine |
| POST | /api/users/logout | Kasutaja väljalogimine |
| GET | /api/users/me | Laenutatud raamatute kohta andmete hankimine |

### Raamatud

| Meetod | URL | Kirjeldus |
|--------|-----|-----------|
| GET | /api/books | Kõigi raamatute nimekirja pärimine |
| GET | /api/books/:id | Konkreetse raamatu andmete pärimine |
| GET | /api/books/search | Raamatute otsimine pealkirja, autori või muu märksõna järgi |
| GET | /api/books/genres | Kõigi olemasolevate žanrite nimekirja pärimine |
| GET | /api/books/genre/:genre | Raamatute filtreerimine žanri järgi |

### Laenud

| Meetod | URL | Kirjeldus |
|--------|-----|-----------|
| POST | /api/loans | Raamatu laenutamine |
| POST | /api/loans/:id/return | Laenutatud raamatu tagastamine |
| GET | /api/loans | Kõigi laenutuste nimekirja pärimine |
| GET | /api/loans/me | Sisselogitud kasutaja laenutuste vaatamine |

## Testid

```
node src/test.js
```

## GitHub Actions

GitHub Actions käivitub automaatselt iga push'i ja pull request'i korral.

Automaatne töövoog:

- paigaldab sõltuvused;
- käivitab testid;
- kontrollib, et projekt ehitub edukalt;
- tagab, et vigane kood ei jõuaks põhiharusse.
