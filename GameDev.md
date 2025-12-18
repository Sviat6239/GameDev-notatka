# GameDev Notatki

## Framework vs Silnik
- **Framework** jest zawsze zupełnie free
- **Silnik** ma większe możliwości do developmentu

## Silniki Gier

### Unity
- Skrypty w C#
- Zaawansowany Asset Store
- Profesjonalne narzędzia

### Godot
- Open Source
- Przyjazny dla użytkownika
- Wsparcie dla 2D i 3D

### Unreal Engine
- Fotorealistyczna grafika
- Wizualne skryptowanie
- Funkcje kinematograficzne
- Wsparcie dla VR i AR

## Wybór Właściwego Silnika
- Zakres projektu
- Doświadczenie w rozwoju
- Społeczność i wsparcie

## Licencje

### Godot
- Free 100%, open source

### Unreal Engine
- Powyżej 1 miliona dolarów trzeba płacić procent

### Unity
- Powyżej 200K za rok trzeba przejść na licencje Pro (2 koła $)

## Systemy Kontroli Wersji (Version Control Systems)
Systemy kontroli wersji służą do zarządzania zmianami w kodzie źródłowym projektu. Są niezbędne przy pracy zespołowej, ale również bardzo pomocne w projektach indywidualnych, ponieważ pozwalają:
- Przechowywać historię zmian
- Wracać do poprzednich wersji projektu
- Pracować równolegle nad różnymi funkcjami
- Bezpiecznie eksperymentować bez psucia głównej wersji projektu

### Przykłady Systemów Kontroli Wersji
- **Git** – najpopularniejszy, rozproszony system kontroli wersji
- **GitHub** – platforma hostingowa dla repozytoriów Git
- **Perforce** – scentralizowany system, często używany w dużych studiach (np. gamedev)
- **Subversion (SVN)** – starszy, scentralizowany system kontroli wersji

## Git i GitHub – Różnice i Podstawowe Pojęcia

### Git
- To sam system kontroli wersji, który działa lokalnie na komputerze
- Pozwala tworzyć repozytoria, zapisywać zmiany i zarządzać historią projektu
- Możliwe jest uruchomienie własnego serwera Git bez korzystania z GitHuba

### GitHub
- To zewnętrzna platforma do przechowywania repozytoriów Git w chmurze
- Umożliwia współpracę zespołową, code review i zarządzanie projektami

### Podstawowe Pojęcia i Komendy Git
- **Repozytorium (Repository)**: Miejsce, w którym przechowywany jest projekt wraz z pełną historią zmian
- **Commit**: Zapis stanu projektu w danym momencie. Commit zawiera zmiany oraz opis (komentarz)
- **Push**: Wysyłanie lokalnych commitów na zdalne repozytorium (np. GitHub)
- **Fetch**: Pobieranie informacji o zmianach z repozytorium zdalnego bez ich łączenia z lokalnym kodem
- **Pull**: Pobieranie zmian z repozytorium zdalnego i automatyczne scalanie ich z lokalną gałęzią (fetch + merge)
- **Branch (Gałąź)**: Oddzielna linia rozwoju projektu, pozwalająca pracować nad funkcją bez wpływu na główną wersję
- **Merge**: Łączenie jednej gałęzi z inną (np. gałęzi funkcji z develop lub main)
- **Rebase**: Przeniesienie commitów na inny punkt w historii w celu uzyskania czystszej struktury commitów
- **Pull Request (PR)**: Prośba o połączenie zmian z jednej gałęzi do drugiej, często połączona z code review
- **Fork**: Kopia cudzego repozytorium na własnym koncie GitHub, umożliwiająca niezależną pracę nad projektem

## GitFlow – Model Pracy z Gałęziami
GitFlow to popularny model organizacji pracy w repozytorium Git, który jasno określa role poszczególnych gałęzi.

