# Notebooks für das Buch Machine Learning - kurz &amp; gut

Notebooks für das Buch Machine Learning - kurz &amp; gut: https://oreilly.de/produkt/machine-learning-kurz-gut-2/

Du kannst dieses Repository entweder clonen und die Notebooks bei dir lokal ausführen oder diese mit den folgenden Links direkt auf Google Colab (https://colab.research.google.com/) ausführen:

## Direkte Links auf Colab-Notebooks (aktualisiert auf neuste Versionen und lauffähig auf Colab Mai 2023)
* Kapitel 2 (Quick-Start): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap2.ipynb
* Kapitel 3 (Datenimport und -vorbereitung): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap3.ipynb
* Kapitel 4 (Supervised Learning): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap4.ipynb
* Kapitel 5 (Feature-Auswahl): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap5.ipynb
* Kapitel 6 (Modellvalidierung): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap6.ipynb
* Kapitel 7 (Neuronale Netze und Deep Learning):
  * https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap7-iris.ipynb
  * https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap7-cnn.ipynb
* Kapitel 8 (Unsupervised Learning mit Autoencodern): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap8.ipynb
* Kapitel 9 (Deep Reinforcement Learning): https://colab.research.google.com/github/djcordhose/buch-machine-learning-notebooks/blob/master/kap9.ipynb

## Änderungen zur Auflage 1
* Kapitel 4: Abbruchsbedingungen für SGDRegressor sind in aktuellen Sklearn-Versionen verändert, der Code ist daraufhin angepasst
* Kapitel 7: migriert auf die aktuellste TensorFlow- und Keras-Version
* Kapitel 8: neu in Auflage 2
* Kapitel 9: neu in Auflage 2

## Errata Auflage 2 (bereits korrigiert im ersten Nachdruck)
* Kapitel 6
  * 118: Sensitivity müsste tp / (tp+fn) sein (Dank an Stefan Ollinger)
  * 119 in den Gleichungen: "Mean Squared Error" sollte "Mean Absolute Error" und "Mean Absolute Error" sollte "Median Absolute Error" sein  (Dank an Stefan Ollinger)
* Kapitel 7
  * 138 im Listing unten: Model Parameter "inputs" und "outputs" (Dank an Stefan Ollinger)

## Errata Auflage 2 (bereits korrigiert im zweiten Nachdruck)
* Kapitel 4
  * 77 oben: die Ebenen 4 und 5 werden nicht in der Abbildung 4-29 und 4-30, sondern in 4-30 und 4-31 gezeigt
  * 79 oben: die maximale Anzahl der Ebenen ist hier nicht 5, sondern 2, wie auch richtig im Plot 4-32 dargestellt


## Zusätzliche Erklärungen

### Erklärung zu Abbildung 6-1 und 6-2 (bereits hinzugefügt im ersten Nachdruck)

Precision-Recall- und ROC-Kurven sind gute Indikatoren fuer das Potential deines Modells.
Wie du sicherlich schon erkannt hast muss man immer einen Kompromiss zwischen verschiedenen 
Metriken machen, die man optimieren will.
In unserem Beispiel erkauft man sich eine sehr hohe True-Positive-Rate (tpr) auch mit 
einer relativ hohen False-Positiv-Rate (fpr).

Um die entsprechenden Metriken für deine jeweilige Anwendung zu optimieren, solltest du 
zunaechst den Arbeitspunkt (z.B. welchen gewünschten tpr-fpr-Punkt aus der ROC-Kurve) anhand der Performance-Kurven (6-1 und 6-2) definieren.
Dementsprechend kannst du dann den Schwellenwert für den Ausgabe-Score (y_score) deines Modells anpassen.

Sehr praktische Tools dafuer gibt es in z. B. auch in Sklearn:

```
fpr, tpr, thresholds = sklearn.metrics.roc_curve(y_true, y_scores)
precision, recall, thresholds = sklearn.metrics.precision_recall_curve(y_true, y_scores)
```
