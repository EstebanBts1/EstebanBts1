
# GameShell : un “jeu” pour apprendre le shell Unix

<p><img src="https://github.com/phyver/GameShell/raw/master/Images/illustration-small.png" alt="Illustration inspired by the game"></p>
<p>Enseigner l’utilisation d’un shell Unix à des étudiants de première année à<br>
l’université ou à des lycéens n’est pas toujours simple, ni très amusant.<br>
GameShell a été conçu comme un outil pour aider les étudiants de <a href="https://univ-smb.fr">l’Université<br>
Savoie Mont Blanc</a> à découvrir un <em>vrai</em> shell, avec une<br>
approche qui favorise l’apprentissage tout en s’amusant.</p>
<p>L’idée initiale, due à Rodolphe Lepigre, était de lancer une session bash avec<br>
un fichier de configuration qui définissait des “missions”, qui seraient<br>
“validées” pour avancer dans le jeu.</p>
<p>Voilà le résultat…</p>
<p><img src="https://github.com/phyver/GameShell/raw/master/Images/gameshell_first_mission_small.gif" alt="GameShell's first mission"></p>
<p>N’hésitez pas à nous envoyer vos remarques, questions ou suggestions en<br>
ouvrant des <a href="https://github.com/phyver/GameShell/issues">“issues”</a> ou en<br>
soumettant des <a href="https://github.com/phyver/GameShell/pulls">“pull requests”</a>.<br>
Nous sommes particulièrement intéressés pas toute nouvelle mission que vous<br>
pourriez créer !</p>
<h2 id="comment-jouer-">Comment jouer ?</h2>
<p>GameShell devrait fonctionner sur n’importe quel système Linux standard, et<br>
aussi sur macOS et BSD (mais ces systèmes ont été moins testés). Sur Debian ou<br>
Ubuntu, les seules dépendances (autres que <code>bash</code>) sont les paquets <code>awk</code> et<br>
<code>gettext-base</code> (le premier étant généralement installé par défaut). Certaines<br>
missions ont des dépendances additionnelles : elles seront annulées si leurs<br>
dépendances ne sont pas satisfaites. Sur Debian ou Ubuntu, lancez la commande<br>
suivante pour installer toutes les dépendances pour le jeu et les missions.</p>
<pre class=" language-sh"><code class="prism  language-sh">$ sudo apt install gettext-base man-db psmisc nano tree bsdmainutils x11-apps
</code></pre>
<p>Consultez le <a href="https://github.com/phyver/GameShell/blob/master/doc/user_manual.md">manuel utilisateur</a> (en anglais) pour voir<br>
comment installer les dépendances sur d’autres systèmes (macOS, BSD, …).</p>
<p>En supposant que toutes les dépendances sont installées, vous pouvez essayer<br>
la dernière version du jeu en lançant les deux commandes suivantes dans un<br>
terminal.</p>
<pre class=" language-sh"><code class="prism  language-sh">$ wget https://github.com/phyver/GameShell/releases/download/latest/gameshell.sh
$ bash gameshell.sh
</code></pre>
<p>La première commande téléchargera la dernière version du jeu sous la forme<br>
d’une archive auto-extractible, et la seconde commande initialisera et lancera<br>
le jeu à partir de cette archive. Les instructions pour jouer sont données<br>
directement dans le jeu.</p>
<p>Quand vous quitterez le jeu (avec <code>control-d</code> ou la commande <code>gsh exit</code>) votre<br>
progression sera sauvegardée dans une nouvelle archive (nommée<br>
<code>gameshell-save.sh</code>). Elle peut être lancée pour reprendre le jeu où vous vous<br>
étiez arrêté.</p>
<p>Si vous préférez ne pas exécuter des scripts étrangers sur votre machine,<br>
vous pouvez générer une image Docker avec :</p>
<pre class=" language-sh"><code class="prism  language-sh">$ mkdir GameShell; cd GameShell
$ wget --quiet https://github.com/phyver/GameShell/releases/download/latest/Dockerfile
$ docker build -t gsh .
$ docker run -it gsh
</code></pre>
<p>Votre progression ne sera PAS sauvée lorsque vous quittez le jeu, et des<br>
options supplémentaires sont nécessaires si vous souhaitez lancer des<br>
programmes X depuis GameShell. Référez vous à <a href="./doc/deps.md#running-GameShell-from-a-docker-container">cette<br>
section</a> du manuel<br>
d’utilisateur.</p>
<h2 id="documentation">Documentation</h2>
<p>Pour en savoir plus sur GameShell les documents suivants sont disponibles (en<br>
langue anglaise uniquement):</p>
<ol>
<li>Le <a href="https://github.com/phyver/GameShell/blob/master/doc/user_manual.md">manuel utilisateur</a> explique, entre autres, comment<br>
lancer le jeu sur toutes les plateformes supportées (Linux, macOS, BSD),<br>
comment lancer le jeu à partir des sources, et comment générer une archive<br>
de jeu personnalisée (ce qui est utile pour utiliser le jeu dans le cadre<br>
d’un cours).</li>
<li>Le <a href="https://github.com/phyver/GameShell/blob/master/doc/dev_manual.md">manuel développeur</a> explique, entre autres, comment<br>
créer une nouvelle mission, comment traduire le jeu et les missions, et<br>
comment participer au développement du jeu.</li>
</ol>
<h2 id="qui-développe-gameshell">Qui développe GameShell?</h2>
<h3 id="développeurs">Développeurs</h3>
<p>Le jeu est développé par:</p>
<ul>
<li><a href="http://www.lama.univ-smb.fr/~hyvernat">Pierre Hyvernat</a> (développeur<br>
principal, <a href="mailto:pierre.hyvernat@univ-smb.fr">pierre.hyvernat@univ-smb.fr</a>),</li>
<li><a href="https://lepigre.fr">Rodolphe Lepigre</a>.</li>
</ul>
<h3 id="contributeurs-missions">Contributeurs missions</h3>
<ul>
<li>Pierre Hyvernat</li>
<li>Rodolphe Lepigre</li>
<li>Christophe Raffalli</li>
<li>Xavier Provencal</li>
<li>Clovis Eberhart</li>
<li>Sébastien Tavenas</li>
<li>Tiemen Duvillard</li>
</ul>
<h3 id="remerciements">Remerciements</h3>
<ul>
<li>Tous les étudiants qui ont testé les toutes premières versions du jeu.</li>
<li>Joan Stark (alias jgs) qui a créé des centaines d’ASCII-art à la fin des<br>
années 90. La majorité des ASCII-art que vous rencontrerez dans GameShell<br>
lui sont dus.</li>
</ul>
<hr>
<h2 id="test">Test</h2>
<p>Avez-vous lu tous le document ?</p>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" checked="true" disabled=""> Oui</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> Non</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> <s>peut-être</s></li>
</ul>
<p>Alors n’oubliez pas de lire la <mark>note</mark> de bas de page<sup class="footnote-ref"><a href="#fn1" id="fnref1">1</a></sup></p>
<p>Et attention buvez beaucoup d’H<sub>2</sub>O et n’oubliez pas le <code>1000</code> est égale à 8 soit 2<sup>3</sup>.</p>
<h2 id="licence">Licence</h2>
<p>GameShell est distribué sous la licence <a href="https://www.gnu.org/licenses/gpl-3.0.en.html">GPLv3</a>.</p>
<p>Merci de pointer vers ce dépôt si vous l’utilisez.</p>
<p>GameShell est open source et son utilisation est gratuite. Une manière de<br>
reconnaitre le travail que cela à nécessité est d’envoyer un carte postale à</p>
<pre><code>  Pierre Hyvernat
  Laboratoire de Mathématiques, CNRS UMR 5127
  Université de Savoie
  73376 Le Bourget du Lac
  FRANCE
</code></pre>
<hr>
<hr class="footnotes-sep">
<section class="footnotes">
<ol class="footnotes-list">
<li id="fn1" class="footnote-item"><p>c’est bien <a href="#fnref1" class="footnote-backref">↩︎</a></p>
</li>
</ol>
</section>
</div>
</body>

</html>
