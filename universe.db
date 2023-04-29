CREATE TABLE universe,
\c universe;
CREATE TABLE galaxy(
	galaxy_id SERIAL PRIMARY KEY,
	name VARCHAR(255) NOT NULL,
	age INT, 
	distance_from_earth NUMERIC,
	has_black_hole BOOLEAN NOT NULL,
	has_ring_system BOOLEAN NOT NULL,
	UNIQUE (name)
);

INSERT INTO galaxy (name, age, distance_from_earth, has_black_hole, has_ring_system)
VALUES ('Milky Way', 13000, 10000, true, false),
       ('Andromeda', 22000, 253700, false, true),
       ('Triangulum', 13000, 3000, false, false),
       ('Pinwheel', 25000, 2900, true, true),
       ('Cigar', 10000, 1200, true, false),
       ('Whirlpool', 23000, 31000, false, true),
       ('Sunflower', 10000, 27000, true, false),
       ('Sombrero', 28000, 31400, true, true),
       ('Cartwheel', 50000, 50300, false, true);

CREATE TABLE star(
	star_id SERIAL PRIMARY KEY,
	name VARCHAR(255) NOT NULL,
	temperature INT NOT NULL,
	is_black_hole BOOLEAN NOT NULL,
	has_habitable_planet BOOLEAN NOT NULL,
	galaxy_id INT NOT NULL REFERENCES galaxy(galaxy_id)
	UNIQUE (name)
);

INSERT INTO star (name, temperature, is_black_hole, has_habitable_planet, galaxy_id)
VALUES 
    ('Sun', 5778, FALSE, TRUE, 1),
    ('Sirius', 9940, FALSE, FALSE, 1),
    ('Vega', 9602, FALSE, FALSE, 1),
    ('Betelgeuse', 3490, FALSE, FALSE, 1),
    ('Alpha Centauri A', 5790, FALSE, TRUE, 1),
    ('Alpha Centauri B', 5260, FALSE, TRUE, 1),
    ('Proxima Centauri', 3042, FALSE, TRUE, 1),
    ('Polaris', 5840, FALSE, FALSE, 1),
    ('Antares', 3500, FALSE, FALSE, 1);

CREATE TABLE planet(
	planet_id SERIAL PRIMARY KEY,
	name VARCHAR(255) NOT NULL,
	mass NUMERIC NOT NULL,
	has_water BOOLEAN NOT NULL, 
	is_habitable BOOLEAN NOT NULL, 
	star_id INT NOT NULL REFERENCES star(star_id)
	UNIQUE (name)
);

INSERT INTO planet(name, mass, has_water, is_habitable, star_id) 
VALUES 
('Mercury', 0.33, FALSE, FALSE, 1),
('Venus', 4.87, FALSE, FALSE, 1),
('Earth', 5.97, TRUE, TRUE, 1),
('Mars', 0.642, FALSE, FALSE, 2),
('Jupiter', 1898, FALSE, FALSE, 3),
('Saturn', 568, FALSE, FALSE, 3),
('Uranus', 86.8, FALSE, FALSE, 4),
('Neptune', 102, TRUE, FALSE, 4),
('Kepler-452b', 5, TRUE, TRUE, 5);


CREATE TABLE moon(
	moon_id SERIAL PRIMARY KEY,
	name VARCHAR(255) NOT NULL,
	distance_from_planet INT NOT NULL,
	radius NUMERIC(10,2) NOT NULL,
	has_water BOOLEAN NOT NULL,
	has atmosphere BOOLEAN INT NOT NULL,
	planet_id IS NOT NULL REFERENCES planet(planet_id),
	UNIQUE (name)
);

INSERT INTO moon (name, distance_from_planet, radius, has_water, has_atmosphere, planet_id)
VALUES
  ('Luna', 384400, 1738.14, TRUE, FALSE, 1),
  ('Phobos', 9377, 11.27, FALSE, FALSE, 2),
  ('Deimos', 23460, 6.2, FALSE, FALSE, 2),
  ('Io', 421700, 1821.6, TRUE, TRUE, 3),
  ('Europa', 671034, 1560.8, TRUE, TRUE, 3),
  ('Ganymede', 107042, 2634.1, TRUE, TRUE, 3),
  ('Callisto', 1809, 2410.3, FALSE, FALSE, 3),
  ('Mimas', 1839, 198.2, FALSE, FALSE, 4),
  ('Enceladus', 2387, 252.1, TRUE, TRUE, 4),
  ('Tethys', 2919, 531.1, FALSE, FALSE, 4),
  ('Dione', 3796, 561.7, FALSE, TRUE, 4),
  ('Rhea', 52708, 763.8, FALSE, FALSE, 4),
  ('Titan', 1265, 2575.5, TRUE, TRUE, 4),
  ('Hyperion', 14102, 135, FALSE, FALSE, 4),
  ('Iapetus', 3820, 734.5, FALSE, FALSE, 4),
  ('Miranda', 190, 235.8, FALSE, FALSE, 5),
  ('Ariel', 100, 578.9, FALSE, FALSE, 5),
  ('Umbriel', 2000, 584.7, FALSE, FALSE, 5),
  ('Titania', 4310, 788.9, FALSE, FALSE, 5),
  ('Oberon', 5820, 761.4, FALSE, FALSE, 5);


CREATE TABLE cluster(cluster_id SERIAL PRIMARY KEY, name TEXT NOT NULL, galaxy_id INT NOT NULL REFERENCES galaxy(galaxy_id), UNIQUE (name));
 ALTER TABLE cluster ALTER COLUMN name SET DATA TYPE VARCHAR(255);
ALTER TABLE cluster ADD COLUMN location TEXT NOT NULL;
INSERT INTO cluster(name, galaxy_id, location) VALUES('Laniakea', 2, 'osa'),('Virgo', 2, 'andromeda'),('Bios', 1, 'milk');











