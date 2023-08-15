# Variabilité lexicale et thématique dans des poèmes générés par ChatGPT: Analyse sur différents niveau de prompting

## Résumé 

## Introduction 

La question de la créativité, ou de la génération de contenu créatif, de la part des _Large Language Models_ (LLM) est sans conteste l’une des plus complexe, tant à appréhender conceptuellement, qu’à évaluer pratiquement. En effet, la question « un modèle de langage génératif peut-il être créatif ? », posée comme telle, est trop ambiguë. Le statut, ou la nature, de la créativité devraient être définis au préalable pour permettre tout élaboration d’une réponse satisfaisante. En premier lieu, la créativité peut s’entendre au sens formel ; est-il possible pour une machine de créer une nouvelle phrase, jamais énoncée ? À cette question, la réponse est de toute évidence « oui » ; les LLM, entrainés sur une large base de données textuelles, sont capables de produire des nouvelles phrases. Toutefois, la créativité s’entend également au niveau sémantique. C’est d’ailleurs en ce second sens qu’on la conçoit généralement. La créativité est « faculté d’invention ». L’interrogation apparait d’elle-même : ces modèles de langage, entrainés sur des données _existantes_, sont-ils capables de produire du contenu nouveau, innovant ? Ne sont-ils pas voués à ne sortir qu’un ramassis du passé, que des « variations sur le même thème » ? À cela, on rétorque alors aisément que rien ne nous prouve que cela n’est pas notre cas aussi, et que toute chose nouvelle que nous, humains, produisons n’est peut-être, elle aussi, qu’un ramassis de nos expériences passées. 

Ainsi, face à cette impasse argumentative, nous nous proposons de laisser de côté cette question au profit d’une autre : « Qu’obtient-on lorsque l’on demande à des LLM de générer des textes créatifs ? ». De cette manière, nous sortons d’une dichotomie de type test de Turing. Nous nous proposons en effet de remplacer la question fermée « est-ce que oui ou non les LLM peuvent produire des textes créatifs ? » par une **analyse empirique et exploratoire** des textes générés, qui nous parait plus pertinente, et surtout plus à même de livrer des résultats dignes d’intérêt.

### Hypothèses 

Nous faisons l’hypothèse que si ces modèles sont capables de générer des textes crédibles, qui « auraient pu être écrits par des humains », ou qui en sont pour le moins difficilement différentiable, ceux-ci – parce qu’ils sont entrainés à imiter des régularités – font montre d’une diversité lexicale et thématique plus faibles que des textes écrits par des humains. 

La diversité lexicale et thématique étant des mesures quantifiables, nous allons les utiliser comme des indices de mesure de la qualité créative des textes. Toutefois, nous n’avons pas la prétention d’affirmer que ces indices constituent une mesure de phénomène créatif en tant que tel, mais simplement qu’ils peuvent en constituer un _ersatz_, en donnant certains indicateurs permettant ensuite pour ainsi dire, d’ouvrir la discussion sur le sujet. 

En outre, nous nous cantonnerons pour notre étude à l’analyse de poèmes générés par ChatGPT ; un choix méthodologique qu’il s’agit pour nous de justifier.

En effet, nous faisons le parti pris de considérer des poèmes comme porte-paroles de l’écriture créative, et ce pour plusieurs raisons. En premier lieu, et il s’agit d’une raison triviale, la poésie nous apparait comme l’exemple paradigmatique de l’écriture créative, en ce qu’elle constitue la forme littéraire « artistique » par excellence, dévouée purement à l’évocation et à l’expression de la langue. Une deuxième raison, bien plus pragmatique cette fois-ci, est la longueur relativement restreinte des textes concernés. Celle-ci les rend, d’une part, plus appréhendables, plus rapides à analyser en termes de traitement des données, et d’autre part d’une longueur comparable, ce qui facilite grandement l’analyse quantitative et qualitative que l’on peut en faire. En outre, la poésie en tant qu’elle est écriture créative est jeu avec le langage, mais aussi jeu _avec les règles_ du langage. La poésie est un lieu d’expérimentation et d’innovation verbale. Et c’est justement cette expérimentation, ce « sortir des sentiers battus » que l’on peine à penser pouvoir trouver dans un algorithme, entrainé au contraire à repérer des _régularités_.

