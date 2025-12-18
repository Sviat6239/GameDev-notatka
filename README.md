Framework vs Silnik:
    --- Framework jest zawsze zupełnie free
    --- Silnik ma większe możliwości do developmentu


Unity:
    --- skrypty w c#
    --- zaawansowany Asset Store
    --- Profesjonalne narzędzia

Godot:
    --- Open Source
    --- Przyjazny dla uzytkownika
    --- Wsparcie dla 2D i 3D

Unreal Engine:
    --- Fotorealistyczna grafika
    --- Wizualne skryptowanie
    --- Funkcje Kinematograficzne
    --- Wsparcie dla VR i AR

Wybór wlaściwego śilnika
    --- Zakres projektu
    --- Doświadczenie w rozwoju
    --- Spoleczność i wsparcie


Licencja:
    Godot:
        --- free 100% , opensorce

    Unreal Engine:
        --- powięcej 1 milionu dolarów trzeba placić procent

    Unity:
        --- powyrzej 200K za rok treba przejść na licencje Pro (2 koła $)

Systemy kontroli wersji (Version Control Systems):
    --- Systemy kontroli wersji służą do zarządzania zmianami w kodzie źródłowym projektu. Są niezbędne przy pracy zespołowej, ale również bardzo pomocne w projektach indywidualnych, ponieważ pozwalają:
    --- przechowywać historię zmian,
    --- wracać do poprzednich wersji projektu,
    --- pracować równolegle nad różnymi funkcjami,
    --- bezpiecznie eksperymentować bez psucia głównej wersji projektu.

Przykłady systemów kontroli wersji:
    --- Git – najpopularniejszy, rozproszony system kontroli wersji.
    --- GitHub – platforma hostingowa dla repozytoriów Git.
    --- Perforce – scentralizowany system, często używany w dużych studiach (np. gamedev).
    --- Subversion (SVN) – starszy, scentralizowany system kontroli wersji.

Git i GitHub – różnice i podstawowe pojęcia:

    --- Git – to sam system kontroli wersji, który działa lokalnie na komputerze.
        Pozwala tworzyć repozytoria, zapisywać zmiany i zarządzać historią projektu.
        Możliwe jest uruchomienie własnego serwera Git bez korzystania z GitHuba.

    --- GitHub – to zewnętrzna platforma do przechowywania repozytoriów Git w chmurze,
        umożliwiająca współpracę zespołową, code review i zarządzanie projektami.

Podstawowe pojęcia i komendy Git:
    --- Repozytorium (Repository):
        --- Miejsce, w którym przechowywany jest projekt wraz z pełną historią zmian.
    --- Commit:
        --- Zapis stanu projektu w danym momencie. Commit zawiera zmiany oraz opis (komentarz).
    --- Push:
        --- Wysyłanie lokalnych commitów na zdalne repozytorium (np. GitHub).
    --- Fetch:
        --- Pobieranie informacji o zmianach z repozytorium zdalnego bez ich łączenia z lokalnym kodem.
    --- Pull:
        --- Pobieranie zmian z repozytorium zdalnego i automatyczne scalanie ich z lokalną gałęzią (fetch + merge).
    --- Branch (Gałąź):
        --- Oddzielna linia rozwoju projektu, pozwalająca pracować nad funkcją bez wpływu na główną wersję.
    --- Merge:
        --- Łączenie jednej gałęzi z inną (np. gałęzi funkcji z develop lub main).
    --- Rebase:
        --- Przeniesienie commitów na inny punkt w historii w celu uzyskania czystszej struktury commitów.
    --- Pull Request (PR):
        --- Prośba o połączenie zmian z jednej gałęzi do drugiej, często połączona z code review.
    --- Fork:
        --- Kopia cudzego repozytorium na własnym koncie GitHub, umożliwiająca niezależną pracę nad projektem.

    --- GitFlow - Model pracy z gałęziami:

GitFlow – model pracy z gałęziami:

