---
title: Installer Power BI Connecteur pour utiliser des modèles de requête CQD
ms.author: serdars
author: SerdarSoysal
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
description: Installer Power BI Connecteur pour utiliser des modèles de requête CQD (Call Quality Dashboard)
ms.openlocfilehash: 3ca8a4c70b23923dcf49906b85529c7b7e369008
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675256"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Installer le connecteur Microsoft Call Quality pour Power BI pour utiliser des modèles de requête Tableau de bord qualité des appels

Avant de pouvoir utiliser les modèles de requête Power BI (fichiers PBIX) pour Microsoft Teams tableau de bord de qualité des appels (CQD), vous devez installer le connecteur Microsoft Call Quality pour Power BI, à l’aide du fichier *MicrosoftCallQuality.pqx* inclus dans le [téléchargement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).

Lire [Utiliser Power BI pour analyser les données de CQD pour Teams](CQD-Power-BI-query-templates.md) en savoir plus sur ces modèles.

Assurez-vous que vous disposez du [rôle d’accès CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) approprié pour accéder aux rapports Power BI.

> [!NOTE]
> Le connecteur Microsoft Call Quality prend uniquement en charge DirectQuery dans Power BI ; Le mode d’importation n’est pas pris en charge. 

## <a name="installation"></a>Installation

Le processus d’installation d’un connecteur personnalisé et d’ajustement de la sécurité pour permettre l’utilisation du connecteur est décrit en détail dans la [documentation Power BI](/power-bi/desktop-connector-extensibility). Par souci de simplicité, voici une explication rapide :

1. Vérifiez si votre ordinateur dispose déjà d’un *\[dossier Documents\]\\ Power BI Desktop\\ Custom Connectors*. Si ce n’est pas le cas, créez ce dossier. <sup>1</sup>

2. Téléchargez le fichier de connecteur (fichier *\*.mez* ou *\*.pqx* ) et placez-le dans le répertoire *des connecteurs personnalisés* .

