martini, go get github.com/codegangsta/martini
martini render, go get github.com/codegangsta/martini-contrib/render
postgres, go get github.com/lib/pq

run postgresql
pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start

CREATE TABLE users (
  id SERIAL,
  username TEXT,
  fb_id TEXT,
  firstname TEXT,
  lastname TEXT,
  encrypted_password TEXT,
  created_at DATE,
  updated_at DATE,
  players JSON[]
);

CREATE TABLE cards (
  id SERIAL,
  name TEXT,
  created_at DATE,
  updated_at DATE
);

CREATE TABLE wc_players (
  id SERIAL,
  uid TEXT,
  name TEXT,
  age NUMERIC,
  foot TEXT,
  goals NUMERIC,
  birthCountry TEXT,
  birthCity TEXT,
  penaltyGoals NUMERIC,
  birthDate TEXT,
  image TEXT,
  weight NUMERIC,
  assists NUMERIC,
  national TEXT,
  position TEXT,
  height NUMERIC,
  ownGoals NUMERIC,
  club TEXT
);

CREATE TABLE players (
  id          SERIAL,
  nameAlias   TEXT,
  name        TEXT,
  club        TEXT,
  position    TEXT,
  appearances TEXT,
  goals       NUMERIC,
  shots       NUMERIC,
  penalties   NUMERIC,
  assists     NUMERIC,
  crosses     NUMERIC,
  offsides    NUMERIC,
  savesMade   NUMERIC,
  ownGoals    NUMERIC,
  cleanSheets NUMERIC,
  blocks      NUMERIC,
  clearances  NUMERIC,
  fouls       NUMERIC,
  cards       NUMERIC,
  dob         TEXT,
  height      TEXT,
  age         NUMERIC,
  weight      TEXT,
  national    TEXT
  image       TEXT
);

ALTER TABLE users ADD id SERIAL;
ALTER TABLE nameAlias ADD nameAlias TEXT;
alter table users add players json[];

CREATE UNIQUE INDEX nameAlias ON wc_players (nameAlias)

curl -d "email=ins429@gmail.com&password=pass" "localhost:8080/signup"


https://code.google.com/p/go/source/browse/html/?repo=net
https://godoc.org/code.google.com/p/go.net/html#Attribute

select distinct nameAlias from players;

