# robert-adhd - output style do Claude Code

Dwa gotowe **output style'e** do Claude Code, które sprawiają, że agent przestaje gadać, a zaczyna dowozić: akcja w pierwszej linii, kroki numerowane, listy maksymalnie po 5 pozycji, zero "Świetnie!" na początku i "Daj znać, gdyby coś" na końcu.

Powstały na potrzeby odcinka na moim kanale YouTube o skillach i pluginach do Claude Code.

## Dlaczego output style, a nie skill

Oryginał ([`ayghri/i-have-adhd`](https://github.com/ayghri/i-have-adhd)) to skill spakowany w plugin. Działa świetnie, ale ma jedną cechę, o której warto wiedzieć: komendę `/i-have-adhd` odpalasz **na bieżącą sesję**. Nowa sesja - odpalasz od nowa (autor przewidział na to plik-flagę `~/.claude/.i-have-adhd-always`).

Output style **zostaje włączony na stałe**, między sesjami, i przełączasz go w ustawieniach Claude Code. Dlatego przełożyłem te zasady na output style i przy okazji wymieszałem z własnym stylem pracy.

## Co jest w środku

| Plik | Co to jest | Dla kogo |
|---|---|---|
| `i-have-adhd.md` | Czysty port 10 zasad z oryginalnego repo, po angielsku. Same reguły formatu odpowiedzi, bez osobowości. | Chcesz dokładnie to, co w oryginale, ale jako output style |
| `robert-adhd.md` | Mój miks: te same 10 zasad **plus** styl pracy, którego używam na co dzień - partner, który myśli razem z Tobą, tłumaczy analogiami, kwestionuje założenia i mówi wprost, gdy bierzesz na siebie za dużo albo budujesz od zera coś, co już istnieje. Po polsku. | Chcesz gotowca z charakterem i pracujesz po polsku |

**Uwaga techniczna do `robert-adhd.md`:** ma we frontmatterze `keep-coding-instructions: false`, czyli **zastępuje** domyślne instrukcje kodowania Claude Code swoimi. To celowe - taki był mój wcześniejszy styl. Jeśli wolisz, żeby domyślne zachowanie zostało nietknięte, a doszły tylko reguły formatu - usuń tę linijkę albo weź `i-have-adhd.md`.

## Instalacja

Skopiuj wybrany plik (albo oba) do katalogu output style'ów:

```bash
mkdir -p ~/.claude/output-styles
curl -o ~/.claude/output-styles/robert-adhd.md \
  https://raw.githubusercontent.com/Szewowsky/robert-adhd-output-style/main/robert-adhd.md
```

Potem w Claude Code wpisz:

```
/settings
```

i w sekcji **"Preferred output style"** wybierz `robert-adhd`. W terminalu ten sam ekran otwiera `/config`.

I tyle. Styl zostaje włączony, dopóki nie wrócisz w to samo miejsce i nie wybierzesz `Default`.

Jedna rzecz, która potrafi zmylić: świeżo skopiowany plik pojawia się na liście dopiero **w nowej sesji**. Jeśli go nie widzisz - zacznij nową rozmowę i sprawdź jeszcze raz.

> Starsze wersje Claude Code miały osobną komendę `/output-style`. Została usunięta - jeśli masz ją u siebie, działa tak samo, ale docelowo idź przez `/settings`.

Katalog `~/.claude/output-styles/` działa globalnie, we wszystkich projektach. Jeśli chcesz styl tylko w jednym projekcie, wrzuć plik do `.claude/output-styles/` w tym projekcie.

## Zrób własny

Oba pliki to zwykły markdown z krótkim frontmatterem (`name`, `description`) - potraktuj je jak punkt startowy, nie świętość. Dopisz swoje zasady, wytnij te, które Ci nie pasują, zmień język. Cała robota to jeden plik tekstowy.

## Licencja i podziękowania

10 zasad ADHD-friendly pochodzi z [`ayghri/i-have-adhd`](https://github.com/ayghri/i-have-adhd) (MIT, © 2026 Ayoub Ghriss) - oryginalna licencja jest w pliku `LICENSE-i-have-adhd`. Jeśli pracujesz w Claude Code, Codex, Cursor czy Gemini CLI, zajrzyj do oryginału: autor utrzymuje wersje pod wszystkie te narzędzia i robi to dużo dokładniej, niż wymaga tego jeden plik.

Adaptacja i wersja `robert-adhd` - MIT, © 2026 Robert Szewczyk.
