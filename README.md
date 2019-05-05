# Ściąga poleceń vima

## Global
```bash
:help słowo # otwórz pomoc dla "słowo"
:o plik       # otwórz plik
:saveas plik  # zapisz jako plik
:close        # close current pane
```

## Poruszanie kursorem
```bash
h        # przenieś kursor w lewo
j        # przenieś kursor w dół
k        # przenieś kursor w górę
l        # przenieś kursor w prawo
H        # przenieś kursor do góry ekranu
M        # przenieś kursor na środek ekranu
L        # przenieś kursor do dołu ekranu
w        # jump forwards to the start of a word
W        # jump forwards to the start of a word (words can contain punctuation)
e        # jump forwards to the end of a word
E        # jump forwards to the end of a word (words can contain punctuation)
b        # jump backwards to the start of a word
B        # jump backwards to the start of a word (words can contain punctuation)
0        # przejdź do początku linii
^        # przejdź do pierwszego niepustego znaku w linii
$        # przejdź do końca linii
g_       # przejdź do ostatniego niepustego znaku w linii
gg       # idź do pierwszej linii dokumentu
G        # idź do ostaniej linii dokumentu
5G       # idź do linii piątej
fx       # przejdź do następnego wystąpienia znaku x
tx       # jump to before next occurrence of character x
}        # jump to next paragraph (or function/block, when editing code)
{        # jump to previous paragraph (or function/block, when editing code)
zz       # center cursor on screen
Ctrl + b # przesuń kursor do tyłu o jeden pełny ekran
Ctrl + f # przesuń kursor do przodu o jeden pełny ekran
Ctrl + d # przesuń kursor do przodu o połowę ekranu
Ctrl + u # przesuń kursor do tyłu o połowę ekranu
```

## Wstawianie tekstu
```bash
i        # wstaw tekst przed kursorem
I        # wstaw tekst na początku linii
a        # wstaw (appenduj) tekst za kursorem
A        # wstaw (appenduj) tekst na końcu linii
o        # appenduj (otwórz) nową linię poniżej obecnej
O        # appenduj (otwórz) nową linię powyżej obecnej
ea       # wstaw (appenduj) tekst na końcu słowa
Esc      # wyjdź z trybu wstawiania tekstu
```

## Edytowanie
```bash
r        # zamień pojedyńczy znak
J        # dołącz linię poniżej do obecnej
cc       # change (replace) entire line
cw       # change (replace) to the start of the next word
ce       # change (replace) to the end of the next word
cb       # change (replace) to the start of the previous word
c0       # change (replace) to the start of the line
c$       # change (replace) to the end of the line
s        # delete character and substitute text
S        # delete line and substitute text (same as cc)
xp       # transpose two letters (delete and paste)
.        # powtórz ostatnie polecenie
u        # cofnij ostatnią operację
Ctrl + r # cofnij undo
```

## Zaznaczanie tekstu (tryb wizualny)
```bash
v        # start visual mode, mark lines, then do a command (like y-yank)
V        # start linewise visual mode
o        # move to other end of marked area
O        # move to other corner of block
aw       # zaznacz słowo
ab       # a block with ()
aB       # a block with {}
ib       # inner block with ()
iB       # inner block with {}
Esc      # wyjdź z trybu wizualnego
Ctrl + v # start visual block mode
```

## Komendy trybu wizualnego
```bash
>       # przesuń tekst w prawo
<       # przesuń tekst w lewo
y       # yankuj (kopiuj) zaznaczony tekst
d       # usuń zaznaczony tekst
~       # switch case
```

## Usuwanie, kopiowanie i wklejanie tekstu
```bash
yy       # yankuj (kopiuj) linię
2yy      # yankuj (kopiuj) dwie linie
yw       # yankuj (kopiuj) znaki od obecnej pozycji kursora do początku następnego słowa (znaki z nastepnego słowa nie są        kopiowane)
y$       # yankuj (kopiuj) do końca linii
p        # wklej tekst za kursorem
P        # wklej tekst przed kursorem
dd       # usuń (wytnij) linię
2dd      # usuń (wytnij) 2 linie
dw       # usuń (wytnij) znaki od obecnej pozycji kursora do początku następnego słowa (znaki z nastepnego słowa nie są        usuwane)
D        # usuń (wytnij) do końca linii
d$       # usuń (wytnij) do końca linii
d^       # usuń (wytnij) do pierwszego niepustego znaku w linii
d0       # usuń (wytnij) do początku linii
x        # usuń (wytnij) znak
```

## Znajdowanie i zamienianie tekstu
```bash
/wzór       # szukaj (do przodu) słowa wzór
?wzór       # szukaj (do tyłu) słowa wzór
\vpattern      # 'very magic' pattern: non-alphanumeric characters are interpreted as special regex symbols (no escaping needed)
n              # repeat search in same direction
N              # repeat search in opposite direction
:%s/old/new/g  # replace all old with new throughout file
:%s/old/new/gc # replace all old with new throughout file with confirmations
:noh           # wyłącz podświetlenie dopasowań z wyszukiwania 
```

## Wyszukiwanie w wielu plikach
```bash
:vimgrep /xyz/ {file} #  szukaj "xyz" w wielu plikach
:cn                       # przejdź do następnego dopasowania
:cp                       # przejdź do poprzedniego dopasowania
:copen                    # otwórz okno zawierające listę dopasowań
```

## Wychodzenie z vima i zapisywanie pliku
```bash
:w              # zapisz plik ale nie wychódź z vima
:w !sudo tee %  # write out the current file using sudo
:wq or :x or ZZ # zapisz i wyjdź z vima
:q              # wyjdź (nie działa jeśli są niezapisane zmiany)
:q! or ZQ       # wyjdź i odrzuć niezapisane zmiany
```

## Praca z wieloma plikami
```bash
:e file       # edytuj plik w nowym buforze
:bnext lub :bn # idź do następnego buforu
:bprev lub :bp # idź do poprzedniego buforu
:bd           # delete a buffer (close a file)
:ls           # list all open buffers
:sp file      # open a file in a new buffer and split window
:vsp file     # open a file in a new buffer and vertically split window
Ctrl + ws     # split window
Ctrl + ww     # switch windows
Ctrl + wq     # quit a window
Ctrl + wv     # split window vertically
Ctrl + wh     # move cursor to the left window (vertical split)
Ctrl + wl     # move cursor to the right window (vertical split)
Ctrl + wj     # move cursor to the window below (horizontal split)
Ctrl + wk     # move cursor to the window above (horizontal split)
```

## Zakładki
```bash
:tabnew or :tabnew file # open a file in a new tab
Ctrl + wT               # move the current split window into its own tab
gt or :tabnext or :tabn # move to the next tab
gT or :tabprev or :tabp # move to the previous tab
<number>gt              # move to tab <number>
:tabmove <number>       # move current tab to the <number>th position (indexed from 0)
:tabclose or :tabc      # close the current tab and all its windows
:tabonly or :tabo       # close all tabs except for the current one
:tabdo command          # run the command on all tabs (e.g. :tabdo q - closes all opened tabs)
```