- **main**: Stabilna wersja produkcyjna projektu. Kod znajdujący się tutaj jest gotowy do wydania
- **develop**: Gałąź rozwojowa, na której integrowane są nowe funkcje przed wydaniem
- **features/***: Gałęzie do tworzenia nowych funkcjonalności. Tworzone z develop i po zakończeniu pracy scalane z powrotem do develop
- **release/***: Gałęzie przygotowujące projekt do wydania (bugfixy, dokumentacja, testy). Po zakończeniu scalane do main i develop
- **hotfix/***: Gałęzie do szybkiego naprawiania krytycznych błędów w wersji produkcyjnej. Tworzone z main i scalane zarówno do main, jak i develop

## Comprehensive Guide of Execution of Unity Event Functions

### Awake()
- Wywoływana raz, przy ładowaniu obiektu
- Działa nawet, gdy obiekt jest wyłączony
- Inicjalizacja wewnętrzna obiektu (zmienne, komponenty)
- Użycie: przygotowanie danych, GetComponent, singletony

### OnEnable()
- Wywoływana za każdym razem, gdy obiekt zostaje włączony
- Po Awake(), przed Start()
- Użycie: podpinanie eventów, uruchamianie timerów, reset stanu

### Start()
- Wywoływana raz, przed pierwszym Update()
- Tylko jeśli obiekt jest aktywny
- Użycie: logika zależna od innych obiektów, start gry

### FixedUpdate()
- Wywoływana w stałym kroku czasu (fizyka)
- Niezależna od FPS
- Użycie: fizyka, Rigidbody, siły, ruch fizyczny

### Update()
- Wywoływana co klatkę
- Zależna od FPS
- Użycie: input, logika gry, timery

### LateUpdate()
- Wywoływana po Update() w tej samej klatce
- Użycie: kamera, korekty pozycji po ruchu obiektów

### OnDisable()
- Wywoływana, gdy obiekt lub komponent zostaje wyłączony
- Użycie: odpinanie eventów, zatrzymanie coroutine

### OnDestroy()
- Wywoływana przy usuwaniu obiektu z pamięci
- Użycie: sprzątanie zasobów, zapisy, logi

## Programowanie

### Typy Danych

#### Typy Proste (Prymitywne)
```csharp
int a = 10;          // liczby całkowite
float b = 3.14f;    // liczby zmiennoprzecinkowe (32-bit)
double c = 3.14;    // liczby zmiennoprzecinkowe (64-bit)
bool flag = true;   // wartości logiczne
char znak = 'A';    // pojedynczy znak
```

#### Typy Referencyjne
```csharp
string tekst = "Cześć";   // tekst
object obj = null;       // obiekt ogólny
```

### Zmienne i Stałe
```csharp
int liczba = 5;
liczba = 10;     // zmienna – można zmieniać

const int MAX = 100; // stała – nie można zmieniać
```

### Operatory
- Arytmetyczne: `+ - * /`
- Porównania: `== != > < >= <=`
- Logiczne: `&& || !`

### Instrukcje Warunkowe

#### if / else
```csharp
if (liczba > 0)
{
    Console.WriteLine("Dodatnia");
}
else
{
    Console.WriteLine("Ujemna lub zero");
}
```

#### switch
```csharp
switch (liczba)
{
    case 1:
        Console.WriteLine("Jeden");
        break;
    default:
        Console.WriteLine("Inna wartość");
        break;
}
```

### Pętle

#### for
```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

#### while
```csharp
while (liczba > 0)
{
    liczba--;
}
```

#### foreach
```csharp
int[] tablica = {1, 2, 3};
foreach (int x in tablica)
{
    Console.WriteLine(x);
}
```

### Metody i Procedury

#### Procedura (bez zwracanej wartości)
```csharp
void Powitaj()
{
    Console.WriteLine("Witaj!");
}
```

#### Metoda (zwraca wartość)
```csharp
int Dodaj(int a, int b)
{
    return a + b;
}
```

### Klasy i Obiekty
```csharp
class Player
{
    public int HP;

    public void TakeDamage(int dmg)
    {
        HP -= dmg;
    }
}

// Tworzenie obiektu
Player p = new Player();
p.HP = 100;
p.TakeDamage(20);
```

### Konstruktory
```csharp
class Enemy
{
    public int HP;

    public Enemy(int hp)
    {
        HP = hp;
    }
}
```

### Modyfikatory Dostępu
- **public** – dostępne wszędzie
- **private** – tylko w klasie
- **protected** – klasa + klasy dziedziczące

### Dziedziczenie
```csharp
class Animal
{
    public void Speak() { }
}

class Dog : Animal
{
}
```

## Wzorce Architektoniczne (MVC, MVP, MVVM, VC)

### MVC (Model–View–Controller)
- Najpopularniejszy klasyczny wzorzec
- **Model** – dane i logika biznesowa
- **View** – interfejs użytkownika (UI)
- **Controller** – pośrednik: reaguje na input i steruje Modelem
- Zastosowanie: web (ASP.NET MVC), klasyczne aplikacje
- Plusy: czytelny podział odpowiedzialności
- Minusy: Controller bywa „przeładowany”
- Przepływ: User → Controller → Model → View

### VC (View–Controller)
- Uproszczony wariant MVC
- **View** – UI
- **Controller** – logika + dane (brak osobnego Modelu)
- Zastosowanie: Unity, małe aplikacje
- Plusy: prostota
- Minusy: słaba skalowalność, mieszanie logiki z UI
- Przepływ: View ↔ Controller

### MVP (Model–View–Presenter)
- Lepsza testowalność niż MVC
- **Model** – dane
- **View** – tylko wyświetla (pasywna)
- **Presenter** – cała logika, komunikuje się z View
- Zastosowanie: aplikacje desktopowe, mobilne
- Plusy: łatwe testy
- Minusy: więcej kodu
- Przepływ: View ↔ Presenter ↔ Model

### MVVM (Model–View–ViewModel)
- Nowoczesny wzorzec, data binding
- **Model** – dane
- **View** – UI
- **ViewModel** – logika + stan UI
- Zastosowanie: WPF, Xamarin, MAUI, Unity (częściowo)
- Plusy: świetna separacja, testy
- Minusy: bardziej złożony
- Przepływ: View ↔ ViewModel ↔ Model

### TL;DR – Kiedy Co Stosować
| Wzorzec | Kiedy Używać |
|---------|---------------|
| MVC     | Web, backend |
| VC      | Unity, proste gry |
| MVP     | UI + testy |
| MVVM    | Aplikacje UI (WPF, mobile) |

## Podstawy Programowania w Unity

### 1. Czym Jest Unity
Unity to silnik gier, który:
- Zarządza scenami, obiektami i ich cyklem życia
- Używa C# jako głównego języka
- Działa w oparciu o architekturę komponentową

### 2. Scene (Scena)
- Scena to poziom / świat gry
- Zawiera GameObjecty
- Projekt może mieć wiele scen (menu, poziom, ekran ładowania)

### 3. GameObject
- Podstawowy obiekt w Unity
- Sam z siebie nic nie robi
- Zachowanie jest dodawane przez komponenty
- Przykłady: Player, Enemy, Camera, Light

### 4. Components (Komponenty)
Komponenty nadają funkcjonalność GameObjectowi. Najczęstsze:
- Transform (pozycja, rotacja, skala)
- Renderer (renderowanie)
- Collider (kolizje)
- Rigidbody (fizyka)
- Script (C#)
- Skrypt to również komponent

### 5. Skrypty i MonoBehaviour
Każdy skrypt Unity:
```csharp
using UnityEngine;

public class Player : MonoBehaviour
{
}
```
- MonoBehaviour – klasa bazowa logiki
- Skrypt musi być przypięty do GameObjectu

### 6. Cykl Życia Skryptu (bardzo ważne)
Główne metody:
- `Awake()` – inicjalizacja
- `OnEnable()` – obiekt włączony
- `Start()` – start logiki
- `Update()` – każda klatka
- `FixedUpdate()` – fizyka
- `LateUpdate()` – po Update
- `OnDisable()` – obiekt wyłączony
- `OnDestroy()` – usunięcie

### 7. Transform — Podstawa Ruchu
```csharp
transform.position += Vector3.forward * Time.deltaTime;
```
- position – pozycja
- rotation – obrót
- localScale – skala

### 8. Update i Time.deltaTime
```csharp
void Update()
{
    transform.Translate(Vector3.right * speed * Time.deltaTime);
}
```
- Update() wywoływane co klatkę
- Time.deltaTime uniezależnia ruch od FPS

### 9. Wejście (Input)
Klawiatura:
```csharp
if (Input.GetKey(KeyCode.W))
{
    // ruch do przodu
}
```
Pojedynczy klawisz:
```csharp
if (Input.GetKeyDown(KeyCode.Space))
{
    Jump();
}
```

### 10. Fizyka
Rigidbody:
```csharp
Rigidbody rb;

void Start()
{
    rb = GetComponent<Rigidbody>();
}

void FixedUpdate()
{
    rb.AddForce(Vector3.up * 5);
}
```
- Fizyka → FixedUpdate
- Nie poruszaj Rigidbody przez transform

### 11. Kolizje
```csharp
void OnCollisionEnter(Collision col)
{
    if (col.gameObject.CompareTag("Enemy"))
    {
        Debug.Log("Uderzenie!");
    }
}
```

### 12. Prefab
- Szablon GameObjectu
- Można tworzyć kopie w trakcie gry
- `Instantiate(enemyPrefab, position, rotation);`

### 13. Tagi i Warstwy
- Tag – oznaczenie logiczne (Player, Enemy)
- Layer – fizyka, kamera, renderowanie

### 14. Pola Publiczne i Inspector
```csharp
public float speed = 5f;
```
- Widoczne w Inspectorze
- Można zmieniać bez rekompilacji
- `[SerializeField] private int hp;`

### 15. Komunikacja Między Obiektami
```csharp
public GameObject target;
```
- Przypisywane przez Inspector (drag & drop)

### 16. Debugowanie
```csharp
Debug.Log("Wiadomość");
```
- Do sprawdzania logiki

### TL;DR
- Wszystko = GameObject + Komponenty
- Skrypt = komponent
- Logika → Update
- Fizyka → FixedUpdate
- Ustawienia → Inspector
- Powtarzalne obiekty → Prefab
