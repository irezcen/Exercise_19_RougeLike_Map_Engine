W folderze bin/debug/maps znajduje się plik o nazwie "MetaMap.txt".
Plik ten pozwala na tworzenie map z włąsnymi połaczeniami, potworami i interakcjami.
Nazwy tego pliku nie należy zmieniać pod żadnym pozorem.
Każda linijka poza pierwszą w tym pliku odpowiada kolejnej mapie, któa pojawi się w grze.

Pierwsza linijka pozwala na modyfikowanie globalnych ustawień:
portals=	// oczekiwana licza portali na każdej losowej mapie
shops=	// ilość sklepów w grze, które pojawią się losowo na mapie
interactions=	// ilość losowych interakcji (włączając w to sklepy) w grze pojawiających się na mapach, które na to pozwalają. Ta liczba często będzie się różnić przez interakce questowe
monsters=	// ilość potworów na każdej mapie, która pozwala na losowe potwory.
walls=	// oczekiwana iczba ścian na mapie(ta lczba możę się różnić, by pozwolić na dotarcie w każde pole mapy)

W każdej linijce dostępne są następujące flagi:
randomportals=true/false	// Na tej mapie będą tworzyć się losowe portale między innymi mapami, któe na to pozwalają
randominteractions=true/false	// Na tej mapie będą pojawiać się losowe interakcje i wydarzenia questowe, które nie zostały ujęte w innych mapach
randommonsters=true/false	// Na tej mapie będą pojawiać się loswe potwory
mainquest=(liczba)	// Na tej mapie pojawi się interakcja głównego questa. Liczba mówi, która interakcja ma się pojawić. Interakcje, które nie zostaną ręcznie ustalone pojawią się na mapach pozwalających na losowe interakcje.
sidequest=(liczba).(liczba)	// Na tej ampie pojawi się interakcja questa pobocznego. Pierwsza liczba oznacza, z którego questa pochodzi interakcja(liczba ta odpoiwada kolejnym interakcjom zawartym w Index.SideQuestFactory). Druga liczba mówi, która interakcja ma zostać położona na mapie. Reszta interakcji pojawi się tak samo jak w przypadku mainquest. Jeżeli rzadna z interakcji nie zostanie ręcznie umeiszczona, ten sidequest nie pojawi się w  grze.
portal=(liczba)	// Na tej mapie zostanie stworzony portal do mapy odpowiadającej linijce danej lcizbą + 1 (tzn mapa nr 1 znajdująca się w drugiej linijce odpowiada liczbie 1)
monster=(liczba)	// Na tej mapie pojawi się potwór znajdujący się na pozycji (liczba) w liście Index.monsterFactories

W szczególności istnieje flaga file=(ścieżka). Dzieki niej można stworzyć mapę opisując każde pole numerem(patrz MapMatrix).
Musi to być plik typu .txt zawierający w sobie numery odpoiwadające polom mapy odzielone w tej samej linijce tabulatorami, a linijki odzielone enterami.
Rozmiar mapy to 25x20.

UWAGA 1!
Jeżeli korzysta się z flagi file=, nalezy rónież w tej linijce umieścić flagi mówiące o tym jakie portale i questy znajdują się na mapie.
UWAGA 2!
Flagi w tej samej linijce muszą być odzielone tabulatorami!
UWAGA 3!
Jeżeli przynajmniej jedna mapa posiada flagę randominteractions=true, to jedna z tych map musi znajdować się w pliku MetaMapMatrix jako ostatnia.
UWAGA 4!
W linijkach opisujacych mapy można również pisać kometarze oddzielone tabulatorami, jednak nie mogą one zawierać w sobie nazwy flagi ani znaczącej jej części.

Dla lepszego zrozumienia patrz plik bin/debug/Maps/MetaMapMatrix.txt