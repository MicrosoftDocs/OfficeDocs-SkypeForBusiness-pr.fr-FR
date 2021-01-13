---
title: Configurer votre hiérarchie de ciblage d’équipe
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Découvrez comment configurer une hiérarchie d’équipes dans votre organisation pour publier du contenu dans un ensemble important d’équipes.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 099ee82e5890e81b6fc89a5ffc1842d936e6ad1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806154"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurer votre hiérarchie de ciblage d’équipe

> **Cette fonctionnalité est actuellement en prévisualisation privée.**

Pour créer une hiérarchie d’équipes qui peut être utilisée par votre organisation pour publier du contenu dans un ensemble important d’équipes, vous devez configurer le schéma de ciblage d’équipe. Le schéma définit comment toutes les équipes de votre hiérarchie sont liées entre elles et les attributs qui peuvent être utilisés pour filtrer vos équipes. Après avoir créé le schéma, vous le chargez dans Teams et la hiérarchie est appliquée dans votre organisation. Une fois le schéma téléchargé, les applications du client Teams peuvent l’utiliser. 

> [!IMPORTANT]
> Vous ne verrez pas une hiérarchie d’équipes lorsque vous parcourez les équipes ou les canaux qu’elles intérieur. Pour voir la hiérarchie des équipes, vous devez utiliser une application qui la prend en charge. Pour la version initiale, seule l’application Tâches prend en charge les équipes hiérarchiques. Le reste de cet article décrit la configuration d’une hiérarchie d’équipe dans le contexte de la publication de tâches aux équipes de destinataires. Avant de configurer la hiérarchie de ciblage d’équipe, consultez l’application Gérer les tâches pour votre organisation dans [Teams](manage-tasks-app.md) pour une vue d’ensemble de la publication de tâches.

Voici un exemple de la manière dont la hiérarchie est représentée dans l’application Tâches dans Teams. Une fois qu’une liste de tâches est créée, les membres de l’équipe de publication peuvent sélectionner les équipes de destinataires à qui envoyer (publier) la liste de tâches. Lors de la sélection d’équipes, l’équipe de publication peut filtrer par hiérarchie, par attributs ou une combinaison des deux.<br>

