# Računalni vid — laboratorijske vježbe

Materijali za praktične vježbe iz računalnog vida u Pythonu. Kroz Jupyter notebookove studenti upoznaju prikaz i obradu digitalnih slika, segmentaciju, geometrijske transformacije, podudaranje značajki te osnove klasifikacije slika neuronskim mrežama.

Fond vježbi iznosi **30 nastavnih sati**, pri čemu jedan nastavni sat traje **45 minuta**. Vježbe su organizirane u **15 termina po 90 minuta**, odnosno ukupno **22,5 sati stvarnog rada**.

Zbirka sadrži 39 lekcija. Raspored određuje dijelove koji se obrađuju na nastavi, a ostali primjeri i zadaci služe za samostalni rad i dodatno istraživanje.

## Ciljevi vježbi

Nakon rada na osnovnim cjelinama student treba moći:

- učitati, prikazati i obrađivati sliku kao NumPy polje;
- primijeniti pragovanje, morfološke operacije i analizu povezanih komponenti;
- odabrati filtar, prostor boja i postupak detekcije rubova za jednostavan zadatak;
- transformirati sliku, podudariti značajke i primijeniti homografiju;
- izgraditi i usporediti jednostavne klasifikatore te prepoznati prenaučenost;
- evaluirati klasifikaciju matricom zabune, preciznošću i odzivom te primijeniti prijenos učenja.

## Predznanje i alati

Očekuje se osnovno poznavanje Pythona: varijable, petlje, funkcije i rad s poljima. Matematički pojmovi potrebni za pojedinu vježbu kratko se ponavljaju uz primjer; detaljni izvodi obrađuju se na predavanjima ili u dodatnim materijalima.

| Alat / biblioteka | Namjena |
|---|---|
| Python | Programiranje i izvođenje primjera |
| JupyterLab | Otvaranje i izvršavanje notebookova |
| NumPy | Polja, matrice i numeričke operacije |
| Matplotlib | Prikaz slika, grafova i rezultata |
| OpenCV | Obrada slika i geometrijski postupci |
| PyTorch i torchvision | Neuronske mreže i prethodno trenirani modeli |
| PyWavelets | Dodatna lekcija o valićima |

## Organizacija materijala

README se nalazi u korijenu repozitorija. Notebookovi zadržavaju postojeće nazive s nastavkom `_hr.ipynb`.

| Putanja | Sadržaj |
|---|---|
| `README.md` | Opis, pokretanje, raspored i zadaci za samostalni rad |
| `notebooks/` | Prevedeni notebookovi, od lekcije 01 do 39 |
| `img/` | Slike i GIF-ovi potrebni za primjere |
| `data/` | Preuzeti skupovi podataka, prema uputama pojedinog notebooka |
| `zadaci/` | Predlošci domaćih zadataka, kada su objavljeni |
| `references.html` | Bibliografija na koju vode postojeće poveznice iz lekcija |

Notebookovi koriste relativne putanje poput `../img/rose.jpg`. Direktoriji `notebooks/` i `img/` zato trebaju biti neposredno u korijenu repozitorija. Za pokretanje su potrebne i slike koje pripadaju pojedinoj lekciji.

## Pokretanje

### 1. Preuzimanje repozitorija

Klonirajte repozitorij pomoću Gita ili preuzmite ZIP arhivu preko izbornika **Code → Download ZIP**. Otvorite terminal u korijenu preuzetog repozitorija.

### 2. Virtualno okruženje

Izradite virtualno okruženje:

```bash
python -m venv .venv
```

Aktivirajte ga na Windowsu u Command Promptu:

```bat
.venv\Scripts\activate.bat
```

Na Linuxu ili macOS-u:

```bash
source .venv/bin/activate
```

Ako se Python na vašem sustavu pokreće naredbom `python3`, koristite je umjesto `python`.

### 3. Instalacija biblioteka

Za obradu slika i pokretanje notebookova:

```bash
python -m pip install jupyterlab numpy matplotlib opencv-python PyWavelets
```

