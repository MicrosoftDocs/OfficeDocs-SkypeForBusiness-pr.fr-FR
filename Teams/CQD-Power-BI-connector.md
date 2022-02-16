---
title: Installer Power BI connector pour utiliser des modèles de requête de recherche de détails de la recherche
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
description: Installer Power BI connecteur pour utiliser des modèles de requête de tableau de bord de qualité des appels
ms.openlocfilehash: 474edeca9e694e38e1503074fc45c8bcdaca3483
ms.sourcegitcommit: f0eaaf67b4fdce87d5c01b456c506c1435714ced
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "62852497"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Installer le connecteur Qualité d’appel De Microsoft Power BI utiliser les modèles de requête Tableau de bord de qualité d’appel

Avant d’utiliser les modèles de requête Power BI (fichiers PBIX) pour le tableau de bord de qualité des appels de Microsoft Teams, vous devez installer le connecteur Qualité des appels de Microsoft pour Power BI à l’aide du fichier *MicrosoftCallQuality.pqx* inclus dans le [téléchargement.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

[Lisez Utiliser Power BI pour analyser les données du Teams](CQD-Power-BI-query-templates.md) pour en savoir plus sur ces modèles.

Assurez-vous que vous avez le rôle [d’accès du CQD droit pour](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) accéder aux Power BI rapports.

> [!NOTE]
> Le connecteur Qualité d’appel Microsoft prend uniquement en charge DirectQuery Power BI ; Le mode Importation n’est pas pris en charge. 

## <a name="installation"></a>Installation

Le processus d’installation d’un connecteur personnalisé et d’ajustement de la sécurité pour permettre l’utilisation du connecteur est décrit en détail dans la [Power BI documents.](/power-bi/desktop-connector-extensibility) À des fins de simplicité, voici une explication rapide :

1. Vérifiez si votre ordinateur possède déjà un dossier *\[Documents\]\\ Power BI Desktop\\ Custom Connectors*. Si ce n’est pas le cas, créez ce dossier. <sup>1</sup>

2. Téléchargez le fichier du connecteur ( *\*fichier .mez* *\*ou .pqx* ) et placez-le dans le répertoire *Connecteurs personnalisés* .

3. **Si le fichier du connecteur est *\*un fichier .mez* ,** vous devrez également ajuster vos paramètres de sécurité, comme décrit dans la documentation de configuration de connecteur [personnalisée](/power-bi/desktop-connector-extensibility#data-extension-security).

Si une nouvelle version du connecteur Microsoft Call Quality est publiée, remplacez l’ancien fichier de connecteur dans le répertoire *Connecteurs personnalisés* par le nouveau fichier.

## <a name="setup"></a>Installation

Pour créer un état et exécuter des requêtes, vous devez d’abord vous connecter à la source de données du CQD. Pour vous connecter, suivez les étapes ci-dessous :

1. Dans l’onglet Accueil de Power BI Desktop, cliquez sur *Obtenir des données*.

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector1-resize.png)

2. La *fenêtre Obtenir des* données doit apparaître à ce stade. Accédez à *Online Services*, puis sélectionnez *Qualité des appels Microsoft (bêta),* puis *sélectionnez Connecter*.

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector2-resize.png)

3. Vous serez invité à vous connectez ensuite. Utilisez les mêmes informations d’identification que vous utilisez pour le tableau de bord de qualité des appels. <sup>2</sup>

4. L’invite suivante vous permet d’choisir entre deux *modes Connectivité des données*. *Sélectionnez DirectQuery et* sélectionnez *OK*.

5. Pour finir, une invite finale vous montre l’intégralité du modèle de données du tableau de bord qualité des appels. À ce stade, aucune donnée ne sera visible, seul le modèle de données du CQD sera visible. *Sélectionnez Charger* pour terminer le processus de configuration.

6. À ce stade, Power BI charge le modèle de données sur le côté droit de la fenêtre. Sinon, la page reste vide et aucune requête n’est chargée par défaut. Passer à **la création de requêtes ci-dessous** pour créer une requête et renvoyer des données.

