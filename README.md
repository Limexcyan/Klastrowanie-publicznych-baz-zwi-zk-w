# Klastrowanie-publicznych-baz-zwiazkow

Celem projektu jest znalezienie ciekawych zależności w dużych publicznych zbiorach danych

Pozyskane dane pochodzą z publicznej bazy związków ChEMBL dostępnej pod adresem https://www.ebi.ac.uk/chembl/ . Zbiór danych, użyty w projekcie znajduje się w tym repozytorium, pod nazwą CHEMBL244_actives.sdf .

Do modeli wykorzystano wiadomości dostępne w następujących internetowych kursach dotyczących uczenia maszynowego:
1. Google developers: https://developers.google.com/machine-learning/clustering
2. Group of Machine Learning Research, Jagiellonian University: https://github.com/gmum/nn2019

Plik Mockup_clustering.ipynb stanowi kod wykorzystany w prezentacji śródsemestralnej, finalną wersję kodu dla projektu stanowi plik Clustering Project.ipynb.

W projekcie wykorzystanow różne narzędzia do klastrowania danych, głównie eksperymentowano z algorytmem k-means. W związku w bardzo dużą liczbą wymiarów, w których są dane, zastosowano również metodę PCA (principal component analysis) w celu wizualizacji rozmieszczenia związków. Związki zakodowano w postaci fingerprintów Morgana.

Celem projektu było przetestowanie następujących hipotez badawczych:
1. Istnieją metody do znajdywania  wspólych podstruktur dla  bazy daych targetu.
2. Grupy korelują ze źródłem danych, a wewnątrz klastrów można dostrzec wyraźne elementy wspólne dla wszystkich związków.
3. Można znajdywać cechy wspólne dla różnych targetów.

Technicznie należało również przetestować różne metody klastrowania, zastosować inne fingerprinty i sprawdzić efekt ich implementacji w stosunku do pierwotnie użytych narzędzi. Wyzwaniem było również znalezienie odpowiedniej liczby klastrów.

Kod zawiera szereg funkcji skalujących dane, które są używane w zależności od rozkładu danych. Można łatwo dopasować scaler do rozkładu poprzez wizualizację chociażby jego histogramu. Dalej znajduje się featurizer mający za zadanie czytać dane, które są w postaci SMILES. ClusteringFeaturizer został dostosowany do wspomnianych powyżej różnych rozkładów danych.

Na podstawie histogramu aktywności albo std_value stwierdzamy, że rozkład wartości dla związków nie jest równomierny.

Aby ustalić optymalną liczbę klastrów stosuje się metody porównujące wyniki klastrowania dla różnej maksymalnej liczby klastrów. Ma miejsce również wizualizacja analizy liczności klastrów, wykresy w zależności od wyniku oraz od całkowitego dystansu.

W celu wizualizacji klastrów zastosowano analizę głównych składowych i przedstawiono wyniki na wykresie trójwymiarowym (z czwartym wymiarem w postaci kolorów - oznaczeń dla rozróżnienia klastrów).
