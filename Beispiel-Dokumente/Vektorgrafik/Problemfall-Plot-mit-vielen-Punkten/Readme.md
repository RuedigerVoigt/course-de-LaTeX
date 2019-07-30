# Problemfall Scatterplot mit sehr vielen Punkten


In diesem Ordner finden Sie zwei Dateien *mit dem gleichen Inhalt*: ein Plot von mehr als 200,000 Punkten, die sich gegenseitig überlagern.


* Als PDF (Vektorgrafik) ist die Datei etwa 12 MB groß und bringt zuverlässig auch gute Drucker zum Absturz.
* Als PNG (Rastergrafik) sind die Overlays rausgerechnet und die Datei ist nur etwa 200 Kb groß. Der Qualitätsverlust ist praktisch nicht wahrzunehmen.


Wenn Sie also (zum Beispiel) mit R / ggplot2 Scatterplots mit sehr vielen Punkten generieren, dann können Sie das Problem umgehen indem Sie als Exportformat PNG oder ein anderes Rasterformat in guter Qaulität nutzen. Alternativ sollten Sie überlegen, ob andere Diagramm-Typen (Heatmap, Boxplot, ...) die Daten besser darstellen.
