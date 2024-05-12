### CZĘŚĆ DODATKOWA
Utworzony wcześniej kontroler lab7builder pasuje do tego zadania.<br />
Ustawienie builder-a lab7builder jako domyślnego
```
docker buildx use lab7builder
```
Budowanie obrazu
```
docker buildx build -f Dockerfile -t s96504/zadanie1:tag1 --platform linux/amd64,linux/arm64 --push .
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/4b0f268e-a938-4a67-84d9-05908ab8b761)

Sprawdzenie manifesta 
```
docker buildx imagetools inspect docker.io/s96504/zadanie1:tag1
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/f64d9049-03e8-425c-bd3c-7dd01bdbc2f8)
