## Zadanie 1

### Część obowiązkowa


##### 1. (max.20%)

Szukając sposobu na wykonanie tego zadania, znalazłem moduł Satelize do pobierania informacji o lokalizacji użytkownika na podstawie adresu IP. Wszystko działało dobrze, ale pojawił się problem z lokalizacją przez localhost, więc dodałem sprawdzanie, czy adres IP jest adresem wewnętrznym w sieci lokalnej.

Sprawdzanie działania bez kontenera Docker:
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/5fcf74e0-f7a3-46d3-80a8-b8e61abc56d1)
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/2569646f-1d9b-474b-9e56-e85e6b1630ad)

Aby sprawdzić, czy biblioteka działa poprawnie, wprowadzę japoński adres IP:
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/dbdf01fa-125a-4480-abfb-4841fe31d4eb)

##### 2. (max. 50%)
Dodałem plik dockerfile do repozytorium 


##### 3. (max. 30%)
- a) Zbudowanie obrazu kontenera:
```
docker build -t myapp3 .
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/52107559-4a2f-44c5-8808-92eefe7e8931)

- b) Uruchomienie kontenera w tle:
```
docker run -d -p 3000:3000 myapp3
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/549bee55-d71c-47db-b23d-1a84527d41bb)

Sprawdzanie działania:
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/c29ae7c6-f6d4-4a90-94b2-2ac2b1199bf8)

 - c) Uzyskanie informacji, które wygenerował serwer w trakcie uruchamiana kontenera
 Używając docker ps, wyszukujemy id kontenera.
 ```
 docker ps
 docekr logs c7
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/f0224d20-018b-4a2e-ae56-df721d64af7f)

- d) Sprawdzenie, ile warstw posiada zbudowany obraz.
```
docker history myapp3
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/6ad4408c-52fa-4a3a-91d5-2ba02ac26448)

##### Sprawdzenie zagrożeń za pomocą narzędzia Docker Scount.
```
docker scout quickview
```
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/c1c29299-8be8-4309-8485-0413028a05f8)
Dokładny rozmiar obrazu:
![image](https://github.com/MykhailoKrylov/zadanie1/assets/134151663/3d5d5c6d-2f6d-497f-b1ee-7431e22e68b4)


### CZĘŚĆ DODATKOWA
Utworzony wcześniej kontroler lab7builder pasuje do tego zadania 
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


