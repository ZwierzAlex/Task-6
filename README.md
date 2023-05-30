# Task-6
##Subtask 1 <br>
*11. Popełniłam błąd wpisując nazwisko Ani Miler – wpisałam Muler. Znajdź i zastosuj funkcję, która poprawi mój karkołomny błąd 🙈* <br>
__→ UPDATE customers SET surname = REPLACE(surname, 'Muler', 'Miler') WHERE surname = 'Muler';__ <br>
12. Pobrałam za dużo pieniędzy od klienta, który kupił w ostatnim czasie film o id 4. Korzystając z funkcji join sprawdź, jak ma na imię klient i jakiego ma maila. W celu napisania mu wiadomości o pomyłce fantastycznej szefowej.<br>
__→ SELECT name, email <br>FROM customers <br>JOIN sale ON customer_id = sale.customer_id<br>JOIN movies ON movie_id = sale.movie_id<br>WHERE movie_id = 4<br>AND sale.ile_pobrano > sale.pice;<br>
14. Na pewno zauważył_ś, że sprzedawca zapomniał wpisać emaila klientce Patrycji. Uzupełnij ten brak wpisując: pati@mail.com <br>
15. Dla każdego zakupu wyświetl, imię i nazwisko klienta, który dokonał wypożyczenia oraz tytuł wypożyczonego filmu. (wykorzystaj do tego funkcję inner join, zastanów się wcześniej, które tabele Ci się przydadzą do wykonania ćwiczenia). <br>
16. W celu anonimizacji danych, chcesz stworzyć pseudonimy swoich klientów. - Dodaj kolumnę o nazwie ‘pseudonym’ do tabeli customer,- Wypełnij kolumnę w taki sposób, aby pseudonim stworzył się z dwóch pierwszych liter imienia i ostatniej litery nazwiska. Np. Natalie Pilling → Nag <br>
17. Wyświetl tytuły filmów, które zostały zakupione, wyświetl tabelę w taki sposób, aby tytuły się nie powtarzały. <br>
18. Wyświetl wspólną listę imion wszystkich aktorów i klientów, a wynik uporządkuj alfabetycznie. (Wykorzystaj do tego funkcji UNION) <br>
19. Polskę opanowała inflacja i nasz sklepik z filmami również dotknął ten problem. Podnieś cenę wszystkich filmów wyprodukowanych po 2000 roku o 2,5 $ (Pamiętaj, że dolar to domyślna jednostka- nie używaj jej nigdzie). <br>
20. Wyświetl imię i nazwisko aktora o id 4 i tytuł filmu, w którym zagrał <br>
21. A gdzie nasza HONIA!? Dodaj do tabeli customers nową krotkę, gdzie customer_id = 7, name = Honia, surname = Stuczka-Kucharska, email = honia@mail.com oraz pseudonym = Hoa <br>
