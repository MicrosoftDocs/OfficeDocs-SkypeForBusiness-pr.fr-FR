---
title: Configurer la hiérarchie de ciblage de votre équipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Apprenez à configurer une hiérarchie d’équipe au sein de votre organisation pour publier le contenu dans un grand nombre d’équipes.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bb8133733f7230715753ecea0118fc635af446b
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159001"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurer la hiérarchie de ciblage de votre équipe

> **Cette fonctionnalité est actuellement en version préliminaire privée.**

Pour créer une hiérarchie d’équipes qui peuvent être utilisées par votre organisation pour publier du contenu dans un grand nombre d’équipes, vous devez configurer le schéma de ciblage de votre équipe. Le schéma définit le rapport entre toutes les équipes de votre hiérarchie et les attributs qui peuvent être utilisés pour filtrer vos équipes. Après avoir créé le schéma, vous le chargez dans teams et la hiérarchie est appliquée au sein de votre organisation. Après le chargement du schéma, les applications du client teams peuvent l’utiliser. 

> [!IMPORTANT]
> Vous ne verrez pas une hiérarchie d’équipes lorsque vous parcourez des équipes ou des canaux au sein de celles-ci. Pour afficher la hiérarchie des équipes, vous devez utiliser une application qui la prend en charge. Pour la version initiale, seule l’application tâches prend en charge les équipes hiérarchiques. Le reste de cet article décrit la configuration d’une hiérarchie d’équipe dans le cadre de la publication de tâches dans les équipes de destinataires. Avant de configurer la hiérarchie de ciblage de votre équipe, reportez-vous à [la rubrique gérer l’application tâches pour votre organisation dans teams](manage-tasks-app.md) pour obtenir une vue d’ensemble de la publication des tâches.

Voici un exemple du mode de représentation de la hiérarchie dans l’application tâches dans Teams. Après la création d’une liste de tâches, les membres de l’équipe de publication peuvent alors sélectionner les équipes destinataires vers lesquelles envoyer (publier) la liste de tâches. Lors de la sélection d’équipes, l’équipe de publication peut filtrer par hiérarchie, par attribut, ou à l’aide d’une combinaison des deux.<br>