Za lekcije o neuronskim mrežama instalirajte i PyTorch te torchvision. Odgovarajuću naredbu za svoj operacijski sustav i CPU/GPU odaberite u [službenim uputama za PyTorch](https://pytorch.org/get-started/locally/).

Paket `opencv-python` u kodu se uvozi pod nazivom `cv2`, a paket `PyWavelets` pod nazivom `pywt`.

### 4. Otvaranje notebooka

Iz korijena repozitorija pokrenite:

```bash
jupyter lab
```

Otvorite željeni notebook iz direktorija `notebooks/`. Ćelije izvršavajte redom od početka, pomoću **Shift + Enter**. Nakon promjene podataka ili modela ponovno izvršite sve ovisne ćelije.

Službene upute za instalaciju dostupne su u [dokumentaciji JupyterLaba](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html).

## Način rada na vježbama

Studenti dobivaju pripremljene primjere i tijekom nastave mijenjaju parametre, dopunjuju kod, uspoređuju rezultate i rješavaju odabrane zadatke. Brojevi lekcija označavaju notebookove, a ne termine nastave.

Okvirna podjela jednog termina:

| Aktivnost | Vrijeme |
|---|---:|
| Uvod i objašnjenje pojmova | 20 min |
| Zajednički praktični primjer | 20 min |
| Samostalni rad, usporedba rezultata i rasprava | 50 min |
| **Ukupno** | **90 min** |

U svakom terminu obrađuju se dijelovi navedeni u rasporedu. Preostali dijelovi istih notebookova dostupni su za ponavljanje i dodatne eksperimente.

## Raspored vježbi

| Termin | Lekcije | Sadržaj i opseg rada na nastavi | Praktični cilj |
|---:|---|---|---|
| 1 | [01](notebooks/lesson01_images_as_arrays_hr.ipynb), [02](notebooks/lesson02_image_arithmetic_hr.ipynb) | NumPy polja, učitavanje i prikaz slike, RGB/BGR, maske i aritmetika | Izdvojiti dio slike i promijeniti njegove vrijednosti |
| 2 | [03](notebooks/lesson03_thresholding_morphology_hr.ipynb), [04](notebooks/lesson04_floodfill_connected_components_hr.ipynb) | Pragovanje, erozija, dilatacija, otvaranje i povezane komponente | Izdvojiti i prebrojiti objekte; priprema za DZ1 |
| 3 | [05](notebooks/lesson05_moments_hr.ipynb), [06](notebooks/lesson06_eigen_covariance_hr.ipynb) | Površina, težište i orijentacija objekta; praktično tumačenje svojstvenih vektora | Označiti težište i glavnu os objekta, bez detaljnih matematičkih izvoda |
| 4 | [08](notebooks/lesson08_geometric_transformations_hr.ipynb), [09](notebooks/lesson09_warping_interpolation_hr.ipynb) | Rotacija, skaliranje, afina transformacija te usporedba interpolacija u OpenCV-ju | Transformirati sliku i objasniti razlike u rezultatu |
| 5 | [10](notebooks/lesson10_convolution_hr.ipynb), [11](notebooks/lesson11_smoothing_pyramids_hr.ipynb) | Konvolucija, jezgre, Gaussovo zaglađivanje i smanjivanje rezolucije | Usporediti učinak filtara i pokazati zašto zaglađivanje prethodi smanjivanju |
| 6 | [12](notebooks/lesson12_differentiation_edges_hr.ipynb) | Sobel i Canny; kratka demonstracija Houghovih pravaca | Detektirati rubove i ispitati utjecaj pragova |
| 7 | [14](notebooks/lesson14_nonlinear_filters_hr.ipynb), [18](notebooks/lesson18_color_spaces_hr.ipynb) | Medijanski filtar, demonstracija bilateralnog filtra te RGB/HSV segmentacija | Ukloniti šum i izdvojiti objekt prema boji; priprema za DZ2 |
| 8 | [19](notebooks/lesson19_clustering_hr.ipynb), [20](notebooks/lesson20_feature_detection_matching_hr.ipynb) | Kratki primjer k-meansa; glavni dio termina SIFT i test omjera; detektori kutova kao demonstracija | Pronaći odgovarajuće značajke na dvjema slikama |
| 9 | [23](notebooks/lesson23_model_fitting_ransac_hr.ipynb), [24](notebooks/lesson24_projective_geometry_hr.ipynb) | Intuicija RANSAC-a, homografija i korekcija perspektive, uz pripremljene funkcije | Ispraviti perspektivu fotografiranog dokumenta |
| 10 | [25](notebooks/lesson25_stitching_mosaicking_hr.ipynb) | Podudaranje značajki, procjena homografije, preslikavanje i miješanje | Spojiti dvije fotografije u panoramu; priprema za DZ3 |
| 11 | [26](notebooks/lesson26_image_formation_hr.ipynb), [27](notebooks/lesson27_camera_calibration_hr.ipynb) | Osnovni model kamere, distorzija i kalibracija na pripremljenim primjerima | Usporediti sliku ili točke prije i nakon uklanjanja distorzije |
| 12 | [30](notebooks/lesson30_projection_hr.ipynb), [31](notebooks/lesson31_neural_network_fundamentals_hr.ipynb) | Projekcija kao kratki uvod; linearni klasifikator, gubitak i gradijentni spust | Trenirati jednostavan klasifikator i pratiti gubitak |
| 13 | [32](notebooks/lesson32_multilayer_perceptrons_hr.ipynb), [33](notebooks/lesson33_optimization_hr.ipynb) | MLP, aktivacijska funkcija i treniranje u PyTorchu; usporedba SGD-a i Adama | Riješiti nelinearni klasifikacijski zadatak |
| 14 | [34](notebooks/lesson34_convolutional_neural_networks_hr.ipynb), [35](notebooks/lesson35_training_a_cnn_hr.ipynb) | Mali CNN, kratko treniranje, prenaučenost i augmentacija; dulji eksperimenti iz pripremljenih rezultata | Usporediti uspješnost na skupu za treniranje i validacijskom skupu |
| 15 | [36](notebooks/lesson36_image_classification_practice_hr.ipynb), [38](notebooks/lesson38_transfer_learning_hr.ipynb) | Matrica zabune, preciznost, odziv i prijenos učenja s pripremljenim modelom | Evaluirati klasifikator i uvježbati novi završni sloj; priprema za DZ4 |

## Domaći zadaci

Predviđene su četiri manje cjeline, svaka okvirno **45–60 minuta samostalnog rada**. Procjena se odnosi na osnovni zadatak uz poznate postupke i pripremljeno okruženje. Rokovi i način predaje objavljuju se uz pojedini zadatak.

| Zadatak | Zadaje se nakon | Sadržaj | Očekivani rezultat |
|---|---|---|---|
| **DZ1 — Segmentacija i brojanje** | Termina 2 | Na novoj slici primijeniti pragovanje i morfologiju, izdvojiti komponente i ukloniti sitni šum | Izvršen notebook, prikaz koraka i broj pronađenih objekata |
| **DZ2 — Filtri i boje** | Termina 7 | Usporediti dva postupka filtriranja te HSV maskom izdvojiti odabranu boju | Usporedni prikazi i kratko obrazloženje parametara |
| **DZ3 — Geometrija slike** | Termina 10 | Odabrati jedan zadatak: spojiti dvije vlastite fotografije ili ispraviti perspektivu dokumenta | Ulazne slike, konačni rezultat i opis ograničenja postupka |
| **DZ4 — Evaluacija klasifikatora** | Termina 15 | Promijeniti jednu postavku pripremljenog modela ili treniranja i usporediti rezultat s početnom konfiguracijom | Matrica zabune, preciznost i odziv po klasama te kratki zaključak |

Svaka predaja treba sadržavati kod koji se može ponovno izvršiti, korištene ulazne podatke ili uputu za njihovo preuzimanje te kratko tumačenje rezultata. Pri uporabi vlastitih ili vanjskih slika navedite izvor.

## Dodatne lekcije i izborna proširenja

Sljedeće lekcije proširuju osnovni raspored. Cijeli notebookovi iz ove tablice nisu dodatni obvezni domaći zadaci; pojedini primjeri mogu se koristiti za samostalno istraživanje ili projektnu nadogradnju.

| Lekcija | Tema | Kada je korisno nastaviti |
|---|---|---|
| [07](notebooks/lesson07_distance_measures_hr.ipynb) | Mjere udaljenosti | Nakon analize oblika i rada s poljima |
| [13](notebooks/lesson13_laplacian_pyramids_hr.ipynb) | Laplacian i Laplaceove piramide | Nakon konvolucije, piramida i detekcije rubova |
| [15](notebooks/lesson15_fourier_frequency_filtering_hr.ipynb) | Fourierova transformacija i frekvencijsko filtriranje | Nakon prostornih filtara |
| [16](notebooks/lesson16_wavelets_gabor_hr.ipynb) | Valići i Gaborovi filtri | Nakon konvolucije i frekvencijskih postupaka |
| [17](notebooks/lesson17_compression_hr.ipynb) | Kompresija, DCT i JPEG | Za istraživanje odnosa kvalitete slike i veličine datoteke |
| [21](notebooks/lesson21_optical_flow_hr.ipynb) | Optički tok | Nakon gradijenata i značajki; uvod u obradu videozapisa |
| [22](notebooks/lesson22_stereo_matching_hr.ipynb) | Stereo podudaranje i dubina | Za dodatnu cjelinu o stereo vidu i geometriji kamere |
| [28](notebooks/lesson28_epipolar_geometry_hr.ipynb) | Epipolarna geometrija | Nakon homografije i kalibracije, uz dodatno objašnjenje |
| [29](notebooks/lesson29_structure_from_motion_hr.ipynb) | Struktura iz gibanja i triangulacija | Nakon lekcije 28, kao vođena projektna nadogradnja |
| [37](notebooks/lesson37_classic_architectures_hr.ipynb) | Klasične arhitekture i rezidualne veze | Nakon osnovnog CNN-a |
| [39](notebooks/lesson39_visualizing_cnns_hr.ipynb) | Karte važnosti, Grad-CAM i t-SNE | Nakon treniranja i evaluacije CNN-a |

Dodatno se mogu istražiti i prošireni dijelovi lekcija iz osnovnog rasporeda: Huovi momenti, ručna implementacija interpolacije i konvolucije, Houghove kružnice, GMM i DBSCAN, Bayerov uzorak i gama korekcija, ručni backpropagation te inicijalizacija težina i rasporedi stope učenja.

## Praktične napomene

- **Izvršavanje redom:** nakon ponovnog pokretanja kernela izvršite notebook od prve ćelije. Varijable iz ranijih ćelija potrebne su kasnijim primjerima.
- **Nedostajući `cv2`:** u ćeliji notebooka pokrenite `%pip install opencv-python`, zatim ponovno pokrenite kernel. Time se paket instalira u okruženje aktivnog kernela.
- **Nedostajuća slika:** provjerite naziv datoteke, direktorij `img/` i relativnu putanju. `cv2.imread` za nepostojeću sliku može vratiti `None`.
- **Podaci i modeli:** lekcije s CIFAR-10 i prethodno treniranim modelima mogu zahtijevati internetsku vezu i dodatno preuzimanje pri prvom pokretanju. Pripremite ih prije termina.
- **Dulje treniranje:** za nastavu koristite kratke konfiguracije i pripremljene rezultate duljih eksperimenata. Broj epoha povećavajte u samostalnom radu prema dostupnom vremenu.
- **Tumačenje rezultata:** uz svaku usporedbu zabilježite promijenjeni parametar i njegov učinak. Sam izvršen kod nije dovoljan bez objašnjenja rezultata.

## Izvori

Reference na izvorne radove i atribucije slika nalaze se u pojedinim notebookovima. Zadržite ih pri uporabi i prilagodbi materijala.

- [JupyterLab — instalacija](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html)
- [PyTorch — instalacija prema sustavu](https://pytorch.org/get-started/locally/)
- [OpenCV — Python biblioteka](https://pypi.org/project/opencv-python/)

