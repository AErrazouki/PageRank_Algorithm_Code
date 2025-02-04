<h1>Système d’évaluation PageRank avec Interface Graphique</h1>

<h2>📌 Description du Projet</h2>
<p>Ce projet implémente l'algorithme <strong>PageRank</strong> pour analyser et classer des nœuds dans un graphe en fonction de leur importance.
   L’application utilise <code>Tkinter</code> pour fournir une interface graphique interactive permettant de charger, visualiser et analyser un graphe en temps réel.
   L’objectif est de permettre aux utilisateurs d’explorer le fonctionnement de PageRank sur différents types de graphes.</p>

<h2>⚙️ Architecture et Fonctionnalités</h2>

<h3>1️⃣ Implémentation de l’algorithme PageRank</h3>
<ul>
    <li>Utilisation d’une <strong>matrice de transition P</strong> pour capturer les probabilités de passage d’un nœud à un autre.</li>
    <li>Calcul du score PageRank de manière itérative jusqu’à convergence.</li>
    <li>Prise en charge du paramètre <strong>α (facteur de téléportation)</strong> pour éviter les nœuds isolés.</li>
</ul>

<h3>2️⃣ Conversion et Manipulation des Graphes</h3>
<ul>
    <li>Transformation d’un graphe sous forme de <strong>dictionnaire</strong> en <strong>matrice d’adjacence</strong>.</li>
    <li>Compatibilité avec différents formats d’entrée pour une meilleure flexibilité.</li>
</ul>

<h3>3️⃣ Interface Graphique Interactive</h3>
<ul>
    <li>📂 <strong>Chargement et visualisation</strong> de graphes sous différents formats.</li>
    <li>📊 <strong>Affichage dynamique</strong> du graphe avec <code>matplotlib</code>.</li>
    <li>🖥️ <strong>Exécution et affichage des résultats</strong> du PageRank en temps réel.</li>
    <li>🎛️ <strong>Gestion des interactions utilisateur</strong> via <code>tkinter</code>.</li>
</ul>

<h2>🔧 Détails Techniques</h2>
<ul>
    <li><strong>Langage :</strong> Python</li>
    <li><strong>Bibliothèques utilisées :</strong>
        <ul>
            <li><code>numpy</code> pour les calculs matriciels</li>
            <li><code>networkx</code> pour la gestion des graphes</li>
            <li><code>matplotlib</code> pour la visualisation</li>
            <li><code>tkinter</code> pour l’interface utilisateur</li>
            <li><code>pyperclip</code> pour la gestion du presse-papiers</li>
        </ul>
    </li>
</ul>

<h2>🔍 Méthodes d’Implémentation</h2>

<h3>📌 Méthode 1 : PageRank à partir d'une Matrice d'Adjacence</h3>
<p>Dans cette méthode, le graphe est représenté sous forme de <strong>matrice d'adjacence</strong>, où chaque ligne indique les liens sortants d'un nœud.</p>
<pre>
import numpy as np

# Définition de la matrice d'adjacence
adj_matrix = np.array([
    [0, 0, 0],  # Nœud A
    [0, 0, 1],  # Nœud B → C
    [1, 1, 0],  # Nœud C → A, B
])

# Calcul du PageRank
PageRank_Matrix(adj_matrix)
</pre>

<h3>📌 Méthode 2 : PageRank à partir d'un Graphe</h3>
<p>Ici, le graphe est défini directement en listant les arêtes sous forme de paires de nœuds.</p>
<pre>
import networkx as nx

# Définition des arêtes du graphe
edges = [('A', 'B'), ('B', 'C'), ('C', 'A')]

# Création du graphe dirigé
G = nx.DiGraph()
G.add_edges_from(edges)

# Exécution de l'algorithme PageRank
page_rank_score(G)
</pre>

<h3>📌 Méthode 3 : PageRank à partir d’un Fichier XML</h3>
<p>Cette méthode permet d’analyser un graphe stocké dans un fichier XML contenant les nœuds et les arêtes.</p>
<pre>
import xml.etree.ElementTree as ET

# Exemple d'utilisation avec un fichier XML
xml_file = 'edges.xml'
page_rank_score_from_xml(xml_file)
</pre>

<h4>📂 Exemple de structure XML :</h4>
<pre>
&lt;graph&gt;
  &lt;node id="A"&gt;
    &lt;edge target="B" /&gt;
  &lt;/node&gt;
  &lt;node id="B"&gt;
    &lt;edge target="C" /&gt;
  &lt;/node&gt;
&lt;/graph&gt;
</pre>

<h3>📌 Méthode 4 : Utilisation de la Fonction PageRank intégrée à NetworkX</h3>
<p>La bibliothèque <code>networkx</code> fournit une fonction intégrée pour calculer le PageRank d’un graphe.</p>
<pre>
import networkx as nx

def calculer_pagerank(edges):
    G = nx.DiGraph(edges)
    pagerank = nx.pagerank(G, tol=1e-6, alpha=0.85)
    for node, rank in pagerank.items():
        print(f"PageRank du nœud {node}: {rank:.6f}")

# Appeler la fonction avec les arêtes données
calculer_pagerank([('A', 'B'), ('B', 'C'), ('C', 'A')])
</pre>

<h2>🚀 Contribuer</h2>
<p>Les contributions sont les bienvenues ! Veuillez suivre ces étapes :</p>

<ol>
    <li>🔄 <strong>Forkez</strong> le dépôt en cliquant sur le bouton "Fork" sur GitHub.</li>
    <li>🌿 <strong>Créez une nouvelle branche</strong> pour vos modifications :
        <pre>
git checkout -b feature-branch
        </pre>
    </li>
    <li>✍️ <strong>Commitez vos modifications</strong> avec un message clair :
        <pre>
git add .
git commit -m "Ajout d'une nouvelle approche"
        </pre>
    </li>
    <li>📤 <strong>Poussez la branche</strong> vers le fork sur GitHub :
        <pre>
git push origin feature-branch
        </pre>
    </li>
    <li>📩 <strong>Créez une Pull Request</strong> en allant sur le dépôt original et en sélectionnant le branche.</li>
</ol>