![Capture d’écran de la publication de tâches](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planifier votre hiérarchie

Avant de créer le schéma qui définit votre hiérarchie, vous devez planifier et décider comment vous voulez mettre en forme votre organisation. Cela inclut la décision des groupes organisationnels qui doivent publier des tâches dans d’autres groupes. Chaque nœud de la hiérarchie représente un groupe de travail ou un groupe de groupes. Les nodes en bas de la hiérarchie (ceux qui n’ont pas d’enfants) sont des équipes qui peuvent recevoir des tâches tandis que les autres nodes (parents) sont des groupes organisationnels autorisés à publier des tâches vers le bas. Une équipe ne peut être représentée qu’une seule fois dans la hiérarchie.

Par exemple, dans la hiérarchie suivante, Recall, Retail Communications et HR peuvent publier des tâches sur chaque nœud inférieur (équipe) dans la hiérarchie, tandis que la zone Nord Est ne peut publier que les tâches dans les équipes du Store de New York et du Store de York. Cette hiérarchie permet aux groupes Rappel, Communications au détail et RH de publier des tâches qui s’appliquent à l’ensemble de l’entreprise, telles que des informations sur les avantages ou des messages du PDG. La zone Nord Est peut publier des tâches, telles que la planification du personnel, les informations météorologiques, etc., uniquement dans les équipes du New York Store et du Store de York.

![Exemple hiérarchique d’équipe](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Créer votre hiérarchie

Le schéma qui définit votre hiérarchie est basé sur un fichier de valeurs séparées par des virgules (CSV). Chaque ligne du fichier CSV correspond à un nœud au sein de la hiérarchie des équipes. Chaque ligne contient des informations qui nomment le nœud au sein de la hiérarchie, la lie éventuellement à une équipe et inclut des attributs qui peuvent être utilisés pour filtrer les équipes dans les applications qui la supportent.

Vous pouvez également définir des compartiments, qui sont des catégories que l’équipe de publication peut utiliser pour organiser le contenu envoyé aux équipes de destinataires afin de leur faciliter l’affichage, le tri et la concentration sur le contenu pertinent.

### <a name="add-required-columns"></a>Ajouter des colonnes requises

Le fichier CSV doit contenir les trois colonnes suivantes, dans l’ordre suivant, en commençant par la première colonne. Un nœud doit être lié à une équipe pour recevoir des tâches. Pendant la prévisualisation privée, nous 2 000 nodes sont prise en charge. Au lancement, nous nous attendons à prendre en charge au moins 15 000 nodes par défaut. Nous prévoyons de travailler avec des clients afin d’élever cette limite pour les grandes organisations.

| Nom de colonne   | Obligatoire | Description   |
----------------|----------|---------------|
| TargetName    | Oui      | Il s’agit du nom du nœud. Le nom peut comporter jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9. Les noms de nœuds doivent être uniques. |
| ParentName    | Oui       | Il s’agit du nom du nœud parent. La valeur que vous spécifiez ici doit correspondre exactement à la valeur du champ TargetName du nœud parent. Si vous voulez ajouter plusieurs nœuds parents, séparez le nom de chaque nœud parent par un point-virgule (;). Vous pouvez ajouter jusqu’à 25 nœuds parents et chaque nom de nœud parent peut faire jusqu’à 2 500 caractères. Un nœud peut avoir plusieurs nœuds parents uniquement si les nœuds parents sont des nœuds racines.   <br><br>**IMPORTANT** Attention de ne pas créer de boucle dans laquelle un parent qui se trouve plus haut dans la hiérarchie fait référence à un nœud enfant plus bas dans la hiérarchie. Cela n’est pas pris en charge. |
| TeamId        | Oui, si l’équipe publie des tâches ou reçoit des tâches d’un nœud parent       | Il contient l’ID de l’équipe à qui vous voulez lier un nœud. Un nœud doit être lié à une équipe si elle se trouve au bas de la hiérarchie, si vous souhaitez que les utilisateurs puissent publier à partir de ce nœud, ou si vous voulez que les utilisateurs puissent voir la signalement de ce nœud et de ses descendants. Par exemple, si votre responsable d’Office de la région Ouest souhaite voir les rapports d’achèvement des tâches pour les nodes appartenant à cette région.<br><br>Si vous souhaitez ajouter un nœud uniquement dans le but de grouper d’autres nœuds dans la hiérarchie, vous n’avez pas besoin de lier ce nœud à une équipe et pouvez laisser ce champ vide. Vous pouvez lier chaque nœud à une seule équipe.<br>Pour obtenir l’ID d’une équipe à qui vous voulez lier un nœud, exécutez la commande PowerShell suivante `Get-Team | Export-Csv TeamList.csv` : Cette liste répertorie les équipes de votre organisation et inclut le nom et l’ID de chaque équipe. Recherchez le nom de l’équipe avec qui vous souhaitez établir un lien, puis copiez l’ID dans ce champ.|

### <a name="add-attribute-columns"></a>Ajouter des colonnes d’attribut

Après avoir ajouté les trois colonnes requises, vous pouvez ajouter des colonnes d’attribut facultatives. Ces attributs peuvent être utilisés pour filtrer les nodes afin de sélectionner plus facilement celles sur qui vous voulez publier des tâches. Il existe deux façons de définir vos attributs, selon que les valeurs pour cet attribut sont mutuellement exclusives.

|Méthodes d’ajout d’attributs|Description |Exemple  |
|---|---------|---------|
|Si les valeurs d’un attribut s’excluent mutuellement, le nom de colonne que vous spécifiez devient le nom de l’attribut.|Chaque ligne peut contenir une valeur pour cet attribut et chaque valeur peut comporter jusqu’à 100 caractères. L’ensemble des valeurs d’attribut que vous spécifiez dans la colonne de l’attribut s’affiche en tant que valeurs de filtre disponibles pour cet attribut dans les applications Teams qui utilisent la hiérarchie. Chaque colonne d’attribut peut avoir jusqu’à 50 valeurs uniques. |Vous souhaitez que les utilisateurs puissent filtrer les magasins par disposition. Les valeurs pour cet attribut s’excluent mutuellement, car un magasin ne peut avoir qu’une mise en page. <br><br>Pour ajouter un attribut au filtre des magasins par disposition, ajoutez une colonne nommée Disposition du Store. Dans cet exemple, les valeurs de l’attribut de disposition Store sont Compact, Standard et Grande.
|Si vous devez indiquer plusieurs valeurs pour un attribut et que ces valeurs ne sont pas mutuellement exclusives, utilisez le format **AttributeName:UniqueValue** pour les noms de colonnes. |Chaîne de texte avant les deux-points (:) devient le nom de l’attribut. Toutes les colonnes qui contiennent la même chaîne de texte avant les deux-:) sont regroupés en une section du menu de filtrage. Chacune des chaînes après les deux-points devient les valeurs de cette section.<br><br>Chaque ligne peut avoir une valeur de 0 (zéro) ou 1 pour cet attribut. Une valeur de 0 signifie que l’attribut ne s’applique pas au nœud et une valeur de 1 signifie que l’attribut s’applique à ce nœud.|Vous souhaitez que les utilisateurs puissent filtrer les magasins par service. Un magasin peut avoir plusieurs services et les valeurs pour cet attribut ne sont pas mutuellement exclusives.<br><br>Dans cet exemple, nous ajoutons Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sports: Attribute Columns. Les services deviennent le nom de l’attribut et les utilisateurs peuvent filtrer par les services Vêtements, Électronique, Aliments, Famille et Jardin et Articles de sport.|

Lorsque vous ajoutez une colonne d’attribut, gardez les éléments suivants à l’esprit :

- Nom de la colonne que vous spécifiez ou de la colonne que vous spécifiez avant les deux-points (:) devient le nom de l’attribut. Cette valeur sera affichée dans les applications Teams qui utilisent la hiérarchie.
- Le nom de la colonne peut comporter jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9, ainsi que des espaces. Les noms de colonne doivent être uniques.
- Au lancement, nous prévoyons d’autoriser 50 colonnes d’attributs.

### <a name="add-bucket-columns"></a>Ajouter des colonnes de compartiment

Vous pouvez ajouter des colonnes de compartiment pour créer des compartiments, qui sont des regroupements dans lesquels les tâches peuvent être organisées. Chaque compartiment possède sa propre colonne dans le fichier CSV. Les compartiments que vous créez sont mis à la disposition de l’équipe de publication. L’équipe de publication peut ensuite utiliser ces compartiments pour catégoriser les tâches pour les équipes de destinataires. Si un compartiment n’existe pas encore dans une équipe, il est créé à la demande lors de la publication des tâches.

En classant le travail de manière centralisée, l’équipe de publication peut pré-organiser la liste des tâches pour les dizaines, centaines ou milliers d’équipes de destinataires qui reçoivent la liste de tâches. Les équipes de destinataires peuvent ensuite trier et filtrer leurs tâches par compartiment pour se concentrer sur la zone la plus pertinente pour leur travail.

Lorsque vous ajoutez une colonne de compartiment, notez ce qui suit :

- Le nom de la colonne devient le nom du compartiment. Chaque compartiment que vous spécifiez s’affiche dans la liste compartiments des applications Teams qui utilisent la hiérarchie. Nous vous recommandons de ne pas inclure d’informations sensibles dans les noms de compartiment. Pour le moment, les équipes de publication ne peuvent pas supprimer un compartiment via la publication après sa création.
- Le nom de la colonne doit être précédé d’un hashtag (#). Il peut comporter jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9. Par exemple, #Operations et #Frozen Produits.
- Au lancement, nous nous attendons à prendre en charge 25 colonnes de compartiment. Nous prévoyons de travailler avec des clients afin d’augmenter cette limite pour les grandes organisations.

### <a name="example"></a>Exemple

Voici un exemple de fichier CSV de schéma qui serait créé pour prendre en charge la hiérarchie présentée dans l’image ci-dessus. Ce schéma contient les éléments suivants :

- Trois colonnes obligatoires `TargetName` `ParentName` nommées , et `TeamId`
- Trois colonnes d’attribut `Store layout` `Departments:Clothing` nommées , et `Departments:Foods`
- Trois colonnes de compartiment `Fresh Foods` `Frozen Foods` nommées , et `Womenswear`

`Store layout`L’attribut possède des valeurs qui `Compact` `Standard` comprennent , et `Large` . Les `Departments` colonnes d’attribut peuvent être définies sur une valeur de `0` (zéro) ou `1` . La `Store` disposition et les `Departments` attributs ne sont pas affichés dans l’image ci-dessus. Ils sont ajoutés ici pour vous aider à montrer comment les attributs peuvent être ajoutés aux entrées de nœud. Il en va de même pour les trois colonnes de compartiment.


| TargetName             | ParentName                      | TeamId                       | Disposition du Store|Services:Vêtements|Departments:Aliments|#Fresh Aliments|#Frozen Aliments|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Rappeler                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Communications         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| HR                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Bureau régional de l’Est   |                         |                                      |||||||
| Bureau régional de l’Ouest   |                         |                                      |||||||
| Zone Nord Est        | Bureau régional de l’Est    |                                      |||||||
| Zone Est du Sud        | Bureau régional de l’Est    |                                      |||||||
| New York Store         | Zone Nord Est         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Grande|1|1||||
| Le Store de Centre           | Zone Nord Est         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Magasin de Miami            | Zone Est du Sud         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Compacter|0|1||||
| Le Magasin de NewAsSais      | Zone Est du Sud         | 6be960b8-72af-4561-a343-9ac4711874eb |Compacter|0|1||||
| Seattle Store          | Bureau régional de l’Ouest    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Los Angeles Store      | Bureau régional de l’Ouest    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Grande|1|1||||

## <a name="apply-your-hierarchy"></a>Appliquer votre hiérarchie

> [!IMPORTANT]
> Pour effectuer cette étape, vous devez installer et utiliser le module d’aperçu public Teams PowerShell à partir de la [Galerie PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Pour savoir comment installer le module, voir [Installer Teams PowerShell.](teams-powershell-install.md)

Après avoir défini votre hiérarchie dans le fichier de schéma CSV, vous êtes prêt à la télécharger dans Teams. Pour ce faire, exécutez la commande suivante. Pour effectuer cette étape, vous devez être un administrateur global ou un administrateur de service Teams.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Supprimer votre hiérarchie

> [!IMPORTANT]
> Pour effectuer cette étape, vous devez installer et utiliser le module d’aperçu public Teams PowerShell à partir de la [Galerie PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Pour savoir comment installer le module, voir [Installer Teams PowerShell.](teams-powershell-install.md)

Si vous souhaitez désactiver  immédiatement l’onglet Listes publiées pour tous les utilisateurs de votre organisation, vous pouvez supprimer votre hiérarchie. Les utilisateurs n’ont pas accès à l’onglet **Listes** publiées ou à l’une des fonctionnalités de l’onglet.  Cela inclut la possibilité de créer des listes des tâches à publier, d’accéder à des brouillons de listes, de publier, de republier et de dupliquer des listes, et d’afficher les rapports. La suppression de la hiérarchie ne supprime pas les tâches publiées précédemment. Ces tâches restent disponibles pour les équipes de destinataires. 

Pour supprimer votre hiérarchie, exécutez la commande suivante. Vous devez être un administrateur pour effectuer cette étape. 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Vous recevez un message d’erreur lors du téléchargement de votre fichier CSV de schéma

Notez le message d’erreur qui doit inclure des informations de dépannage pour indiquer la raison pour laquelle le schéma n’a pas pu être téléchargé. Examinez et modifiez votre fichier CSV de schéma en fonction des informations du message d’erreur, puis réessayez.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Vous recevez un message d’erreur « Erreur : InvalidTeamId » lorsque vous téléchargez votre fichier CSV de schéma

Lorsque vous essayez de télécharger votre fichier CSV de schéma, vous obtenez le message d’erreur suivant :

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Vérifiez que vous utilisez le TeamId correct pour l’équipe dans votre fichier CSV de schéma. L’ID d’équipe doit être identique à l’ID de groupe du groupe Microsoft 365 qui a pour fond l’équipe. Vous pouvez rechercher l’ID de groupe de l’équipe dans le Centre d’administration Microsoft Teams. 

1. Dans le navigation gauche du Centre d’administration [Microsoft Teams,](https://admin.teams.microsoft.com/)allez dans **Teams**  >  **Gérer les équipes.**
2. Si la **colonne ID** de groupe n’est  pas affichée dans la table, sélectionnez Modifier les colonnes dans le coin supérieur droit du tableau, puis activer **l’ID de groupe.**
3. Recherchez l’équipe dans la liste, puis recherchez l’ID de groupe.

Assurez-vous que l’TeamId de votre fichier CSV de schéma correspond à l’ID de groupe qui s’affiche dans le Centre d’administration Microsoft Teams. 

## <a name="related-topics"></a>Sujets associés

- [Gérer l’application Tâches pour votre organisation dans Teams](manage-tasks-app.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