De plus, il nous faut également mentionner l’importante restriction de notre recherche de ne traiter que de poèmes générés par la version gratuite, soit 3.5, de ChatGPT. Nous reconnaissons qu’une telle limitation pourrait introduire de potentiels biais dans les résultats de notre recherche. En effet, en se basant exclusivement sur les sorties de ChatGPT 3.5, il est possible que nous reflétions les tendances, les styles et les schémas de génération spécifiques à ce modèle particulier, dont certaines pourraient être évitées ou modifiées par des modèles qui pourraient être soit plus performants – en considérant par exemple d’éventuelles améliorations ou changements dans les versions ultérieures – soit entrainés spécifiquement à la création de poésie. Ainsi, la qualité d’un poème généré par ChatGPT 3.5, n’est pas un gage de la qualité de tous les poèmes qu’il serait possible de générer avec des LLM. Toutefois, nous estimons que l’exploration de ce modèle peut nous fournir des outils et des pistes de réflexions pertinente sur le fonctionnement général des LLM ainsi que leur application dans le contexte poétique.

### Objectif de la recherche

Dès lors, l’objectif de notre recherche est d’une part, d’observer si les poèmes générés par ChatGPT 3.5 font montre d’une diversité lexicale et thématique inférieure à des poèmes humains, et d’autre part, d’analyser qualitativement ces poèmes dans le but d’explorer les mécanismes de « création » de ChatGPT. Pour ce faire, nous souhaitons comparer des poèmes générés par le modèle de langage avec des poèmes humains issus de la littérature canonique et tester les limites de ChatGPT 3.5, en comparant également les performances du modèle pour différents types de prompting.

## Données

Notre dataset est constitué de 200 poèmes, divisés en 4 groupes de 50. 1 groupe de poèmes humains, et 3 groupes de poèmes générés par ChatGPT.

En premier lieu, avons sélectionné **50 poèmes de la littérature "canonique"**. Les poèmes ont été écrits par les auteurs suivants: André Breton, Arthur Rimbaud, Alphonse de Lamartine, Alfred de Vigny, Charles Baudelaire, Guillaume Apollinaire, Gérard de Nerval, Jean Racine, Pierre Corneille, Pierre de Ronsard, Paul Verlaine, Stéphane Mallarmé, Tristan Tzara, Victor Hugo. 