Si l’une des étapes de ce processus d’installation n’a pas été claire, une explication plus détaillée de ce processus est expliquée dans le démarrage rapide : Connecter aux données dans [Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Création de requêtes

Une fois la configuration terminée, vous devriez voir les noms de plusieurs centaines de dimensions et de mesures chargés dans le *volet* Champs. Pour créer de réelles requêtes à partir de cette page, il vous suffit de sélectionner les dimensions et les mesures que vous voulez pour votre requête, puis de les glisser-déposer sur la page. Voici une explication plus détaillée, avec un exemple simple :

1. Sélectionnez la visualisation à utiliser dans le *volet Visualisations* . Une version vierge de cette visualisation doit apparaître sur la page. Dans le cadre de cet exemple, nous allons utiliser la *visualisation de table* .

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector3-resize.png)

2. Déterminez les dimensions et les mesures (ou symbole d’agrégation par leur nom) que vous souhaitez utiliser pour votre requête, puis sélectionnez-les manuellement et faites-les glisser vers la visualisation noire. Vous aussi, faites-les glisser vers le champ *Valeurs* sous les options de visualisation.

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Le tableau de bord de qualité des appels nécessite une mesure pour l’exécuter pour toute requête. L’échec de l’ajout d’une mesure à une requête entraîne l’échec de cette requête.

3. Sélectionnez ensuite les dimensions que vous voulez filtrer et faites-les glisser  vers les filtres de ce champ visuel dans *le volet Filtres*. Le connecteur Qualité d’appel Microsoft prend actuellement en charge le filtrage  de *base (sélection* de valeurs dans une liste de valeurs de dimension *possibles), le* filtrage avancé (spécifier manuellement les valeurs et les opérandes à filtrer, similaire au tableau de bord de qualité de l’appel) et filtrage de *date* relatif (disponible uniquement pour les dimensions Heure de fin et *Heure* de début). Le filtrage en fonction de *la première N n’est* pas pris en charge par le tableau de bord de qualité des appels.

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Les filtres sont uniquement pris en charge lorsqu’ils sont appliqués aux dimensions. Le filtrage des valeurs des mesures n’est pas pris en charge dans le tableau de bord qualité des appels.

4. Enfin, sélectionnez *l’onglet Format* dans le volet *Visualisations* pour mettre en forme votre requête.

    > [!NOTE]
    > Pour être exécutés, les requêtes Tableau de bord de qualité des appels nécessitent au moins une mesure. Si votre requête ne se charge pas, vérifiez que vous avez inclus une mesure dans la requête.

## <a name="creating-a-drillthrough-report"></a>Création d’un rapport d’drillthrough

[L’drillthrough Power BI](/power-bi/desktop-drillthrough) vous permet de créer des rapports concentrés que vous pouvez filtrer rapidement en utilisant les valeurs d’autres rapports comme contexte. Une fois que vous savez comment créer votre première requête avec le connecteur Qualité de l’appel de Microsoft, il est encore plus simple de créer une procédure d’drillthrough.

1. Créez une autre page pour l’état focus, puis ajoutez vos requêtes à cette page.

2. Sélectionnez la dimension à utiliser comme filtre *d’drillthrough* et faites-les glisser vers le champ d’drillthrough sous le volet *Visualisations* .

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector6-resize.png)

3. **Voilà\!** Toute autre requête sur une autre page qui utilise cette dimension peut désormais passer au travers de cette page, en appliquant automatiquement la valeur de dimension d’drillthrough en tant que filtre.

    ![Capture d’écran : Power BI lien.](media/CQD-power-bi-connector7-resize.png)

Contrairement au tableau de bord de qualité des appels, Power BI’drillthrough non séquentiel prend en charge l’drillthrough non séquentiel. Si une requête inclut la dimension nécessaire, elle peut passer à n’importe quelle autre page.

### <a name="best-practice"></a>Meilleure pratique

