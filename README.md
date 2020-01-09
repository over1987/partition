# partition

CREATE TABLE partitable (
    id         int not null,
    condate         date not null,
) PARTITION BY RANGE (condate);

CREATE TABLE partitable19 PARTITION OF partitable
FOR VALUES FROM ('2019-01-01') TO ('2019-12-31');

CREATE TABLE partitable20 PARTITION OF partitable
FOR VALUES FROM ('2020-01-01') TO ('2020-12-31');

INSERT INTO partitable VALUES (0, '2019-01-01');
INSERT INTO partitable VALUES (1, '2019-02-02');
INSERT INTO partitable VALUES (2, '2019-03-03');
INSERT INTO partitable VALUES (3, '2019-04-04');
INSERT INTO partitable VALUES (4, '2019-05-05');
INSERT INTO partitable VALUES (5, '2020-01-01');
INSERT INTO partitable VALUES (6, '2020-02-02');
INSERT INTO partitable VALUES (7, '2020-03-03');
INSERT INTO partitable VALUES (8, '2020-04-04');

select * from partitable19

select * from partitable20

select * from partitable