Puis, nous avons généré des poèmes avec ChatGPT [préciser version]. Nous avons testé 3 différents niveaux de prompting (pour plus sur le prompt engineering, voir par exemple https://github.com/dair-ai/Prompt-Engineering-Guide/blob/main/guides/prompts-chatgpt.md). 

Pour le **premier niveau de prompting**, nous avons donné des indications minimales. Pour chaque poème de notre dataset de "poèmes humains", nous avons généré un poème en indicant le type de poème (sonnet, poème en écriture automatique, etc.) et le style de l'auteur.
- <span style="color🍊">Ex : Écris un sonnet dans le style d'Arthur Rimbaud</span>

Pour le **deuxième niveau de prompting**, nous avons donné un example à imiter. Nous avons pris chaque poème de notre dataset de "poèmes humains" et demandé à ChatGPT de générer un poème ressemblant à celui-ci. 

- <span style="color🍊;white-space:pre-line">Ex : Écris un poème qui ressemble à celui-ci : 
    Napoléon mourant vit une Tête armée… 
    Il pensait à son fils déjà faible et souffrant :
    La Tête, c’était donc sa France bien-aimée,
    Décapitée aux pieds du César expirant.</span>

    <span style="color🍊;white-space:pre-line">Dieu, qui jugeait cet homme et cette renommée,
    Appela Jésus-Christ ; mais l’abîme s’ouvrant,
    Ne rendit qu’un vain souffle, un spectre de fumée :
    Le Demi-Dieu, vaincu, se releva plus grand.</span>
    
    <span style="color🍊;white-space:pre-line">Alors on vit sortir du fond du purgatoire
    Un jeune homme inondé des pleurs de la Victoire,
    Qui tendit sa main pure au monarque des cieux ;</span>

    <span style="color🍊;white-space:pre-line">Frappés au flanc tous deux par un double mystère,
    L’un répandait son sang pour féconder la Terre,
    L’autre versait au ciel la semence des dieux !</span>
 
 
 
 Pour le **troisième niveau de prompting**, nous avons donné des indications pour "reproduire" le poème. Nous avons indiqué le début du poème, la forme, les thèmes, les champs lexicaux, et le style général. 
- <span style="color🍊">Ex: 12.	Voici des instructions pour écrire un poème : 
    - Commence par « Esprit parisien ! démon du Bas-Empire !
      Vieux sophiste épuisé qui boit, toutes les nuits, »
    - Respecte la forme sonnet (deux quatrains et deux tersets)
    - Ecris un poème qui parle de l’Esprit parisien en le personnifiant. Prends un ton cynique et ironique pour faire une critique sociale
    - Met en lumière l’hypocrisie, la cruauté et la superficialité de l’Esprit parisien </span>

## Méthodes 


#### Preprocessing

Pour mener à bien notre analyse, nous avons suivi un processus de prétraitement des données afin de garantir leur cohérence et leur comparabilité. Voici les étapes que nous avons suivies :
- Importation des Poèmes dans une DataFrame pandas : Nous avons rassemblé un ensemble de 200 poèmes humains et leurs équivalents générés par ChatGPT, selon les 3 niveaux de prompting mentionnés précédemment. Pour faciliter la correspondance ultérieure, nous avons conservé le nom de chaque fichier associé à son contenu. 
- Séquençage du Texte : Nous avons commencé par éliminer les marqueurs de saut de ligne ('\n') pour assurer une représentation continue du texte. Ensuite, nous avons utilisé la bibliothèque NLTK pour effectuer la tokenisation des poèmes, tout en supprimant les mots vides (stopwords) en utilisant la liste des stopwords français fournie par NLTK. 

#### Variabilité lexicale : fréquence des mots
L'analyse de la variabilité lexicale a été réalisée en utilisant la librairie LexicalRichness, dont la documentation est disponible à l'adresse suivante : https://github.com/LSYS/LexicalRichness/blob/master/README.rst. Les étapes que nous avons suivies sont les suivantes :
- Calcul des métriques lexicales : Nous avons calculé plusieurs métriques, notamment le nombre total de mots, le nombre de mots uniques (termes), et le ratio mots/termes, en utilisant à la fois notre propre tokenisation et celle proposée par LexicalRichness.
- Distribution des mots : Nous avons examiné la distribution des mots en fonction de leur fréquence pour chaque niveau de prompt (humain et ChatGPT).
- Mots les plus fréquents : Nous avons extrait les mots les plus fréquents pour chaque niveau de prompt, ce qui nous a permis d'obtenir un aperçu des termes prédominants dans chaque groupe. 
- Indices de richesse lexicale : Nous avons calculé plusieurs indices de richesse lexicale, notamment le "Measure of Textual Lexical Diversity" (MTLD), la mesure "Hypergeometric distribution diversity" (HD-D), ainsi que la mesure de diversité lexicale de Maas. 
- Analyse comparative : Pour évaluer la richesse lexicale des poèmes générés par ChatGPT par rapport aux poèmes humains, nous avons mesuré la déviation de ces indices par rapport au groupe de contrôle (poèmes humains). 

#### Variabilité thématique : Topic Modelling
Pour analyser la variabilité thématique des poèmes, nous avons adopté une approche de "Topic Modelling" en utilisant le modèle Latent Dirichlet Allocation (LDA). Voici les étapes que nous avons suivies :
- Préparation des données pour le LDA : Nous avons regroupé l'ensemble des poèmes de chaque groupe (humain et ChatGPT) en un seul texte afin de former un corpus distinct pour chaque groupe.
- Application du modèle LDA : Nous avons utilisé la bibliothèque Gensim pour exécuter le modèle LDA. Pour simplifier notre analyse, nous avons fixé le nombre de thèmes (topics) à retourner à 10. Nous avons comparé les thèmes obtenus dans l'espoir d'identifier la diversité ou la redondance des thèmes, ce qui pourrait servir d'indicateur de la diversité thématique des poèmes.
  
#### Analyse qualitative
En complément de nos analyses quantitatives, nous avons également mené une analyse qualitative approfondie des poèmes générés par ChatGPT et des poèmes humains. Cette analyse nous a permis de capturer des éléments tels que le style, l'émotion, les métaphores et les thèmes sous-jacents présents dans les poèmes. Cette approche qualitative nous a fourni un aperçu holistique et nuancé de la nature des textes produits par les deux groupes.

# Résultats 

## 1. Variabilité lexicale 

## 2. Analyse qualitative : exemple de poèmes 

Pour nous faire une meilleure idée de la manière dont ChatGPT 3.5 génère des poèmes, nous allons présenter quelques exemples, à savoir, les trois poèmes générés à partir du sonnet d’Arthur Rimbaud, Le Dormeur du val, ainsi que les trois poèmes générés à partir du poème de Victor Hugo, Demain, dès l’aube… . Les poèmes originaux ainsi que leurs dérivations produites à partir des trois différents niveaux de prompt sont visibles sur les figures X et Y. Nous souhaitons ainsi i) comparer les résultats des trois niveaux de prompt, ii) établir les caractéristiques d’écriture de ChatGPT 3.5, ainsi que les différences dans le style des poèmes en fonction de leur niveau de prompt, et iii) déterminer si les scores qu’obtiennent ces poèmes pour les différents indices de diversité lexicale correspondent à notre intuition 