![Capture d’écran de la publication de tâches](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planifier votre hiérarchie

Avant de créer le schéma qui définit votre hiérarchie, vous avez besoin d’une planification et de la manière dont vous souhaitez définir la forme de votre organisation. Pour cela, vous devez décider des groupes d’organisations qui doivent publier des tâches à d’autres groupes. Chaque nœud de la hiérarchie représente un groupe de travail ou un groupe de groupes. Les nœuds situés en bas de la hiérarchie (qui n’ont pas d’enfant) sont des équipes qui peuvent recevoir des tâches alors que d’autres nœuds (parents) sont des groupes d’organisation qui ont l’autorisation de publier les tâches vers le bas. Une équipe ne peut être représentée qu’une seule fois dans la hiérarchie.

Par exemple, dans la hiérarchie suivante, rappeler, revendeurs et ressources humaines peuvent publier des tâches sur chaque nœud inférieur (équipe) dans la hiérarchie, alors que la zone nord est peut uniquement publier des tâches dans les équipes du magasin de New York et de l’équipe de banque d’informations Boston. Cette hiérarchie permet aux utilisateurs de rappeler, de revendeurs et de ressources humaines de publier les tâches qui s’appliquent à l’ensemble de la société, telles que des informations sur les avantages ou les messages du PDG. La zone nord-est peut publier des tâches, telles que la planification du personnel, les informations météorologiques, etc.

![Exemple hiérarchique d’équipe](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Créer votre hiérarchie

Le schéma qui définit votre hiérarchie est basé sur un fichier de valeurs séparées par des virgules (CSV). Chaque ligne du fichier CSV correspond à un nœud au sein de la hiérarchie d’équipes. Chaque ligne contient des informations qui nomment le nœud au sein de la hiérarchie, éventuellement le lie à une équipe, ainsi que des attributs qui peuvent être utilisés pour filtrer les équipes dans les applications qui la prennent en charge.

Vous pouvez également définir des compartiments, qui sont des catégories que l’équipe de publication peut utiliser pour organiser le contenu envoyé aux équipes de destinataires afin de faciliter leur affichage, le tri et la mise au point de contenus pertinents.

### <a name="add-required-columns"></a>Ajouter des colonnes requises

Le fichier CSV doit contenir les trois colonnes suivantes, dans l’ordre suivant, en commençant par la première colonne. Un nœud doit être lié à une équipe pour pouvoir recevoir des tâches. Dans le cadre de la version d’évaluation privée, nous prenons en charge les nœuds 500. Au démarrage, nous attendons de prendre en charge au moins 2 000 nœuds par défaut. Nous prévoyons de travailler avec les clients pour élever cette limite pour les grandes organisations.

| Nom de la colonne   | Obligatoire | Description   |
----------------|----------|---------------|
| TargetName    | Oui      | Il s’agit du nom du nœud. Le nom peut contenir jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9. Les noms de nœud doivent être uniques. |
| ParentName    | Oui       | Il s’agit du nom du nœud parent. La valeur que vous spécifiez ici doit correspondre exactement à la valeur figurant dans le champ NomCible du nœud parent. Si vous souhaitez ajouter plusieurs nœuds parents, séparez chaque nom de nœud parent par un point-virgule (;). Vous pouvez ajouter jusqu’à 25 nœuds parents et chaque nom de nœud parent peut contenir jusqu’à 2500 caractères. Un nœud peut avoir plusieurs nœuds parents uniquement si les nœuds parents sont des nœuds racines.   <br><br>**Important** Veillez à ne pas créer une boucle dans laquelle un parent situé plus haut dans la hiérarchie fait référence à un nœud enfant inférieur dans la hiérarchie. Cette opération n’est pas prise en charge. |
| TeamID        | Oui, si l’équipe publie des tâches ou reçoit des tâches d’un nœud parent       | Il contient l’ID de l’équipe à laquelle vous voulez lier un nœud. Un nœud doit être lié à une équipe s’il se trouve en bas de votre hiérarchie, si vous voulez que les utilisateurs puissent publier à partir de ce nœud, ou si vous souhaitez que les utilisateurs puissent voir les rapports de ce nœud et de ses descendants. Par exemple, si votre responsable pour le Bureau de la région ouest souhaite voir le rapport d’achèvement des tâches pour les nœuds qui appartiennent à cette région.<br><br>Si vous souhaitez ajouter un nœud uniquement pour le regroupement d’autres nœuds dans la hiérarchie, il n’est pas nécessaire de lier ce nœud à une équipe et de laisser ce champ vide. Vous pouvez lier chaque nœud à une seule équipe.<br>Pour obtenir l’ID d’une équipe à laquelle vous voulez lier un nœud, exécutez la commande PowerShell suivante : `Get-Team | Export-Csv TeamList.csv`. Cette liste répertorie les équipes au sein de votre organisation et inclut le nom et l’ID de chaque équipe. Recherchez le nom de l’équipe vers laquelle vous voulez créer le lien, puis copiez l’ID dans ce champ.|

### <a name="add-attribute-columns"></a>Ajouter des colonnes d’attributs

Après avoir ajouté les trois colonnes obligatoires, vous pouvez ajouter des colonnes d’attributs facultatives. Ces attributs peuvent être utilisés pour filtrer des nœuds afin que vous puissiez sélectionner plus facilement celles auxquelles vous voulez publier des tâches. Il existe deux manières de définir vos attributs, selon que les valeurs de cet attribut sont mutuellement exclusives.

|Méthodes d’ajout d’attributs|Description |Exemple  |
|---|---------|---------|
|Si les valeurs d’un attribut sont mutuellement exclusives, le nom de la colonne que vous spécifiez devient le nom de l’attribut.|Chaque ligne peut contenir une valeur pour cet attribut et chaque valeur peut comporter jusqu’à 100 caractères. L’ensemble de valeurs d’attributs que vous spécifiez dans la colonne attribut sera affiché en tant que valeurs de filtre disponibles pour cet attribut dans les applications d’équipe qui utilisent la hiérarchie. Chaque colonne d’attribut peut contenir jusqu’à 50 valeurs uniques. |Vous voulez que les utilisateurs puissent filtrer les magasins par disposition. Les valeurs de cet attribut sont mutuellement exclusives, car un magasin ne peut avoir qu’une seule disposition. <br><br>Pour ajouter un attribut pour filtrer les magasins par disposition, ajoutez une colonne nommée disposition du magasin. Dans cet exemple, les valeurs pour l’attribut de disposition Store sont compactes, standard et grande.
|Si vous devez indiquer plusieurs valeurs pour un attribut et si les valeurs ne sont pas mutuellement exclusives, utilisez le format **AttributeName : UniqueValue** pour les noms de colonnes. |La chaîne de texte avant les deux-points ( :) devient le nom de l’attribut. Toutes les colonnes qui contiennent la même chaîne de texte avant les deux-points ( :) sont regroupés en une section dans le menu de filtrage. Chacune des chaînes figurant après le signe deux-points devient les valeurs de cette section.<br><br>Chaque ligne peut avoir une valeur de 0 (zéro) ou 1 pour cet attribut. La valeur 0 indique que l’attribut ne s’applique pas au nœud et qu’une valeur de 1 signifie que l’attribut s’applique à ce nœud.|Vous voulez que les utilisateurs puissent filtrer les magasins par service. Un Windows Store peut avoir plusieurs départements ; les valeurs de cet attribut ne sont donc pas mutuellement exclusives.<br><br>Dans cet exemple, nous ajoutons services : vêtements, services : Electronics, services : aliments, services : maison et jardin, services : Articles sportifs en tant que colonnes d’attributs. Services devient le nom de l’attribut et les utilisateurs peuvent filtrer sur la base de l’habillement, de l’électronique, des aliments, de la maison et du jardin, et des départements d’articles sportifs.|

Lorsque vous ajoutez une colonne attribut, gardez les points suivants à l’esprit :

- Le nom de la colonne que vous spécifiez ou le nom de la colonne que vous spécifiez avant le signe deux-points ( :) devient le nom de l’attribut. Cette valeur s’affichera dans les applications teams qui utilisent la hiérarchie.
- Le nom de la colonne peut comporter un maximum de 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9, et des espaces. Les noms de colonnes doivent être uniques.
- Au démarrage, nous envisageons d’autoriser les colonnes d’attributs 50.

### <a name="add-bucket-columns"></a>Ajouter des colonnes de compartiment

Vous pouvez ajouter des colonnes de type compartiment pour créer des compartiments, qui sont des regroupements dans lesquels les tâches peuvent être organisées. Chaque compartiment dispose de sa propre colonne dans le fichier CSV. Les compartiments que vous créez sont mis à la disposition des membres de l’équipe de publication. L’équipe de publication peut ensuite utiliser ces compartiments pour classer les tâches pour les équipes destinataires. S’il n’existe pas déjà un compartiment sur une équipe, les compartiments sont créés à la demande lorsque des tâches sont publiées.

Le classement d’un travail centralisé est centralisé, l’équipe de publication peut préorganiser la liste de tâches de tous les horaires, centaines ou milliers d’équipes de destination qui reçoivent la liste des tâches. Les équipes du destinataire peuvent ensuite trier et filtrer leurs tâches par compartiment pour se concentrer sur la zone la plus pertinente pour leur tâche.

Lorsque vous ajoutez une colonne de compartiment, notez ce qui suit :

- Le nom de la colonne devient le nom du compartiment. Chaque compartiment que vous spécifiez s’affiche dans la liste des compartiments des applications teams utilisant la hiérarchie. Nous vous recommandons de ne pas inclure d’informations sensibles dans les noms de compartiment. Pour l’instant, la publication d’équipes ne peut pas supprimer un compartiment via la publication après sa création.
- Le nom de la colonne doit être précédé d’un mot-dièse (#). Il peut y avoir un maximum de 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9. Par exemple, #Operations et des produits #Frozen.
- Au démarrage, nous attendons de prendre en charge 25 colonnes de compartiment. Nous prévoyons de travailler avec les clients afin d’augmenter cette limite pour les grandes organisations.

### <a name="example"></a>Exemple

Voici un exemple de fichier CSV de schéma qui sera créé pour prendre en charge la hiérarchie affichée dans l’image ci-dessus. Ce schéma contient les éléments suivants :

- Trois colonnes obligatoires `TargetName`nommées `ParentName`, et`TeamID`
- Trois colonnes d’attribut `Store layout`nommées, `Departments:Clothing`et`Departments:Foods`
- Trois colonnes de compartiment `Fresh Foods`nommées, `Frozen Foods`et`Womenswear`

L' `Store layout` attribut comporte des valeurs incluant `Compact`, `Standard`et `Large`. Les `Departments` colonnes d' `0` attribut peuvent être définies sur une valeur égale à (zéro `1`) ou. La `Store` disposition et `Departments` les attributs n’apparaissent pas dans l’image ci-dessus. Ils sont ajoutés ici pour vous permettre de montrer comment les attributs peuvent être ajoutés aux entrées de nœud. Le même vrai pour les trois colonnes de compartiment.


| TargetName             | ParentName                      | TeamID                       | Disposition du Windows Store|Services : vêtements|Services : aliments|#Fresh aliments|#Frozen aliments|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Oublier                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Communications         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| HR                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Bureau régional de l’est   |                         |                                      |||||||
| Bureau régional d’ouest   |                         |                                      |||||||
| Zone nord-est        | Bureau régional de l’est    |                                      |||||||
| Zone sud-est        | Bureau régional de l’est    |                                      |||||||
| Magasin de New York         | Zone nord-est         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Grande|1|1||||
| Magasin d’Boston           | Zone nord-est         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Magasin Miami            | Zone sud-est         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Boîtier|0,4|1||||
| Magasin de nouvelles Orléans      | Zone sud-est         | 6be960b8-72af-4561-A343-9ac4711874eb |Boîtier|0,4|1||||
| Boutique de Seattle          | Bureau régional d’ouest    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Boutique de Los Angeles      | Bureau régional d’ouest    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Grande|1|1||||

## <a name="apply-your-hierarchy"></a>Appliquer votre hiérarchie

> [!IMPORTANT]
> Pour effectuer cette étape, vous devez installer et utiliser la dernière version du module PowerShell teams dans la Galerie de tests PowerShell. Pour plus d’informations sur la procédure à suivre, voir [installer le dernier module PowerShell teams dans la Galerie de tests PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).

Après avoir défini votre hiérarchie dans le fichier CSV de schéma, vous pouvez la télécharger dans Teams. Pour cela, exécutez la commande suivante. Pour effectuer cette étape, vous devez être un administrateur général ou un administrateur de service Teams.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Supprimer votre hiérarchie

> [!IMPORTANT]
> Pour effectuer cette étape, vous devez installer et utiliser la dernière version du module PowerShell teams dans la Galerie de tests PowerShell. Pour plus d’informations sur la procédure à suivre, voir [installer le dernier module PowerShell teams dans la Galerie de tests PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).

Si vous voulez désactiver immédiatement l’onglet **listes publiées** pour tous les utilisateurs de votre organisation, vous pouvez supprimer votre hiérarchie. Les utilisateurs ne peuvent pas accéder à l’onglet **listes publiées** ou aux fonctionnalités de l’onglet.  Cela inclut la possibilité de créer de nouvelles listes de tâches pour publier, accéder aux listes à l’ébauche, publier, annuler la publication et les listes en double et afficher la création de rapports. La suppression de la hiérarchie n’entraîne pas la publication des tâches publiées précédemment. Ces tâches resteront accessibles aux équipes de destinataires. 

Pour supprimer votre hiérarchie, exécutez la commande suivante. Vous devez être administrateur pour effectuer cette étape. 

```powershell
Remove-TeamTargetingHierarchy
```

### <a name="teams-powershell-module"></a>Module PowerShell teams

#### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>Installer le dernier module PowerShell teams à partir de la Galerie de tests PowerShell

La dernière version publique disponible du module teams PowerShell (actuellement [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) ne prend pas en charge la gestion de la hiérarchie d’équipe. Suivez ces étapes pour installer la dernière version du module PowerShell Teams, avec la prise en charge de la hiérarchie d’équipe, à partir de la Galerie de tests PowerShell.

> [!NOTE]
> N’installez pas le module PowerShell teams à partir de la Galerie de tests PowerShell côte à côte avec une version du module dans la Galerie PowerShell publique. Procédez comme suit pour désinstaller d’abord le module PowerShell teams dans la Galerie PowerShell public, puis installez la dernière version du module à partir de la Galerie de tests PowerShell.

1. Fermez toutes les sessions PowerShell existantes.
2. Démarrez une nouvelle instance du module Windows PowerShell.
3. Pour désinstaller le module teams PowerShell de la Galerie public PowerShell, exécutez la commande suivante :

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Fermez toutes les sessions PowerShell existantes.
5. Démarrez de nouveau le module Windows PowerShell, puis exécutez la commande suivante pour inscrire la Galerie de tests PowerShell en tant que source de confiance :

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Pour installer le dernier module PowerShell teams à partir de la Galerie de tests PowerShell, exécutez la commande suivante :

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Effectuer une mise à jour vers la dernière version du module PowerShell teams à partir de la Galerie de tests PowerShell

Si vous avez déjà installé le module teams PowerShell à partir de la Galerie de tests PowerShell, procédez comme suit pour effectuer une mise à jour vers la dernière version.

1. Fermez toutes les sessions PowerShell existantes.
2. Démarrez une nouvelle instance du module Windows PowerShell.
3. Exécutez la commande suivante pour mettre à jour la version actuellement installée du module PowerShell teams à partir de la Galerie de tests PowerShell :

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>Vous recevez un message d’erreur lors du chargement de votre fichier de schéma

Prenez note du message d’erreur, car il devrait inclure des informations de dépannage pour indiquer la raison pour laquelle le schéma n’a pas pu être chargé. Examinez et modifiez votre fichier CSV de schéma en fonction des informations contenues dans le message d’erreur, puis réessayez.

## <a name="related-topics"></a>Voir aussi

- [Gérer l’application tâches pour votre organisation dans teams](manage-tasks-app.md)
