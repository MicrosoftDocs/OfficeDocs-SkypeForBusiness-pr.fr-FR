---
title: Installer le connecteur Power BI pour utiliser des modèles de requête CQD
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Installer le connecteur Power BI pour utiliser des modèles de requête CQD (Call Quality Dashboard)
ms.openlocfilehash: 534103fc2bec48566a1d0a57eeb390ed6ae0606c
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774749"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Installer le connecteur De qualité des appels Microsoft pour Power BI afin d’utiliser des modèles de requête tableau de bord qualité des appels

Avant de pouvoir utiliser les modèles de requête Power BI (fichiers PBIX) pour le tableau de bord de qualité des appels (CQD) Microsoft Teams, vous devez installer le connecteur Microsoft Call Quality pour Power BI, à l’aide du fichier *MicrosoftCallQuality.pqx* inclus dans le [téléchargement](https://www.microsoft.com/download/details.aspx?id=102291).

Consultez [Utiliser Power BI pour analyser les données CQD pour Teams](CQD-Power-BI-query-templates.md) afin d’en savoir plus sur ces modèles.

Vérifiez que vous disposez du [rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) approprié pour accéder aux rapports Power BI.

> [!NOTE]
> Le connecteur Qualité des appels Microsoft prend uniquement en charge DirectQuery dans Power BI . Le mode d’importation n’est pas pris en charge. 

## <a name="installation"></a>Installation

Le processus d’installation d’un connecteur personnalisé et d’ajustement de la sécurité pour permettre l’utilisation du connecteur est décrit en détail dans la [documentation power BI](/power-bi/desktop-connector-extensibility). Par souci de simplicité, voici une explication rapide :

1. Vérifiez si votre ordinateur dispose déjà d’un *\[dossier Documents\]\\ Power BI Desktop\\ Custom Connectors*. Si ce n’est pas le cas, créez ce dossier. <sup>1</sup>

2. Téléchargez le fichier de connecteur (fichier *\*.mez* ou *\*.pqx) et placez-le* dans le répertoire *Connecteurs personnalisés* .

3. **Si le fichier de connecteur est un *\*fichier .mez* ,** vous devez également ajuster vos paramètres de sécurité comme décrit dans la [documentation de configuration du connecteur personnalisé](/power-bi/desktop-connector-extensibility#data-extension-security).

Si une nouvelle version du connecteur Microsoft Call Quality est publiée, remplacez l’ancien fichier de connecteur dans le répertoire *Connecteurs personnalisés* par le nouveau fichier.

## <a name="setup"></a>Installation

Pour créer un rapport et exécuter des requêtes, vous devez d’abord vous connecter à la source de données CQD. Suivez les étapes ci-dessous pour vous connecter :

1. Sous l’onglet Accueil de Power BI Desktop, cliquez sur *Obtenir des données*.

    ![Obtenir des données dans le connecteur Power BI.](media/CQD-power-bi-connector1-resize.png)

2. La fenêtre *Obtenir des données* doit apparaître à ce stade. Accédez à *Services en ligne*, puis sélectionnez *Qualité des appels Microsoft (bêta)* et *appuyez sur Se connecter*.

    ![Qualité des appels Microsoft dans le connecteur Power BI.](media/CQD-power-bi-connector2-resize.png)

3. Vous serez invité à vous connecter ensuite. Utilisez les mêmes informations d’identification que celles que vous utilisez pour le tableau de bord qualité des appels. <sup>2</sup>

4. L’invite suivante vous donne l’option entre deux *modes de connectivité de données*. Sélectionnez *DirectQuery* et appuyez sur *OK*.

5. Enfin, vous recevrez une invite finale vous indiquant le modèle de données entier pour le tableau de bord qualité des appels. Aucune donnée n’est visible à ce stade, uniquement le modèle de données pour CQD. Sélectionnez *Charger* pour terminer le processus d’installation.

6. À ce stade, Power BI charge le modèle de données sur le côté droit de la fenêtre. Sinon, la page reste vide et aucune requête n’est chargée par défaut. Passez à **Génération de requêtes** ci-dessous afin de générer une requête et de retourner des données.

Si l’une des étapes de ce processus d’installation n’était pas claire, vous trouverez une explication plus détaillée du processus dans [Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Génération de requêtes

Une fois l’installation terminée, vous devez voir les noms de plusieurs centaines de dimensions et mesures chargées dans le volet *Champs* . La construction de requêtes réelles à partir d’ici est simple. Il vous suffit de sélectionner les dimensions et les mesures souhaitées pour votre requête, puis de les faire glisser et de les déposer sur la page. Voici une explication plus détaillée, avec un exemple simple :

1. Sélectionnez la visualisation que vous souhaitez utiliser dans le volet *Visualisations* . Une version vide de cette visualisation doit apparaître sur la page. Pour les besoins de cet exemple, nous allons utiliser la visualisation *Table* .

    ![Volet Visualisations dans le connecteur Power BI.](media/CQD-power-bi-connector3-resize.png)

2. Déterminez les dimensions et mesures (désignées par un symbole d’agrégation par leur nom) que vous souhaitez utiliser pour votre requête, puis sélectionnez-les manuellement et faites-les glisser vers la visualisation noire. Vous pouvez également les faire glisser sur le champ *Valeurs* sous les options de visualisation.

    ! Requête visualisations dans le connecteur Power BI.] (média/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Le tableau de bord qualité des appels nécessite une mesure pour que toute requête s’exécute. L’échec de l’ajout d’une mesure à une requête entraîne l’échec de cette requête.

3. Ensuite, sélectionnez les dimensions sur lesquelles vous souhaitez filtrer et faites-les glisser vers le champ *Filtres de ce visuel* dans le volet *Filtres* . Le connecteur Qualité des appels Microsoft prend actuellement en charge le *filtrage de base* (sélectionner des valeurs dans une liste de valeurs de dimension possibles), le *filtrage avancé* (spécifier manuellement les valeurs et les opérandes sur tableaux de bord qualité des appels) et le *filtrage de date relative* (disponible uniquement pour les dimensions *Heure de fin* et *Heure de début* ). Le filtrage en fonction des *N premiers* n’est pas pris en charge par le tableau de bord de qualité des appels.

    ![Les visualisations filtrent dans le connecteur Power BI.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Les filtres sont pris en charge uniquement lorsqu’ils sont appliqués à Dimensions. Le filtrage sur les valeurs de Mesures n’est pas pris en charge dans le tableau de bord qualité des appels.

4. Enfin, sélectionnez l’onglet *Format* dans le volet *Visualisations* pour appliquer un style et mettre en forme votre requête.

    > [!NOTE]
    > Les requêtes Call Quality Dashboard nécessitent au moins une mesure pour s’exécuter. Si votre requête ne se charge pas, vérifiez que vous avez inclus une mesure dans la requête.

## <a name="creating-a-drillthrough-report"></a>Création d’un rapport d’extraction

[L’extraction dans Power BI](/power-bi/desktop-drillthrough) vous permet de créer des rapports ciblés que vous pouvez filtrer rapidement en utilisant les valeurs d’autres rapports comme contexte. Une fois que vous savez comment créer votre première requête avec le connecteur Microsoft Call Quality, la création d’une extraction est encore plus simple.

1. Créez une autre page pour le rapport prioritaire, puis ajoutez vos requêtes à cette page.

2. Sélectionnez la dimension que vous souhaitez utiliser comme filtre d’extraction et faites-la glisser sur le champ *Extraction* sous dans le volet *Visualisations* .

    ![Extraction dans le connecteur Power BI.](media/CQD-power-bi-connector6-resize.png)

3. **Voilà\!** Toute autre requête sur une autre page qui utilise cette dimension peut désormais accéder à cette page, en appliquant automatiquement la valeur de la dimension d’extraction en tant que filtre.

    ![Filtre d’extraction dans le connecteur Power BI.](media/CQD-power-bi-connector7-resize.png)

Contrairement au tableau de bord qualité des appels, Power BI prend en charge l’extraction non séquentielle. Si une requête inclut la dimension nécessaire, elle peut accéder à n’importe quelle autre page.

### <a name="best-practice"></a>Bonne pratique

Les requêtes du connecteur Qualité des appels Microsoft doivent être conçues avec la fonctionnalité d’extraction à l’esprit. Au lieu d’essayer de charger toutes les données à la fois, puis de découper avec des filtres, commencez par des requêtes plus larges à faible cardinalité et explorez les requêtes à cardinalité élevée. Par exemple, lorsque vous tentez de diagnostiquer les sous-réseaux qui contribuent le plus aux problèmes de qualité, il est utile d’identifier d’abord les régions et les pays qui contribuent au problème, puis d’explorer les sous-réseaux de cette région ou pays. Les modèles de connecteur qualité des appels ont été conçus de cette manière pour servir d’exemple.

## <a name="limitations"></a>Limites

Malgré l’utilisation de Power BI, toutes les fonctionnalités de Power BI ne sont pas prises en charge par le connecteur De qualité des appels Microsoft, soit en raison des limitations du modèle de données du tableau de bord de qualité des appels, soit des connecteurs DirectQuery en général. La liste ci-dessous note certaines des limitations les plus notables du connecteur, mais cette liste ne doit pas être considérée comme exhaustive :

1. **Colonnes calculées –** En général, les connecteurs DirectQuery prennent en charge les colonnes calculées dans Power BI. Certaines colonnes calculées peuvent fonctionner avec le connecteur, car ces colonnes sont des exceptions. En règle générale, les colonnes calculées ne fonctionnent pas.

2. **Agrégations–** Le modèle de données Tableau de bord qualité des appels est basé sur un modèle de cube, ce qui signifie que les agrégations sont déjà prises en charge sous forme de mesures. La tentative d’ajout manuel d’agrégations à différentes dimensions ou la modification du type d’agrégation d’une mesure ne fonctionne pas avec le connecteur et génère généralement une erreur.

3. **Visuels personnalisés :** Bien que le connecteur Microsoft Call Quality fonctionne avec une gamme de visuels personnalisés, nous ne pouvons pas garantir la compatibilité avec tous les visuels personnalisés. De nombreux visuels personnalisés s’appuient sur l’utilisation de colonnes calculées ou de données importées, dont aucun n’est pris en charge par les connecteurs DirectQuery.

4. **Référencement de données mises en cache –** Actuellement, Power BI ne prend pas en charge le référencement des données mises en cache à partir d’un connecteur DirectQuery. Toute tentative de référencer les résultats d’une requête entraîne une nouvelle requête.

5. **Filtrage des données relatives –** Est pris en charge dans le connecteur Qualité des appels Microsoft, mais uniquement avec les dimensions *Heure de début* et *Heure de fin* . Bien que la dimension *Date* puisse être le choix évident pour le filtrage de date relative, *Date* n’est pas stocké en tant qu’objet date-heure et ne prend donc pas en charge le filtrage de date relative dans Power BI.

6. **Requêtes de mesure uniquement -** Ne sont pas pris en charge pour l’instant dans le connecteur Qualité des appels Microsoft. Lors de la création d’une visualisation avec au moins trois mesures et aucune dimension, les données de colonne sont transposees. Pour éviter cela, incluez toujours au moins une dimension (par exemple, Mois Année) dans vos visualisations. Ce problème devrait être résolu dans une prochaine version du connecteur Qualité des appels Microsoft pour Power BI.

7. **Prise en charge du cloud de la communauté du secteur public (GCC) –** Pour les clients de l’environnement GCC, le connecteur Microsoft Call Quality fonctionne uniquement lors de l’utilisation de Power BI Desktop. Le connecteur Qualité des appels Microsoft n’est actuellement pas compatible avec la service Power BI pour les clients gcc.

La plupart de ces problèmes sont des restrictions à la conception du connecteur DirectQuery dans Power BI ou sont fondamentaux pour la conception du modèle de données CQD.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>J’essaie d’utiliser la colonne Date comme segment Date. Dès que je convertit le type de données de cette colonne en Date, je reçois cette erreur

> **Impossible de charger les données pour ce visuel** : ERREUR OLE DB ou ODBC : [Expression.Error] Nous n’avons pas pu plier l’expression dans la source de données. Essayez une expression plus simple.

Les segments de date ne sont pas pris en charge avec le connecteur Qualité des appels Microsoft. Pour spécifier une plage de dates, appliquez deux filtres au rapport, en spécifiant une valeur inférieure à et supérieure à la date.

Sinon, si les dates que vous souhaitez afficher sont récentes, appliquez un filtre de date relative pour afficher uniquement les données des N derniers jours/semaines/mois.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Lorsque j’ajoute certaines dimensions à mes rapports, le visuel retourne immédiatement **« Impossible de charger les données pour ce visuel ».** La suppression de la dimension corrige le visuel : que se passe-t-il ?

Il s’agit d’un problème connu dans le connecteur Qualité des appels Microsoft ; Toute dimension exposée sous forme de nombre entier s’affiche dans Power BI sous la forme d’une colonne « agrégée », où Power BI tente une action de synthèse par défaut (généralement « Somme »). Dans certains cas, ce comportement réussit à additionner les valeurs même si le résultat n’est pas utile, car la « somme » d’une dimension comme Second WiFi Channel est vide de sens. Dans d’autres cas, cette action de synthèse échoue et provoque des erreurs dans le visuel.

Pour contourner ce problème, commencez par supprimer la dimension du visuel. Sélectionnez la dimension dans la liste « Champs », accédez à l’onglet « Outils de colonne » dans le ruban, cliquez sur le menu déroulant « Résumé », puis sélectionnez **Ne pas résumer**. La dimension peut maintenant être ajoutée à nouveau au visuel.


## <a name="error-codes"></a>Codes d’erreur

Étant donné que le connecteur Qualité des appels Microsoft pour Power BI est moins restreint que l’application de navigateur en termes de types de requêtes que vous pouvez construire, vous pouvez parfois rencontrer un certain nombre d’erreurs lors de la création de vos requêtes. Si vous recevez un message d’erreur du type « CQDError. RunQuery – Erreur d’exécution de requête », référencez la liste ci-dessous avec le numéro ErrorType fourni afin de résoudre le problème possible avec la requête. Voici les codes de type d’erreur les plus courants que vous pouvez rencontrer avec le connecteur Power BI CQD :

- **ErrorType 1 - Erreur de structure de requête :** Une erreur de structure de requête est généralement due à l’échec du connecteur à générer une requête correctement mise en forme. Cela se produit le plus souvent lors de l’utilisation de fonctionnalités non prises en charge, comme spécifié dans les limitations ci-dessus. Vérifiez que vous n’utilisez pas de colonnes calculées ou de visuels personnalisés pour cette requête.

  - **ErrorType 2 - Erreur de génération de requête :** Une erreur de génération de requête est due au fait que le connecteur Microsoft Call Quality ne parvient pas à analyser correctement la requête que vous essayez de générer. Cela se produit le plus souvent lors de l’utilisation de fonctionnalités non prises en charge, comme spécifié dans les limitations ci-dessus. Vérifiez que vous n’utilisez pas de colonnes calculées ou de visuels personnalisés pour cette requête.

  - **ErrorType 5 - Délai d’exécution :** La requête a atteint le maximum d’exécution possible avant expiration. Essayez d’ajouter d’autres filtres à la requête afin de limiter son étendue. La réduction de la plage de données est souvent le moyen le plus efficace d’y parvenir.

  - **ErreurType 7 - Erreur aucune mesure :** Les requêtes Call Quality Dashboard nécessitent une mesure pour fonctionner. Vérifiez que votre requête inclut une mesure. Les mesures du connecteur Qualité des appels Microsoft sont indiquées par le symbole d’agrégation (somme) avant leur nom.

Si vous rencontrez des erreurs supplémentaires en dehors de cette étendue, veuillez en informer l’équipe du tableau de bord de qualité des appels afin que nous puissions vous aider à résoudre le problème et mettre à jour la documentation le cas échéant.

## <a name="footnotes"></a>Notes

**<sup>1</sup>** Certains processus et applications (par exemple, OneDrive) peuvent entraîner la modification de votre dossier racine Documents ; assurez-vous que le répertoire *Power BI Desktop\\ Custom Connectors* est placé à l’intérieur du dossier racine Actuel dossier Documents.

**<sup>2</sup>** Les informations d’identification de connexion que vous utilisez pour le tableau de bord qualité des appels *n’ont pas* besoin d’être les mêmes que celles que vous utilisez pour vous connecter à l’application Power BI Desktop elle-même.

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quand le connecteur Power BI sera-t-il mis à jour à partir de l’état « Bêta » ?

Malgré la balise Bêta, le connecteur Microsoft Call Quality (bêta) pour Power BI est la première version « release » du connecteur et a été officiellement signé par l’équipe Power BI pour refléter cela. Au moment de la publication initiale du connecteur, l’équipe Power BI n’était pas en mesure de fournir un support et une certification plus large, mais elle était toujours prête à attester de la sécurité, de l’authenticité et des fonctionnalités générales du connecteur Qualité des appels Microsoft. À l’avenir, nous prévoyons d’investir dans le connecteur Microsoft Call Quality pour Power BI dans un avenir proche.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Pourquoi le connecteur semble-t-il plus lent par rapport au tableau de bord qualité des appels dans le navigateur ? Que puis-je faire pour améliorer les performances ?

Les performances des requêtes pour les différents modèles sont en fait les mêmes dans le navigateur et dans le connecteur.  Comme toute autre application autonome, Power BI ajoute son temps d’authentification et de rendu à nos performances. En outre, la différence vient du nombre de requêtes simultanées exécutées. Étant donné que la version dans le navigateur du tableau de bord de qualité des appels comportait des options de visualisation moins développées et plus denses en informations, la plupart de nos rapports étaient limités au chargement de 2 à 3 requêtes à la fois. En revanche, les modèles de connecteur affichent souvent plus de 20 requêtes simultanées. Si vous souhaitez créer des rapports qui sont tout aussi réactifs que les anciens auxquels vous étiez habitué, essayez de créer des rapports avec pas plus de 2 à 3 requêtes par onglet.

Pour plus d’informations, consultez les articles suivants :

- [Guide d’optimisation pour Power BI](/power-bi/guidance/power-bi-optimization)
- [Guide du modèle DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Je constate que je rencontre systématiquement la limite de 10 000 lignes lors de l’exécution de requêtes. Comment puis-je faire en sorte que le connecteur retourne plus de 10 000 lignes ?

La limite de 10 000 lignes est en fait spécifiée à l’extrémité de l’API, et elle est conçue pour aider à améliorer considérablement les performances et à réduire le risque d’erreurs d’exécution des requêtes résultant de conditions de mémoire insuffisantes.

Au lieu d’essayer d’augmenter le nombre de lignes de résultat, il est préférable de restructurer vos rapports conformément aux meilleures pratiques du connecteur. Les modèles que nous avons inclus sont conçus pour illustrer ces meilleures pratiques. Dans la mesure du possible, commencez par examiner vos indicateurs de performance clés à l’aide de dimensions plus larges et à cardinalité inférieure, telles que le mois, l’année, la date, la région, le pays, etc. À partir de là, vous pouvez explorer des dimensions de cardinalité de plus en plus élevées. Le support technique et les rapports Location-Enhanced fournissent tous deux de bons exemples de ce flux de travail d’exploration.



## <a name="related-topics"></a>Rubriques connexes

[Utiliser Power BI pour analyser les données CQD pour Teams](CQD-Power-BI-query-templates.md)
