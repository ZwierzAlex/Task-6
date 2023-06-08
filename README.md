# Task-6  <br>
## Subtask 1  <br>
*11. Popełniłam błąd wpisując nazwisko Ani Miler – wpisałam Muler. Znajdź i zastosuj funkcję, która poprawi mój karkołomny błąd 🙈* <br>
__→ UPDATE customers SET surname = REPLACE(surname, 'Muler', 'Miler') WHERE surname = 'Muler';__ <br>
*12. Pobrałam za dużo pieniędzy od klienta, który kupił w ostatnim czasie film o id 4. Korzystając z funkcji join sprawdź, jak ma na imię klient i jakiego ma maila. W celu napisania mu wiadomości o pomyłce fantastycznej szefowej.*<br>
__→ SELECT name, email <br>FROM customers <br>JOIN sale ON customer_id <br>JOIN movies ON movie_id <br>WHERE movie_id = 4<br>AND sale.ile_pobrano > sale.price;__<br>
*13. Na pewno zauważył_ś, że sprzedawca zapomniał wpisać emaila klientce Patrycji. Uzupełnij ten brak wpisując: pati@mail.com* <br>
__→ UPDATE customers SET email = 'pati@mail.com' WHERE name = 'Patrycja' AND email IS NULL;__ <br>
*14. Dla każdego zakupu wyświetl, imię i nazwisko klienta, który dokonał wypożyczenia oraz tytuł wypożyczonego filmu. (wykorzystaj do tego funkcję inner join, zastanów się wcześniej, które tabele Ci się przydadzą do wykonania ćwiczenia).* <br>
*15. W celu anonimizacji danych, chcesz stworzyć pseudonimy swoich klientów. - Dodaj kolumnę o nazwie ‘pseudonym’ do tabeli customer,- Wypełnij kolumnę w taki sposób, aby pseudonim stworzył się z dwóch pierwszych liter imienia i ostatniej litery nazwiska. Np. Natalie Pilling → Nag* <br>
__→ ALTER TABLE customers <br>ADD COLUMN pseudonym VARCHAR(10);<br>UPDATE customers<br>SET pseudonym = CONCAT(LEFT(name, 2), RIGHT(surname, 1));__ <br>
*16. Wyświetl tytuły filmów, które zostały zakupione, wyświetl tabelę w taki sposób, aby tytuły się nie powtarzały.* <br>
__→ SELECT DISTINCT movies.title FROM sale JOIN movies ON sale.movie_id;__ <br>
*17. Wyświetl wspólną listę imion wszystkich aktorów i klientów, a wynik uporządkuj alfabetycznie. (Wykorzystaj do tego funkcji UNION)* <br>
__→ SELECT name FROM actors UNION SELECT name FROM customers ORDER BY name;__ <br>
*18. Polskę opanowała inflacja i nasz sklepik z filmami również dotknął ten problem. Podnieś cenę wszystkich filmów wyprodukowanych po 2000 roku o 2,5 $ (Pamiętaj, że dolar to domyślna jednostka- nie używaj jej nigdzie).* <br>
__→ UPDATE movies SET price = price + 2.5 WHERE year_of_production > 2000;__ <br>
*19. Wyświetl imię i nazwisko aktora o id 4 i tytuł filmu, w którym zagrał* <br>
__→ SELECT name, surname<br>FROM actors<br>JOIN cast ON actor_id<br>JOIN movies ON movie_id<br>WHERE actor_id = 4;<br>
*20. A gdzie nasza HONIA!? Dodaj do tabeli customers nową krotkę, gdzie customer_id = 7, name = Honia, surname = Stuczka-Kucharska, email = honia@mail.com oraz pseudonym = Hoa* <br>
__→ INSERT INTO customers (customer_id, name, surname, email, pseudonym) VALUES (7, 'Honia', 'Stuczka-Kucharska', 'honia@mail.com', 'Hoa')__
## Subtask 2
Ilość punktów osiągnięta w quizie: 12/15, nie tak źle, aleeee...mogło być znacznie lepiej.
![wynik testu](https://github.com/ZwierzAlex/Task-6/assets/131251044/86c9cabf-55d3-4ac0-9c39-6c29faec597d)
