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
- <span style="color:green">Ex : Écris un sonnet dans le style d'Arthur Rimbaud</span>

Pour le **deuxième niveau de prompting**, nous avons donné un example à imiter. Nous avons pris chaque poème de notre dataset de "poèmes humains" et demandé à ChatGPT de générer un poème ressemblant à celui-ci. 

- <span style="color:green;white-space:pre-line">Ex : Écris un poème qui ressemble à celui-ci : 
    Napoléon mourant vit une Tête armée… 
    Il pensait à son fils déjà faible et souffrant :
    La Tête, c’était donc sa France bien-aimée,
    Décapitée aux pieds du César expirant.</span>

    <span style="color:green;white-space:pre-line">Dieu, qui jugeait cet homme et cette renommée,
    Appela Jésus-Christ ; mais l’abîme s’ouvrant,
    Ne rendit qu’un vain souffle, un spectre de fumée :
    Le Demi-Dieu, vaincu, se releva plus grand.</span>
    
    <span style="color:green;white-space:pre-line">Alors on vit sortir du fond du purgatoire
    Un jeune homme inondé des pleurs de la Victoire,
    Qui tendit sa main pure au monarque des cieux ;</span>

    <span style="color:green;white-space:pre-line">Frappés au flanc tous deux par un double mystère,
    L’un répandait son sang pour féconder la Terre,
    L’autre versait au ciel la semence des dieux !</span>
 
 
 
 Pour le **troisième niveau de prompting**, nous avons donné des indications pour "reproduire" le poème. Nous avons indiqué le début du poème, la forme, les thèmes, les champs lexicaux, et le style général. 
- <span style="color:green">Ex: 12.	Voici des instructions pour écrire un poème : 
    - Commence par « Esprit parisien ! démon du Bas-Empire !
      Vieux sophiste épuisé qui boit, toutes les nuits, »
    - Respecte la forme sonnet (deux quatrains et deux tersets)
    - Ecris un poème qui parle de l’Esprit parisien en le personnifiant. Prends un ton cynique et ironique pour faire une critique sociale
    - Met en lumière l’hypocrisie, la cruauté et la superficialité de l’Esprit parisien </span>

## Méthodes 

## Résultats 

## Discussion 
