# Opis projektu
Nowa metoda wykrywania nieprawidłowości w przebiegach EKG.

Wykożystanie bazy przebiegów arytmii MIT-BIH.

Celem pracy jest projekt i implementacja nowej metody wspomagającej diagnozowanie chorób serca na podstawie EKG. Metoda będzie używała nowatorskiego podejścia wykorzystującego głębokie sieci neuronowe. 

TensorFlow + Keras

# Kolejność uruchamiania
1. csv_ann_type.py
2. mod_csv_ann.py
3. png_spec.py 

(usunąć pliki z "rejected_type_N", "train_val_test")
4. image_split.py
5. wstawienie spakowanych zdjęć (.zip) na dysk
6. podłączenie dyku w colab i uruchomienie pliku z folderu /classification

# Opis programów

Starałem się używać języka angielskiego, komentarze, zmienne itp.

### folder główny

csv_ann_type.py - wyszukiwanie wzniesień w plikach testowych bazy mit-bih wykożystując adnotacje, 
zapisanie pliku grupując po typach arytmii, nie ma tu odrzucania plików z małą ilością danych;

mod_csv_ann.py - kożysta na zrobionym wcześniej pliku csv wycinków sygnału by przetworzyć sygnał
i stworzyć nowe wycinki, stworzony w celu zwiększenia ilości zdjęć spektrogramów typu_F i grupy_F;

png_spec.py - tworzenie spektrogramów i zapisywanie ich jako zdjęcia o rozmiarach 220x220 RGB, 
robione jest to tylko dla wygranych (z dużą ilością przedziałów) typów bicia serca;

image_split.py - pozwala na podzielenie zdjęć na sety (train/dev/test) do późniejszego trenowania sieci 
neuronowej;

### OLD/

macierz_pomylek.py - Macierz pomyłek ale z możliwością ustawienia zakresu koloru, przydatne gdy 
liczba danych w konkretnych klasach jest zróżnicowana;

file_move.py - Przenosi nadmiar zdjęć grupy N, zostawiając tylko 9k zdjęć (po 3k z każdego typu 
należącego do tej grupy);

sig_display.py - wyświetlenie subplotów na potrzeby pokazania i zobaczenia jak to wygląda, 
zdjęcia spektrogramów oraz nie przetworzone przebiegi po wycięciu przedziałów;

load_data_train_test.py - tworzenie plików z powstałych wcześniej zdjęć spektrogramów: X_train_test.npz 
i y_train_test.npz, są to pliki zkompresowane numpy, pozwalają znacząco zmniejszyć rozmiar danych 
i nie ma już problemów z dużą ilością zdjęć oraz ich rozmiarem, w jednym pliku są dane treningowe i testowe;

create_csv_pat.py - wyszukiwanie wzniesień używając biblioteki wfdb bez uwzględnienia adnotacji;

create_csv_ann_pat.py - wyszukiwanie wzniesień w plikach testowych bazy mit-bih wykożystując adnotacje, 
zapisanie pliku grupując po pacjentach;

create_jpg.py - zapisywanie stworzonych plików .CSV w formie zdjęcia by sprawdzić na szybko poprawność wyszukania wzniesień;

OLD_create_png_spectrogram.py - przykładowe tworzenie spektrogramu używając biblioteki "signal";

load_data.py - tworzenie plików z powstałych wcześniej zdjęć spektrogramów: X_train.npz, y_train.npz, 
X_test.npz, y_test.npz są to pliki zkompresowane numpy, pozwalają znacząco zmniejszyć rozmiar danych 
i nie ma już problemów z dużą ilością zdjęć oraz ich rozmiarem;