Les requêtes Connecteur de qualité d’appel Microsoft doivent être conçues avec la fonctionnalité d’drillthrough à l’esprit. Au lieu d’essayer de charger toutes les données en une seule opération, puis de vous lancer avec des filtres, commencez avec des requêtes plus larges et à faible cardinalité, puis descendez jusqu’aux requêtes de cardinalité élevée. Par exemple, lorsque vous tentez de diagnostiquer les sous-réseaux qui contribuent le plus aux problèmes de qualité, il est utile d’identifier les régions et pays qui contribuent au problème, puis d’descendre dans les sous-réseaux dans cette région ou ce pays. Les modèles de connecteur Qualité d’appel ont été conçus de cette manière afin de faire appel à un exemple.

## <a name="limitations"></a>Limites

Malgré l’utilisation d’Power BI, toutes les fonctionnalités de Power BI ne sont pas prise en charge par le connecteur Qualité des appels Microsoft, soit en raison de limitations du modèle de données du tableau de bord de qualité des appels, soit sur les connecteurs DirectQuery en général. La liste ci-dessous remarque certaines des limitations les plus importantes du Connecteur, mais cette liste ne doit pas être considérée comme exhaustive :

1. **Colonnes calculées :** En général, les connecteurs DirectQuery offrent une prise en charge limitée des colonnes calculées Power BI. Certaines colonnes calculées peuvent fonctionner avec le connecteur, que ces colonnes sont des exceptions. En règle générale, les colonnes calculées ne fonctionnent pas.

2. **Agrégation –** Le modèle de données Tableau de bord de qualité des appels est conçu sur un modèle de cube : les agrégations sont déjà prises en charge sous forme de mesures. La tentative d’ajouter manuellement des agrégations à différentes dimensions ou de modifier le type d’agrégation d’une mesure ne fonctionne pas avec le connecteur et entraîne généralement une erreur.

3. **Éléments visuels personnalisés –** Bien que le connecteur Qualité appel Microsoft fonctionne avec une plage de visuels personnalisés, nous ne pouvons pas garantir la compatibilité avec tous les visuels personnalisés. De nombreux visuels personnalisés s’appuient sur l’utilisation de colonnes calculées ou de données importées, lesquelles ne sont pas pris en charge par les connecteurs DirectQuery.

4. **Référencement aux données** mises en cache Power BI pour le moment ne prend pas en charge le référencement des données mises en cache à partir d’un connecteur DirectQuery de quelque manière que ce soit. Toute tentative de référence aux résultats d’une requête entraîne la génération d’une nouvelle requête.

5. **Filtrage relatif des données –** Est pris en charge dans le connecteur Qualité des appels Microsoft, mais  uniquement avec les dimensions Heure de début et *Heure de fin*. Bien que la dimension *Date* puisse être l’option la plus évidente pour le filtrage relatif des *dates, La* date n’est pas stockée en tant qu’objet d’heure de date et ne prend donc pas en charge le filtrage relatif des dates dans Power BI.

6. **Requêtes de mesure uniquement -** Ne sont pas pris en charge pour le moment dans le connecteur Qualité de l’appel Microsoft. Lors de la création d’une visualisation avec trois mesures ou plus sans dimensions, les données de colonne sont transposées. Pour éviter cela, incluez toujours au moins une dimension (par exemple, Month Year) dans vos visualisations. Ce problème devrait être résolu dans une prochaine version du connecteur Qualité des appels Microsoft pour Power BI.

7. **Cloud de la communauté du secteur public (Cloud de la communauté du secteur public) –** Pour les clients dans l’environnement Cloud de la communauté du secteur public, le connecteur Qualité d’appel Microsoft fonctionne lors de l’utilisation Power BI Desktop uniquement. Le connecteur Qualité d’appel Microsoft n’est actuellement pas compatible avec le service Power BI pour Cloud de la communauté du secteur public clients.

La plupart de ces problèmes sont soit des restrictions à la conception de connecteur DirectQuery dans Power BI, soit fondamentales pour la conception du modèle de données du graphique de qualité des qualités de la recherche de données.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>J’essaie d’utiliser la colonne Date comme un secteur Date. Dès que je convertisse le type de données de cette colonne en Date, je reçois cette erreur