### Comparaison des niveaux de prompt 

#### Le Dormeur du val 
#### Niveau 1  
Le poème de niveau 1 a été généré à partir du prompt : « Écris un sonnet dans le style d’Arthur Rimbaud ». Première constatation, le poème généré ne respecte pas la forme sonnet, mais est constitué de quatre quatrains, avec des rimes alternées, dont plusieurs sont ratées (froissent, flamboie ; insatiable, impossible ; oubliés, défis). Le premier quatrain contient quatre alexandrins, mais cette rigueur rythmique est abandonnée dans la suite du poème. 

Celui-ci est rédigé à la première personne, et le narrateur masculin – qui semble être une imitation du personnage d’Arthur Rimbaud – se présente comme une figure héroïque, presque mégalomane (« je suis prêt à braver l’impossible », « je suis le maître de mon temps », « rien ne peut arrêter l’élan de mon destin »). 

D’une manière générale, le poème est assez faible. Le mot « destin » apparait trois fois, et de nombreux groupes nominaux sont des associations de mots très génériques (« contrées lointaines », « soif insatiable », « passion dévorante », « feu ardent », « victoire triomphante »). Outre les figures de style très pauvres, le propos du poème est lui aussi très peu spécifique (« Je suis prêt à braver l’impossible, Pour conquérir mon destin », etc.). 

Le poème contient également des incohérences sémantiques (« Et je sais que je trouverai sur ma route, tous les défis, Car rien ne peut arrêter … »). Le premier vers « Ô saison, ô châteaux, ô rêves enchantés » est repris en anaphore à la dernière strophe et devient « Ô saison, ô châteaux, ô rêves oubliés ». Ces éléments ne semblent n’avoir rien à voir avec le propos du poème. Il est possible que le terme « saison » soit utilisé en raison du titre de l’œuvre Une Saison en enfer d’Arthur Rimbaud, mais dans le contexte, cela est incohérent. 