GitFlow to popularny model organizacji pracy w repozytorium Git, który jasno określa role poszczególnych gałęzi.
    --- main:
        --- Stabilna wersja produkcyjna projektu. Kod znajdujący się tutaj jest gotowy do wydania.
    --- develop:
        --- Gałąź rozwojowa, na której integrowane są nowe funkcje przed wydaniem.
    --- features/*:
        --- Gałęzie do tworzenia nowych funkcjonalności.
            Tworzone z develop i po zakończeniu pracy scalane z powrotem do develop.
    --- release/*:
        --- Gałęzie przygotowujące projekt do wydania (bugfixy, dokumentacja, testy).
            Po zakończeniu scalane do main i develop.
    --- hotfix/*:
        --- Gałęzie do szybkiego naprawiania krytycznych błędów w wersji produkcyjnej.
            Tworzone z main i scalane zarówno do main, jak i develop.


Comprehensive guide of execution of Unity event functions:

    --- Awake():
        --- Wywoływana raz, przy ładowaniu obiektu
        --- Działa nawet, gdy obiekt jest wyłączony
        --- Inicjalizacja wewnętrzna obiektu (zmienne, komponenty)
        --- Użycie: przygotowanie danych, GetComponent, singletony

    --- OnEnable():
        --- Wywoływana za każdym razem, gdy obiekt zostaje włączony
        --- Po Awake(), przed Start()
        --- Użycie: podpinanie eventów, uruchamianie timerów, reset stanu

    --- Start():
        --- Wywoływana raz, przed pierwszym Update()
        --- Tylko jeśli obiekt jest aktywny
        --- Użycie: logika zależna od innych obiektów, start gry

    --- FixedUpdate():
        --- Wywoływana w stałym kroku czasu (fizyka)
        --- Niezależna od FPS
        --- Użycie: fizyka, Rigidbody, siły, ruch fizyczny

    --- Update():
        --- Wywoływana co klatkę
        --- Zależna od FPS
        --- Użycie: input, logika gry, timery

    --- LateUpdate():
        --- Wywoływana po Update() w tej samej klatce
        --- Użycie: kamera, korekty pozycji po ruchu obiektów

    --- OnDisable():
        --- Wywoływana, gdy obiekt lub komponent zostaje wyłączony
        --- Użycie: odpinanie eventów, zatrzymanie coroutine

    --- OnDestroy():
        --- Wywoływana przy usuwaniu obiektu z pamięci
        --- Użycie: sprzątanie zasobów, zapisy, logi

Programowannie

    --- Typy danych:

        --- Typy proste (prymitywne):

            int a = 10;          // liczby całkowite
            float b = 3.14f;    // liczby zmiennoprzecinkowe (32-bit)
            double c = 3.14;    // liczby zmiennoprzecinkowe (64-bit)
            bool flag = true;   // wartości logiczne
            char znak = 'A';    // pojedynczy znak

        --- Typy referencyjne:

            string tekst = "Cześć";   // tekst
            object obj = null;       // obiekt ogólny

        --- Zmienne i stałe:

            int liczba = 5;
            liczba = 10;     // zmienna – można zmieniać

            const int MAX = 100; // stała – nie można zmieniać

        --- Operatory:

            +  -  *  /      // arytmetyczne
            == != > < >= <= // porównania
            && || !         // logiczne

        --- Instrukcje warunkowe:

            --- if / else:
            if (liczba > 0)
            {
                Console.WriteLine("Dodatnia");
            }
            else
            {
                Console.WriteLine("Ujemna lub zero");
            }

            --- switch:

                switch (liczba)
                {
                    case 1:
                        Console.WriteLine("Jeden");
                        break;
                    default:
                        Console.WriteLine("Inna wartość");
                        break;
                }

        --- Pętle:

            --- for:

                    for (int i = 0; i < 5; i++)
                    {
                        Console.WriteLine(i);
                    }

            --- while:

                    while (liczba > 0)
                    {
                        liczba--;
                    }

            --- foreach:

                    int[] tablica = {1, 2, 3};
                    foreach (int x in tablica)
                    {
                        Console.WriteLine(x);
                    }

        --- Metody i procedury:

            --- Procedura (bez zwracanej wartości):

                void Powitaj()
                {
                    Console.WriteLine("Witaj!");
                }

            --- Metoda (zwraca wartość):

                int Dodaj(int a, int b)
                {
                    return a + b;
                }

        --- Klasy i obiekty:

                class Player:
                {
                    public int HP;

                    public void TakeDamage(int dmg)
                    {
                        HP -= dmg;
                    }
                }

            --- Tworzenie obiektu:

                Player p = new Player();
                p.HP = 100;
                p.TakeDamage(20);

        --- Konstruktory:

                class Enemy
                {
                    public int HP;

                    public Enemy(int hp)
                    {
                        HP = hp;
                    }
                }

        --- Modyfikatory dostępu:

            --- public – dostępne wszędzie
            --- private – tylko w klasie
            --- protected – klasa + klasy dziedziczące

        --- Dziedziczenie
                class Animal
                {
                    public void Speak() { }
                }

                class Dog : Animal
                {
                }

Wzorce architektoniczne (MVC, MVP, MVVM, VC):

    --- MVC (Model–View–Controller):

        --- Najpopularniejszy klasyczny wzorzec
        --- Model – dane i logika biznesowa
        --- View – interfejs użytkownika (UI)
        --- Controller – pośrednik: reaguje na input i steruje Modelem
        --- Zastosowanie: web (ASP.NET MVC), klasyczne aplikacje
        --- Plusy: czytelny podział odpowiedzialności
        --- Minusy: Controller bywa „przeładowany”
        --- User → Controller → Model → View

    VC (View–Controller)

    --- Uproszczony wariant MVC:

        --- View – UI

        --- Controller – logika + dane (brak osobnego Modelu)

        --- Zastosowanie: Unity, małe aplikacje
        --- Plusy: prostota
        --- Minusy: słaba skalowalność, mieszanie logiki z UI
        --- View ↔ Controller

    --- MVP (Model–View–Presenter):

        --- Lepsza testowalność niż MVC
        --- Model – dane
        --- View – tylko wyświetla (pasywna)
        --- Presenter – cała logika, komunikuje się z View
        --- Zastosowanie: aplikacje desktopowe, mobilne
        --- Plusy: łatwe testy
        --- Minusy: więcej kodu
        --- View ↔ Presenter ↔ Model

    --- MVVM (Model–View–ViewModel):

        --- Nowoczesny wzorzec, data binding
        --- Model – dane
        --- View – UI
        --- ViewModel – logika + stan UI
        --- Zastosowanie: WPF, Xamarin, MAUI, Unity (częściowo)
        --- Plusy: świetna separacja, testy
        --- Minusy: bardziej złożony
        --- View ↔ ViewModel ↔ Model

    --- TL;DR – kiedy co stosować:

        --- Wzorzec - Kiedy używać
        --- MVC - Web, backend
        --- VC - Unity, proste gry
        --- MVP	- UI + testy
        --- MVVM - Aplikacje UI (WPF, mobile)

Podstawy programowania w Unity:

    1. Czym jest Unity
        Unity to silnik gier, który:
        zarządza scenami, obiektami i ich cyklem życia
        używa C# jako głównego języka
        działa w oparciu o architekturę komponentową


    2. Scene (Scena)
        Scena to poziom / świat gry
        Zawiera GameObjecty
        Projekt może mieć wiele scen (menu, poziom, ekran ładowania)


    3. GameObject
        Podstawowy obiekt w Unity
        Sam z siebie nic nie robi
        Zachowanie jest dodawane przez komponenty
        Przykłady:
        Player
        Enemy
        Camera
        Light


    4. Components (Komponenty)
        Komponenty nadają funkcjonalność GameObjectowi.
        Najczęstsze:

        Transform (pozycja, rotacja, skala)
        Renderer (renderowanie)
        Collider (kolizje)
        Rigidbody (fizyka)
        Script (C#)
        Skrypt to również komponent

    5. Skrypty i MonoBehaviour
            Każdy skrypt Unity:
            using UnityEngine;

            public class Player : MonoBehaviour
            {
            }

        MonoBehaviour – klasa bazowa logiki
        Skrypt musi być przypięty do GameObjectu


    6. Cykl życia skryptu (bardzo ważne)
        Główne metody:
        Awake()        // inicjalizacja
        OnEnable()    // obiekt włączony
        Start()       // start logiki
        Update()       // każda klatka
        FixedUpdate()  // fizyka
        LateUpdate()   // po Update
        OnDisable()    // obiekt wyłączony
        OnDestroy()    // usunięcie


    7. Transform — podstawa ruchu
            transform.position += Vector3.forward * Time.deltaTime;

        position – pozycja
        rotation – obrót
        localScale – skala


    8. Update i Time.deltaTime
            void Update()
            {
                transform.Translate(Vector3.right * speed * Time.deltaTime);
            }

        Update() wywoływane co klatkę
        Time.deltaTime uniezależnia ruch od FPS


    9. Wejście (Input)
        Klawiatura
        if (Input.GetKey(KeyCode.W))
        {
            // ruch do przodu
        }

        Pojedynczy klawisz
        if (Input.GetKeyDown(KeyCode.Space))
        {
            Jump();
        }


    10. Fizyka
        Rigidbody
        Rigidbody rb;

            void Start()
            {
                rb = GetComponent<Rigidbody>();
            }

            void FixedUpdate()
            {
                rb.AddForce(Vector3.up * 5);
            }

        Fizyka → FixedUpdate
        Nie poruszaj Rigidbody przez transform


    11. Kolizje
        void OnCollisionEnter(Collision col)
        {
            if (col.gameObject.CompareTag("Enemy"))
            {
                Debug.Log("Uderzenie!");
            }
        }


    12. Prefab
        Szablon GameObjectu
        Można tworzyć kopie w trakcie gry
        Instantiate(enemyPrefab, position, rotation);


    13. Tagi i warstwy
        Tag – oznaczenie logiczne (Player, Enemy)
        Layer – fizyka, kamera, renderowanie


    14. Pola publiczne i Inspector
        public float speed = 5f;
        Widoczne w Inspectorze
        Można zmieniać bez rekompilacji
        [SerializeField] private int hp;


    15. Komunikacja między obiektami
        public GameObject target;
        Przypisywane przez Inspector (drag & drop)


    16. Debugowanie:
        Debug.Log("Wiadomość");
        Do sprawdzania logiki


    TL;DR:
        Wszystko = GameObject + Komponenty
        Skrypt = komponent
        Logika → Update
        Fizyka → FixedUpdate
        Ustawienia → Inspector
        Powtarzalne obiekty → Prefab