> **Impossible de charger les** données pour ce visuel : Erreur OLE DB ou ODBC : [Expression.Error] Nous n’avons pas pu plier l’expression à la source de données. Essayez une expression plus simple.

Les slicers de date ne sont pas pris en charge avec le connecteur Qualité des appels Microsoft. Pour spécifier une plage de dates, appliquez deux filtres au rapport, en spécifiant une date inférieure et supérieure à celle-là.

Si les dates que vous voulez afficher sont récentes, vous pouvez également appliquer un filtre de date relatif pour afficher uniquement les données des derniers jours/semaines/mois.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Lorsque j’ajoute certaines dimensions à mes rapports, l’visuel renvoie immédiatement « Impossible de charger **les données pour ce visuel** ». La suppression de la dimension corrige l’aspect visuel. Qu’est-ce qui se passe ?

Il s’agit d’un problème connu dans le connecteur Qualité des appels Microsoft. Toute dimension exposée sous la forme d’un nombre entier apparaît dans Power BI sous la forme d’une colonne « agrégation » dans laquelle Power BI tente une action de synthèse par défaut (généralement « Somme »). Dans certains cas, ce comportement parvient à additioner les valeurs même si le résultat n’est pas utile, car la « somme » d’une dimension telle que le Second Canal WiFi est peu peu importe. Dans d’autres cas, cette action de synthèse échoue et entraîne des erreurs visuelles.

Pour contourner ce problème, commencez par supprimer la dimension de l’visuel. Sélectionnez la dimension dans la liste « Champs ». Accédez à l’onglet Outils de colonne dans le ruban, cliquez sur le menu déroulant « Synthèse » et sélectionnez Ne pas **synthétiser**. La dimension peut désormais être de nouveau ajoutée à l’visuel.


## <a name="error-codes"></a>Codes d’erreur

Étant donné que le connecteur Qualité d’appel de Microsoft pour Power BI est moins restreint que l’application du navigateur en termes de types de requêtes que vous pouvez créer, vous pouvez parfois rencontrer un certain nombre d’erreurs lors de la création de vos requêtes. Si vous recevez un message d’erreur du type « CQDError. RunQuery – Erreur d’exécution de requête », référencez la liste ci-dessous avec le numéro Type d’erreur fourni pour résoudre le problème possible avec la requête. Voici les codes de type d’erreur les plus courants que vous pouvez rencontrer avec le connecteur de tableau de Power BI de tableau de Power BI :

- **Type d’erreur 1 - Erreur de structure de requête :** Une erreur de structure de requête est généralement provoquée par l’échec du connecteur à créer une requête correctement mise en forme. Cela se produit la plupart du temps lors de l’utilisation de fonctionnalités non prévues, comme spécifié dans les limitations ci-dessus. Vérifiez que vous n’utilisez pas de colonne calculée ou d’éléments visuels personnalisés pour cette requête.

  - **Type d’erreur 2 - Erreur de bâtiment de requête :** Une erreur de bâtiment de requête est due au fait que le connecteur Qualité de l’appel Microsoft n’a pas pu correctement l’une des requêtes que vous essayez de créer. Cela se produit la plupart du temps lors de l’utilisation de fonctionnalités non prévues, comme spécifié dans les limitations ci-dessus. Vérifiez que vous n’utilisez pas de colonne calculée ou d’éléments visuels personnalisés pour cette requête.

  - **Type d’erreur 5 - Délai d’exécution :** La requête a atteint le temps d’exécuter maximal avant le minutage. Essayez d’ajouter d’autres filtres à la requête afin de limiter son étendue. Pour y parvenir, il est souvent plus efficace d’affiner la plage de données.

  - **Type d’erreur 7 - Aucune erreur de mesure :** Les requêtes Tableau de bord de qualité des appels nécessitent une mesure pour fonctionner. Vérifiez que votre requête inclut la mesure. Les mesures dans le connecteur Qualité de l’appel Microsoft sont notées par le symbole d’agrégation (somme) avant leur nom.