#### Niveau 2  
Le poème de niveau 2 a été généré à partir du prompt : « Écris un poème qui ressemble à celui-ci : » suivi des quatorze vers du poème Le Dormeur du val. Le poème respecte la forme sonnet, et si la longueur des vers s’approche de la longueur d’alexandrins, elle ne suit pas une rythmique stricte. Les vers ne riment pas. En fait, il apparait que le poème a été généré en performant pour ainsi dire une reformulation du poème original. En effet, les vers ont une forme grammaticale très similaire, mais les noms et adjectifs ont été remplacé par d’autres, issus d’un champ lexical assez similaire. Ainsi « C’est un trou de verdure où chante une rivière, », devient « C’est un coin de ciel bleu où s’égaye une abeille, » ; « où le soleil, de la montagne » devient « où le vent, de la mer » ; « Un soldat jeune » devient « Une enfant joyeuse » ; Ses pieds dans les glaïeuls, il dort, » devient « Ses pieds dans les pâquerettes, elle dort. » ; et le fameux vers final : « Tranquille. Il a deux trous rouges au côté droit. » devient « Apaisée. Elle a deux tresses brunes sur les épaules. ».

Dès lors, le poème a perdu toute cohérence sémantique. On est tour à tour dans le ciel (« C’est un coin de ciel bleu »), vers la mer (« le vent, de la mer »), dans l’herbe (« sa tête blonde sur l’herbe fraîche »), et à l’intérieur (« la main sur son oreiller »). En outre, on retrouve les associations de terme génériques (« herbe fraîche », « doux murmure », « plumes légères », « aventures merveilleuses »). Toutefois, la structure grammaticale du poème original étant largement conservée, celle-ci est plus complexe que pour le poème de niveau 1, contenant notamment des propositions participiales (« Butinant avec ardeur », « Posant sa tête blonde »), des comparaisons (« comme des plumes légères », « Comme un chaton bercé ») et un rejet (« Apaisée. » au vers 14, qui complète le vers 13). 

#### Niveau 3  
Le poème de niveau 2 a été généré à partir du prompt : « Voici des instructions pour écrire un poème : - Commence par « C’est un trou de verdure ou chante une rivière ». - Respecte la forme sonnet. - Décrit un personnage couché dans une nature paisible. - Laisse suggérer que le personnage est mort ». Comme pour le poème de niveau 1, l’output ne respecte pas la forme sonnet, mais est formé de cinq quatrains, avec des rimes embrassées (avec un seul manquement, au vers 8). À nouveau, les vers s’approchent de la longueur d’alexandrins, sans être rythmiquement rigoureux (souvent entre onze et treize syllabes). 

Ici, comme pour les deux poèmes précédents, l’on retrouve le même type d’expressions banales et génériques (« douce nourriture », « fleurs délicates », « le vent murmure », « silence éternel »). Le poème contient également de nombreuses répétitions : le mot « nature », et l’adjectif « éternel(le) » apparaissent trois fois, les mots « silence », « mort » et l’adjectifs « délicat(e) » deux fois, et l’on trouve quatre mots de la même famille que « paix » (« s’apaise », « paix », « apaisement », « paisible »). 

Il a été demandé en prompt de décrire un personnage. Cette requête semble avoir été prise dans un sens trop littéral, comme en témoignent les vers 5 et 13 (« Là, étendu, un personnage repose en paix », « Elle enveloppe le personnage »). De plus, le début de la dernière strophe semble être une explicitation du poème entier (« Dans se sonnet funèbre, la mort laisse sa trace, Mais la beauté de la nature reste éternelle »), réalisant ainsi une mise en abyme assez malvenue. Le poème contient également des incohérences ; il est fait mention de la respiration du personnage (« sa respiration en cadence »), alors que celui-ci est mort. En outre, l’expression « une mélodie empreinte de combes » est nonsensique.

Toutefois, le poème contient quelques éléments intéressants. Au vers 4, il est fait mention de la guerre, alors que cela n’était pas spécifié en prompt. De plus, la comparaison au vers 9 : « Son visage paisible, tel un marbre délicat », est très pertinente pour décrire un mort.


#### Demain, dès l’aube… 

Pour les poèmes générés à partir de Demain, dès l’aube… de Victor Hugo, des considérations analogues à celles faites pour le Dormeur du val s’appliquent, nous serons dès lors plus bref dans notre analyse. Le poème de niveau 1 est tout à fait plat, ne contenant que des images banales, un champ lexical pauvre et une structure grammaticale peu complexe. Il y est à nouveau question de la beauté de la nature, des phénomènes atmosphériques et océaniques (« nuages », « vagues », « vent »). Les mots « vie », « souffle », et « instant » sont répétés deux fois. Le texte contient en outre une répétition incohérente : « las et las », au vers 2. La dernière strophe du poème (« Et je me rappelle […] Que la vie est un souffle […] Et qu’il nous appartient […] De cueillir la beauté […] ») se présente comme une sorte de conclusion, explicitant la « morale » du poème, ce qui semble également être une caractéristique récurrente des poèmes générés par ChatGPT.

