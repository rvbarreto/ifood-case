1. Qual a média de valor total (total_amount) recebido em um mês, considerando todos os yellow táxis da frota?

```sql
SELECT
  year(tpep_pickup_datetime) AS year,
  month(tpep_pickup_datetime) AS month,
  AVG(total_amount) AS avg_total_amount
FROM workspace.ifood_gold.consumption
GROUP BY year, month
ORDER BY year, month;
```

| year | month | avg_total_amount |
| --- | --- | --- |
| 2023 | 1 | 27.356354940523552 |
| 2023 | 2 | 27.288957048142617 |
| 2023 | 3 | 28.208017823911685 |
| 2023 | 4 | 28.68515995284298 |
| 2023 | 5 | 29.363968915824493 |


2. Qual a média de passageiros (passenger_count) por cada hora do dia que pegaram táxi no mês de maio, considerando todos os táxis da frota?

```sql
SELECT
  pickup_hour,
  AVG(passenger_count) AS avg_passenger_count
FROM workspace.ifood_gold.consumption
WHERE year(tpep_pickup_datetime) = 2023 and month(tpep_pickup_datetime) = 5
GROUP BY pickup_hour
ORDER BY pickup_hour;
```

| pickup_hour | avg_passenger_count |
| --- | ---|
| 0, | .4276275933017089 |
| 1, | .4388815383258358 |
| 2, | .455231871722358 |
| 3, | .4536301457156209 |
| 4, | .4069560635004281 |
| 5, | .2836955904886216 |
| 6, | .2626217295696271 |
| 7, | .2834307949106265 |
| 8, | .296357869761361 |
| 9, | .3131942348866952 |
| 10 | 1.3488891230195836 |
| 11 | 1.3636297605500811 |
| 12 | 1.3780805753778727 |
| 13 | 1.38626986217189 |
| 14 | 1.3910050319734724 |
| 15 | 1.4027042915931804 |
| 16 | 1.3996326306901508 |
| 17 | 1.3904340411709772 |
| 18 | 1.3839817535113044 |
| 19 | 1.3927797424844068 |
| 20 | 1.401654104186254 |
| 21 | 1.4205716245213516 |
| 22 | 1.428732802805503 |
| 23 | 1.4233506054876377 |