Si vous rencontrez des erreurs supplémentaires en dehors de cette étendue, informez l’équipe du tableau de bord de qualité des appels afin que nous pouvons vous aider à résoudre le problème et à mettre à jour la documentation le cas échéant.

## <a name="footnotes"></a>Notes de bas de page

**<sup>1</sup>** Certains processus et applications (par exemple, OneDrive) peuvent entraîner la modification du dossier racine Documents ; assurez-vous que le répertoire *Power BI Desktop\\ Custom Connectors* est placé dans le dossier Documents du dossier racine actuel.

**<sup>2 Les</sup>** informations d’identification que vous utilisez pour le tableau  de bord de qualité des appels ne doivent pas nécessairement être les mêmes que pour vous connecter à l’application Power BI Desktop vous-même.

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quand le connecteur Power BI sera-t-il mis à jour à partir de l’état « Bêta » ?

Malgré la balise Bêta, le connecteur Microsoft Call Quality (Beta) pour Power BI est la première version « finale » du connecteur et a officiellement été signé par l’équipe Power BI pour refléter ce qui s’est produit. Lors de la version initiale du connecteur, l’équipe Power BI n’a pas pu assurer le support et la certification générale, mais était néanmoins prête à en confirmer la sécurité, l’authenticité et les fonctionnalités générales du connecteur Qualité d’appel Microsoft. À l’avenir, nous envisageons d’investir dans le connecteur Qualité des appels Microsoft Power BI prochainement.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Pourquoi le connecteur semble-t-il plus lent par rapport au tableau de bord de qualité des appels dans le navigateur ? Que puis-je faire pour améliorer les performances ?

Les performances des requêtes des différents modèles sont en fait identiques tant dans le navigateur que dans le connecteur.  Comme toute autre application autonome, elle ajoute Power BI son authentification et son temps de rendu à nos performances. Par ailleurs, la différence vient du nombre de requêtes simultanées en cours d’exécuter. Étant donné que la version dans le navigateur du tableau de bord de qualité des appels avait moins d’options de visualisation bien développées et de visualisation de la densité d’informations, la plupart de nos rapports étaient limités au chargement de 2 à 3 requêtes à la fois. En revanche, les modèles de connecteur affichent souvent plus de 20 requêtes simultanées. Si vous souhaitez créer des rapports qui sont tout aussi réactifs que ceux que vous utilisiez, essayez de créer des rapports qui ne comptent pas plus de 2 à 3 requêtes par onglet.

Pour plus d’informations, voir les articles suivants :

- [Guide d’optimisation des Power BI](/power-bi/guidance/power-bi-optimization)
- [Conseils sur les modèles DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Je constate que j’exécute régulièrement la limite de 10 000 lignes lors de l’exécution de requêtes. Comment obtenir le connecteur pour renvoyer plus de 10 000 lignes ?

La limite de 10 000 lignes est en fait spécifiée à l’extrémité de l’API. Elle est conçue pour améliorer de manière significative les performances et réduire le risque d’erreurs d’exécution des requêtes résultant de conditions de mémoire réduite.

Au lieu d’essayer d’augmenter le nombre de lignes des résultats, il est préférable de restructurer vos rapports en fonction des meilleures pratiques de connexion. Les modèles que nous avons inclus sont conçus pour montrer ces meilleures pratiques. Si possible, commencez par regarder vos KPIs à l’aide de dimensions plus larges et de faible cardinalité, telles que Mois, Année, Date, Région, Pays, etc. À partir de là, vous pouvez descendre dans les dimensions de plus en plus grande cardinalité. Les rapports d’aide et de Location-Enhanced fournissent de bons exemples de ce flux de travail d’drill down.



## <a name="related-topics"></a>Sujets associés

[Utiliser Power BI pour analyser les données du CQD à des Teams](CQD-Power-BI-query-templates.md)