Le poème de niveau 2 est à nouveau une reformulation du poème original, mais cette fois-ci, le sens original du poème semble plus étroitement conservé, et c’est plus l’ordre des mots qui a été modifié. En témoigne les deux premiers vers : « Demain dès l’aube, à l’heure où blanchit la campagne, Je partirai. Vois-tu, je sais que tu m’attends. » devient « Dès l’aube demain, je partirai, je te l’ai promis, Car je sais que tu m’attends, là-bas, dans l’infini. » ; « J’irai par la forêt, j’irai par la montagne » devient « Je traverserai la ville, je traverserai les champs » ; « Seul, inconnu, le dos courbé, les mains croisées » devient « Marchant seul, inconnu, le cœur lourd et les mains vides ». Toutefois, quelque chose de remarquable se passe à la fin du poème.  Les deux vers finaux de l’original (« Et quand j’arriverai, je mettrai sur ta tombe Un bouquet de houx vert et de bruyère en fleur »), sont transformés de la même manière que les exemples précédents (« Quand j’arriverai enfin, j’irai te rendre hommage, Avec un bouquet de houx vers et de bruyère en fleur ») toutefois le vers est complété par l’ajout de l’expression « comme un message », qui ne fait écho à aucune expression présente dans le poème original. Cette expression semble au contraire amorcer une sorte d’explicitation du sens du poème, confirmée par l’ajout d’une strophe supplémentaire (« Je suis venu te dire que je t’aime encore […] Que même si tu n’es plus là, tu vis en moi à jamais […] ») qui se présente comme un résumé, sous la forme d’une explicitation littérale du poème qui la précède.

Le même genre de considérations s’appliquent pour le poème de niveau 3. Le « sens » du poème original conservé, les phrases sont plus grammaticalement légèrement plus complexes que pour le poème de niveau 1, mais le texte comporte à nouveau de nombreuses répétitions (« fleurs », « tourments », « paix ») ainsi qu’un pléonasme (« voilés par un voile »). La dernière strophe commence par une anaphore faisant écho à la première, phénomène que nous avions déjà observé dans le poème de niveau 1 du Dormeur du val, et présent dans de nombreux poèmes générés par ChatGPT.

#### Conclusion : caractéristiques d’écriture de ChatGPT

En somme, l’on parvient, avec cette brève analyse, à dégager plusieurs caractéristiques d’écriture de ChatGPT 3.5 lorsqu’il génère des poèmes. En effet, on repère notamment l’utilisation quasi-exclusive de mots simples et familiers, ainsi que des associations de mots génériques, et la présence de nombreuses répétitions, résultant en un style banal et résolument monotone. En outre, par moment, certaines incohérences sémantiques ou lexicales peuvent apparaitre, trahissant, pour ainsi dire, la machine. Le thème de la nature et de la contemplation de celle-ci est omniprésent, sauf mention explicite du contraire (et encore !), avec des mentions récurrentes de phénomènes atmosphériques, banalement personnifiés (« le vent murmure »). Par ailleurs, on repère également le topos de l’explicitation, la dernière strophe étant presque systématiquement un « résumé » du poème. De plus, lorsque le poème n’est pas prompté pour générer un contenu sémantique particulier, celui-ci est ainsi transformé en une entreprise quasi-pédagogique, trahissant une idée de la poésie comme une sorte de véhicule de leçons de vie banales ; il faut cueillir la beauté de la nature, il faut conquérir son destin coûte que coûte, etc. Dès lors, on assiste pour ainsi dire à une sorte de rabattement de la poésie sur la fable, la contemplation de la nature n’étant plus qu’évoquée que dans le but d’expliquer une leçon morale à en tirer.




# Supplément : Questionnaire 