3. **Si le fichier de connecteur est un *\*fichier .mez* ,** vous devez également ajuster vos paramètres de sécurité comme décrit dans la [documentation d’installation du connecteur personnalisé](/power-bi/desktop-connector-extensibility#data-extension-security).

Si une nouvelle version du connecteur Microsoft Call Quality est publiée, remplacez l’ancien fichier de connecteur dans le répertoire *Connecteurs personnalisés* par le nouveau fichier.

## <a name="setup"></a>Installation

Pour créer un rapport et exécuter des requêtes, vous devez d’abord vous connecter à la source de données CQD. Suivez les étapes ci-dessous pour vous connecter :

1. Sous l’onglet Accueil de Power BI Desktop, cliquez sur *Obtenir des données*.

    ![Obtenir des données dans le connecteur Power BI.](media/CQD-power-bi-connector1-resize.png)

2. La fenêtre *Obtenir des données* doit apparaître à ce stade. Accédez aux *services en ligne*, puis sélectionnez *Microsoft Call Quality (bêta)* et appuyez *sur Connecter*.

    ![Qualité des appels Microsoft dans le connecteur Power BI.](media/CQD-power-bi-connector2-resize.png)

3. Vous serez invité à vous connecter ensuite. Utilisez les mêmes informations d’identification que pour le tableau de bord qualité des appels. <sup>2</sup>

4. L’invite suivante vous donnera l’option entre deux *modes de connectivité des données*. Sélectionnez *DirectQuery* et appuyez sur *OK*.

5. Enfin, vous recevrez une invite finale vous montrant l’intégralité du modèle de données du tableau de bord qualité des appels. Aucune donnée n’est visible à ce stade, uniquement le modèle de données pour CQD. Sélectionnez *Charger* pour terminer le processus d’installation.

6. À ce stade, Power BI charge le modèle de données sur le côté droit de la fenêtre. Dans le cas contraire, la page reste vide et aucune requête n’est chargée par défaut. Passez à **Générer des requêtes ci-dessous** afin de générer une requête et de retourner des données.

Si l’une des étapes de ce processus d’installation n’était pas claire, vous trouverez une explication plus détaillée du processus dans le guide de [démarrage rapide : Connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Création de requêtes

Une fois l’installation terminée, vous devez voir les noms de plusieurs centaines de dimensions et de mesures charger dans le volet *Champs* . La construction de requêtes réelles à partir d’ici est simple, il vous suffit de sélectionner les dimensions et les mesures souhaitées pour votre requête, puis de les faire glisser et de les déposer sur la page. Voici une explication plus détaillée, avec un exemple simple :

1. Sélectionnez la visualisation que vous souhaitez utiliser dans le volet *Visualisations* . Une version vide de cette visualisation doit apparaître sur la page. Pour les besoins de cet exemple, nous allons utiliser la visualisation *table* .

    ![Volet Visualisations dans le connecteur Power BI.](media/CQD-power-bi-connector3-resize.png)

2. Déterminez les dimensions et mesures (indiquées par un symbole d’agrégation par leur nom) que vous souhaitez utiliser pour votre requête, puis sélectionnez-les manuellement et faites-les glisser sur la visualisation noire. Vous pouvez également les faire glisser sur le champ *Valeurs* sous les options de visualisation.

    ! Requête visualisations dans le connecteur Power BI.] (média/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Call Quality Dashboard nécessite une mesure pour toute requête à exécuter. L’échec de l’ajout d’une mesure à une requête entraîne l’échec de cette requête.

3. Ensuite, sélectionnez les dimensions sur lesquelles vous souhaitez filtrer et faites-les glisser vers les *filtres de ce champ visuel* dans le volet *Filtres* . Le connecteur Qualité des appels Microsoft prend actuellement en charge le *filtrage de base* (sélectionner des valeurs dans une liste de valeurs de dimension possibles), le *filtrage avancé* (spécifier manuellement les valeurs et les opérandes sur lequel filtrer, comme le tableau de bord qualité des appels) et le *filtrage de date relative* (disponible uniquement pour les dimensions *Heure de fin* et Heure de *début* ). Le filtrage en fonction du *N supérieur n’est* pas pris en charge par le tableau de bord qualité des appels.

    ![Filtres de visualisations dans le connecteur Power BI.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Les filtres sont pris en charge uniquement lorsqu’ils sont appliqués aux dimensions. Le filtrage sur les valeurs des mesures n’est pas pris en charge dans le tableau de bord qualité des appels.

4. Enfin, sélectionnez l’onglet *Format* dans le volet *Visualisations* pour appliquer un style et mettre en forme votre requête.

    > [!NOTE]
    > Les requêtes du tableau de bord qualité des appels nécessitent au moins une mesure pour s’exécuter. Si votre requête ne se charge pas, vérifiez que vous avez inclus une mesure dans la requête.

## <a name="creating-a-drillthrough-report"></a>Création d’un rapport d’extraction

[L’extraction dans Power BI](/power-bi/desktop-drillthrough) vous permet de créer des rapports axés que vous pouvez filtrer rapidement à l’aide des valeurs d’autres rapports en tant que contexte. Une fois que vous savez comment créer votre première requête avec le connecteur Microsoft Call Quality, la création d’une extraction est encore plus simple.

1. Créez une autre page pour le rapport ciblé, puis ajoutez vos requêtes à cette page.

2. Sélectionnez la dimension que vous souhaitez utiliser comme filtre d’extraction et faites-les glisser vers le champ *Extraction* sous le volet *Visualisations* .

    ![Extraction dans le connecteur Power BI.](media/CQD-power-bi-connector6-resize.png)

3. **Voilà\!** Toute autre requête d’une autre page qui utilise cette dimension peut maintenant explorer cette page, en appliquant automatiquement la valeur de la dimension d’extraction en tant que filtre.

    ![Filtre d’extraction dans le connecteur Power BI.](media/CQD-power-bi-connector7-resize.png)

Contrairement au tableau de bord qualité des appels, Power BI prend en charge l’extraction non séquentielle. Si une requête inclut la dimension nécessaire, elle peut explorer n’importe quelle autre page.

### <a name="best-practice"></a>Bonne pratique

Les requêtes de connecteur De qualité des appels Microsoft doivent être conçues avec des fonctionnalités d’extraction à l’esprit. Au lieu d’essayer de charger toutes les données en même temps, puis de les découper avec des filtres, commencez par des requêtes plus larges à faible cardinalité et explorez les requêtes à cardinalité élevée. Par exemple, lorsque vous tentez de diagnostiquer les sous-réseaux qui contribuent le plus aux problèmes de qualité, il est utile d’abord d’identifier les régions et les pays qui contribuent au problème, puis d’explorer les sous-réseaux de cette région ou pays. Les modèles de connecteurs Qualité des appels ont été conçus de cette manière pour servir d’exemple.

## <a name="limitations"></a>Limites

Malgré l’utilisation de Power BI, toutes les fonctionnalités Power BI ne sont pas prises en charge par le connecteur Microsoft Call Quality, soit en raison de limitations sur le modèle de données du tableau de bord de qualité des appels, soit sur les connecteurs DirectQuery en général. La liste ci-dessous note certaines des limitations les plus importantes du connecteur, mais cette liste ne doit pas être considérée comme exhaustive :

1. **Colonnes calculées :** Les connecteurs DirectQuery en général ont une prise en charge limitée des colonnes calculées dans Power BI. Certaines colonnes calculées peuvent fonctionner avec le connecteur, que ces colonnes sont des exceptions. En règle générale, les colonnes calculées ne fonctionnent pas.

2. **Agrégations :** Le modèle de données Tableau de bord de la qualité des appels repose sur un modèle de cube, ce qui signifie que les agrégations sont déjà prises en charge sous la forme de mesures. Toute tentative d’ajout manuel d’agrégations à différentes dimensions ou de modification du type d’agrégation d’une mesure ne fonctionne pas avec le connecteur, ce qui entraîne généralement une erreur.

3. **Visuels personnalisés :** Bien que le connecteur Microsoft Call Quality fonctionne avec une gamme de visuels personnalisés, nous ne pouvons pas garantir la compatibilité avec tous les visuels personnalisés. De nombreux visuels personnalisés s’appuient sur l’utilisation de colonnes calculées ou de données importées, dont aucun n’est pris en charge par les connecteurs DirectQuery.

4. **Référencement des données mises en cache :** Power BI ne prend actuellement pas en charge le référencement de données mises en cache à partir d’un connecteur DirectQuery d’aucune façon. Toute tentative de référence des résultats d’une requête entraîne une nouvelle requête.

5. **Filtrage des données relatives :** Est pris en charge dans le connecteur Microsoft Call Quality, mais uniquement avec les dimensions *Heure de début* et *Heure de fin* . Bien que la dimension *Date* puisse être le choix évident pour le filtrage de date relative, *la date* n’est pas stockée en tant qu’objet date/heure et ne prend donc pas en charge le filtrage de date relative dans Power BI.

6. **Requêtes de mesure uniquement -** Ne sont pas pris en charge pour l’instant dans le connecteur Microsoft Call Quality. Lors de la création d’une visualisation avec au moins trois mesures et aucune dimension, les données de colonne sont transposées. Pour éviter cela, incluez toujours au moins une dimension (par exemple: Month Year) dans vos visualisations. Cette situation devrait être résolue dans une prochaine version du connecteur Microsoft Call Quality pour Power BI.

7. **prise en charge Cloud de la communauté du secteur public (Cloud de la communauté du secteur public) :** pour les clients de l’environnement Cloud de la communauté du secteur public, le connecteur Microsoft Call Quality fonctionne lors de l’utilisation Power BI Desktop seulement. Le connecteur Microsoft Call Quality n’est actuellement pas compatible avec le service Power BI pour les clients Cloud de la communauté du secteur public.

La plupart de ces problèmes sont des restrictions à la conception du connecteur DirectQuery en Power BI ou fondamentales à la conception du modèle de données CQD.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>J’essaie d’utiliser la colonne Date comme segment date. Dès que je convertis le type de données de cette colonne en Date, j’obtiens cette erreur

> **Impossible de charger les données pour ce visuel** : erreur OLE DB ou ODBC : [Expression.Error] Nous n’avons pas pu plier l’expression à la source de données. Essayez une expression plus simple.

Les segments de date ne sont pas pris en charge avec le connecteur Microsoft Call Quality. Pour spécifier une plage de dates, appliquez deux filtres au rapport, en spécifiant une valeur inférieure et supérieure à la date.

Sinon, si les dates que vous souhaitez afficher sont récentes, appliquez un filtre de date relative pour afficher uniquement les données des N jours/semaines/mois précédents.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Lorsque j’ajoute certaines dimensions à mes rapports, le visuel retourne immédiatement **« Impossible de charger les données pour ce visuel** ». La suppression de la dimension corrige le visuel : que se passe-t-il ?

Il s’agit d’un problème connu dans le connecteur Microsoft Call Quality ; toute dimension exposée sous la forme d’un nombre entier apparaîtra dans Power BI sous la forme d’une colonne d’agrégation, où Power BI tentera une action de synthèse par défaut (généralement « Somme »). Dans certains cas, ce comportement réussit à additionner les valeurs même si le résultat n’est pas utile, car la « somme » d’une dimension comme Second WiFi Channel n’a aucun sens. Dans d’autres cas, cette action de synthèse échoue et provoque des erreurs dans le visuel.

Pour contourner ce problème, commencez par supprimer la dimension du visuel. Sélectionnez la dimension dans la liste « Champs », accédez à l’onglet « Outils de colonne » dans le ruban, cliquez sur le menu déroulant « Résumé », puis sélectionnez **Ne pas résumer**. La dimension peut maintenant être ajoutée à nouveau au visuel.


## <a name="error-codes"></a>Codes d’erreur

Étant donné que le connecteur Microsoft Call Quality pour Power BI est moins restreint que l’application de navigateur en termes de types de requêtes que vous pouvez construire, vous pouvez parfois rencontrer un certain nombre d’erreurs lors de la création de vos requêtes. Si vous recevez un message d’erreur de type « CQDError ». RunQuery – Erreur d’exécution de requête », référencez la liste ci-dessous avec le numéro ErrorType fourni pour résoudre le problème possible avec la requête. Voici les codes de type d’erreur les plus courants que vous pouvez rencontrer avec le connecteur CQD Power BI :

- **ErrorType 1 - Erreur de structure de requête :** Une erreur de structure de requête est généralement due à l’échec de la génération d’une requête correctement mise en forme par le connecteur. Cela se produit le plus souvent lors de l’utilisation de fonctionnalités non prises en charge, comme spécifié dans les limitations ci-dessus. Vérifiez que vous n’utilisez pas de colonnes calculées ou de visuels personnalisés pour cette requête.

  - **ErrorType 2 - Erreur de génération de requêtes :** Une erreur de génération de requête est provoquée par l’impossibilité pour le connecteur Microsoft Call Quality d’analyser correctement la requête que vous tentez de générer. Cela se produit le plus souvent lors de l’utilisation de fonctionnalités non prises en charge, comme spécifié dans les limitations ci-dessus. Vérifiez que vous n’utilisez pas de colonnes calculées ou de visuels personnalisés pour cette requête.

  - **ErrorType 5 - Délai d’exécution :** La requête a atteint le runtime maximal possible avant expiration du délai d’attente. Essayez d’ajouter d’autres filtres à la requête afin de limiter son étendue. Le rétrécissement de la plage de données est souvent le moyen le plus efficace d’y parvenir.

  - **ErrorType 7 - Aucune erreur de mesure :** Les requêtes tableau de bord qualité des appels nécessitent une mesure pour fonctionner. Vérifiez que votre requête inclut une mesure. Les mesures du connecteur Microsoft Call Quality sont indiquées par le symbole d’agrégation (somme) avant leur nom.

Si vous rencontrez des erreurs supplémentaires en dehors de cette étendue, informez l’équipe du tableau de bord qualité des appels afin que nous puissions aider à résoudre le problème et mettre à jour la documentation selon les besoins.

## <a name="footnotes"></a>Notes

**<sup>1</sup>** Certains processus et applications (par exemple, OneDrive) peuvent entraîner la modification de votre dossier racine Documents ; assurez-vous que le répertoire *Power BI Desktop\\ Custom Connectors* est placé à l’intérieur du dossier racine actuel Documents.

**<sup>2</sup>** Les informations d’identification de connexion que vous utilisez pour Call Quality Dashboard *n’ont pas* besoin d’être les mêmes que vous utilisez pour vous connecter à l’application Power BI Desktop elle-même.

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quand le connecteur Power BI sera-t-il mis à jour à partir de l’état « Bêta » ?

Malgré la balise Bêta, le connecteur Microsoft Call Quality (bêta) pour Power BI est la première version « release » du connecteur et a été officiellement signé par l’équipe Power BI pour refléter cela. Au moment de la publication initiale du connecteur, l’équipe Power BI n’était pas en mesure de fournir un support et une certification plus large, mais elle était toujours prête à attester de la sécurité, de l’authenticité et des fonctionnalités générales du connecteur Microsoft Call Quality. À l’avenir, nous prévoyons d’investir dans le connecteur Microsoft Call Quality pour Power BI dans un avenir proche.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Pourquoi le connecteur semble-t-il plus lent que le tableau de bord qualité des appels dans le navigateur ? Que puis-je faire pour améliorer les performances ?

Les performances des requêtes pour les différents modèles sont en fait les mêmes dans le navigateur et dans le connecteur.  Comme n’importe quelle autre application autonome, Power BI ajoute son temps d’authentification et de rendu à nos performances. En outre, la différence réside dans le nombre de requêtes simultanées exécutées. Étant donné que la version dans le navigateur du tableau de bord qualité des appels avait des options de visualisation moins bien développées et moins riches en informations, la plupart de nos rapports étaient limités au chargement de 2 à 3 requêtes à la fois. En revanche, les modèles de connecteur affichent souvent plus de 20 requêtes simultanées. Si vous souhaitez créer des rapports tout aussi réactifs que les anciens, essayez de créer des rapports avec pas plus de 2 à 3 requêtes par onglet.

Pour plus d’informations, consultez les articles suivants :

- [Guide d’optimisation pour Power BI](/power-bi/guidance/power-bi-optimization)
- [Guide du modèle DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Je trouve que je rencontre régulièrement la limite de 10 000 lignes lors de l’exécution de requêtes. Comment puis-je obtenir que le connecteur retourne plus de 10 000 lignes ?

La limite de 10 000 lignes est en fait spécifiée à l’extrémité de l’API, et elle est conçue pour améliorer considérablement les performances et réduire le risque d’erreurs d’exécution de requête résultant de conditions de mémoire insuffisantes.

Au lieu de tenter d’augmenter le nombre de lignes de résultats, il est préférable de restructurer vos rapports en fonction des meilleures pratiques du connecteur. Les modèles que nous avons inclus sont conçus pour illustrer ces bonnes pratiques. Dans la mesure du possible, commencez par examiner vos indicateurs de performance clés à l’aide de dimensions de cardinalité plus larges et inférieures, telles que mois, année, date, région, pays, etc. À partir de là, vous pouvez explorer des dimensions de cardinalité de plus en plus élevées. Les rapports helpdesk et Location-Enhanced fournissent tous deux de bons exemples de ce flux de travail d’exploration.



## <a name="related-topics"></a>Voir aussi

[Utilisez Power BI pour analyser les données de CQD pour Teams](CQD-Power-BI-query-templates.md)
