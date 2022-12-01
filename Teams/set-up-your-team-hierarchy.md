---
title: Configurer la hiérarchie de ciblage de votre équipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Découvrez comment configurer une hiérarchie d’équipe dans votre organisation pour publier du contenu dans un grand ensemble d’équipes.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 93b8b06238b0f6e15ab5fac5dcb0caeece819d9e
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198356"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurer la hiérarchie de ciblage de votre équipe

La configuration d’une hiérarchie de ciblage d’équipe permet à votre organisation de publier du contenu sur un grand nombre d’équipes. La hiérarchie de ciblage d’équipe définit la façon dont toutes les équipes de votre hiérarchie sont liées les unes aux autres, les utilisateurs qui peuvent publier des tâches et les équipes sur lesquelles les utilisateurs ont les autorisations de publier. Les fonctionnalités de publication sont désactivées pour tous les utilisateurs, sauf si une hiérarchie de ciblage d’équipe est configurée pour votre organisation. Pour configurer une hiérarchie de ciblage d’équipe, vous devez créer un fichier qui définit la hiérarchie, puis le charger dans Teams pour l’appliquer à votre organisation. Une fois le schéma chargé, les applications dans Teams peuvent l’utiliser.

> [!IMPORTANT]
> Pour la version initiale, seule l’application Tâches prend en charge les équipes hiérarchiques.  L’application d’une hiérarchie de ciblage d’équipe à votre organisation permet la [publication de tâches](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) dans l’application Tâches. Vous ne verrez pas de hiérarchie d’équipes dans d’autres zones de Microsoft Teams.

Voici un exemple de la façon dont la hiérarchie est représentée dans l’application Tâches dans Teams. Après la création d’une liste de tâches, les membres de l’équipe de publication peuvent sélectionner les équipes destinataires à qui envoyer (publier) la liste des tâches. Lors de la sélection d’équipes, l’équipe de publication peut filtrer par hiérarchie, par attributs ou une combinaison des deux.<br>

![Capture d’écran de la publication de tâches.](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologie

Les termes suivants sont importants lorsque vous naviguez dans les hiérarchies. Teams sera appelé **nœuds**.

* **Les nœuds racines** sont les nœuds les plus hauts de la hiérarchie. Dans l’exemple, Retail Communications est un nœud racine.
* **Les nœuds parents** et **les nœuds enfants** sont des termes qui représentent une relation entre deux nœuds connectés. Dans l’exemple, District 01 est un nœud enfant de la zone 1.
* Plusieurs niveaux d’enfants sont appelés **descendants**. District 01, Store 01, Store 03, Store 07, District 02 et District 03 sont tous des descendants de la Zone 1.
* Un nœud sans enfant est appelé **nœud feuille**. Ils se trouvent au bas d’une hiérarchie.
* **Les équipes destinataires** sont des équipes qui ont été sélectionnées pour recevoir un ensemble spécifique de contenu à publier. Il doit s’agir de nœuds feuilles.

## <a name="plan-your-hierarchy"></a>Planifier votre hiérarchie

Avant de créer le schéma qui définit votre hiérarchie, vous devez effectuer une planification et décider de la façon dont vous souhaitez mettre en forme votre organisation.  L’une des premières priorités consiste à choisir les groupes organisationnels qui doivent publier des tâches dans d’autres groupes. Chaque nœud de la hiérarchie représente un groupe de travail ou un groupe de groupes.

### <a name="permissions-to-publish"></a>Autorisations de publication

L’autorisation de publication varie selon qu’un utilisateur est membre d’une équipe de la hiérarchie, ainsi que de la relation de cette équipe ou de cet ensemble d’équipes avec d’autres équipes de la hiérarchie.

> [!NOTE]
> Le propriétaire d’une équipe dispose également d’autorisations de publication.

* Si un utilisateur est membre d’au moins une équipe qui a des descendants dans la hiérarchie, cet utilisateur peut publier sur ces descendants sans être membre de toutes les équipes sur lesquelles il souhaite publier.
* Si un utilisateur est membre d’une équipe au moins dans la hiérarchie, mais qu’il n’est pas membre d’une équipe avec des descendants dans la hiérarchie, cet utilisateur peut voir et recevoir du contenu publié de son organisation.
* Si un utilisateur n’est membre d’aucune équipe de la hiérarchie, il ne voit aucune fonctionnalité liée à la publication.

### <a name="guidelines"></a>Lignes directrices

* Il ne peut y avoir qu’un seul fichier de hiérarchie appliqué par organisation. Toutefois, vous pouvez inclure différentes parties de votre organisation en tant que hiérarchies distinctes de nœuds dans un même fichier. Par exemple, Contoso Pharmaceuticals a un nœud racine Pharmacie et un nœud racine Vente au détail. Les deux nœuds racines ont plusieurs lignes de descendants et il n’y a pas de chevauchement entre eux.
* Seuls les nœuds feuilles peuvent être des destinataires d’une publication. D’autres nœuds de la hiérarchie sont utiles pour sélectionner les destinataires d’une publication.
* Une équipe ne peut être représentée qu’une seule fois dans une hiérarchie.
* Une hiérarchie peut contenir jusqu’à 15 000 nœuds. Nous prévoyons de travailler avec les clients pour augmenter cette limite pour les grandes organisations.

### <a name="example-hierarchy"></a>Exemple de hiérarchie

Par exemple, dans la hiérarchie suivante, Rappel, Communications et RH peuvent publier des tâches sur chaque nœud inférieur (équipe) de la hiérarchie, mais zone nord-est peut uniquement publier des tâches dans les équipes du New York Store et du Boston Store. L’exemple de hiérarchie permet aux groupes Rappel, Communications et RH de publier des tâches qui s’appliquent à l’ensemble de l’entreprise, telles que les informations sur les avantages ou les messages du PDG. Zone Nord-Est peut publier des tâches telles que la planification du personnel, les informations météorologiques, etc., uniquement aux équipes du Magasin de New York et du Boston Store.

![Exemple hiérarchique d’équipe.](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Créer votre hiérarchie

> [!NOTE]
> Le reste de cet article traite de la configuration d’une hiérarchie d’équipe dans le contexte de la publication de tâches dans les équipes destinataires. Reportez-vous à [Gérer l’application Tâches pour votre organisation dans Teams](./manage-tasks-app.md) pour obtenir une vue d’ensemble de l’application Tâches, où la publication de tâches s’affiche lorsqu’elle est activée.

Le schéma qui définit votre hiérarchie est basé sur un fichier de valeurs séparées par des virgules (CSV). Le fichier doit être au format UTF-8. Chaque ligne du fichier CSV correspond à un nœud dans la hiérarchie des équipes. Chaque ligne contient des informations qui nomment le nœud dans la hiérarchie, le lie éventuellement à une équipe et inclut des attributs qui peuvent être utilisés pour filtrer les équipes dans les applications qui le prennent en charge.

Vous pouvez également définir **des compartiments**, qui sont des catégories que l’équipe de publication peut utiliser pour organiser le contenu envoyé aux équipes destinataires afin qu’elles puissent afficher, trier et se concentrer plus facilement sur le contenu pertinent.

### <a name="add-required-columns"></a>Ajouter les colonnes requises

Le fichier CSV doit contenir les trois colonnes suivantes, dans l’ordre suivant, en commençant à la première colonne. Un nœud doit être lié à une équipe pour qu’il puisse recevoir des tâches.

| Nom de la colonne   | Obligatoire | Description   |
----------------|----------|---------------|
| DisplayName    | Oui      | Ce champ est le nom du nœud. Le nom peut contenir jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9. Les noms de nœud doivent être uniques. |
| ParentName    | Oui       | Il s’agit du nom du nœud parent. La valeur que vous spécifiez ici doit correspondre exactement à la valeur du champ **DisplayName** du nœud parent. Si vous souhaitez ajouter plusieurs nœuds parents, séparez chaque nom de nœud parent par un point-virgule (;). Vous pouvez ajouter jusqu’à 25 nœuds parents, et chaque nom de nœud parent peut comporter jusqu’à 2 500 caractères. Un nœud peut avoir plusieurs nœuds parents uniquement si les nœuds parents sont des nœuds racines.   <br><br>**IMPORTANT** Veillez à ne pas créer de boucle où un parent plus haut dans la hiérarchie référence un nœud enfant inférieur dans la hiérarchie. Cela n’est pas pris en charge. |
| TeamId        | Oui, si l’équipe publie des tâches ou reçoit des tâches d’un nœud parent       | Il contient l’ID de l’équipe à laquelle vous souhaitez lier un nœud. Chaque nœud doit faire référence à une équipe unique, de sorte que chaque valeur TeamId ne peut apparaître qu’une seule fois dans le fichier de hiérarchie. Pour obtenir l’ID d’une équipe à laquelle vous souhaitez lier un nœud, exécutez la commande PowerShell suivante : `Get-Team | Export-Csv TeamList.csv`. Cette commande répertorie les équipes de votre organisation et inclut le nom et l’ID de chaque équipe. Recherchez le nom de l’équipe à lier, puis copiez l’ID dans ce champ.|

> [!NOTE]
> Si un nœud n’est pas un nœud racine ou un nœud feuille et que vous n’avez pas besoin que l’appartenance à l’équipe accorde les autorisations correspondantes pour la publication et la création de rapports, vous pouvez laisser teamId vide. Cette méthode peut être utilisée pour ajouter plus de granularité lors du choix des équipes de destinataires ou pour afficher les rapports d’achèvement sans avoir d’équipe correspondante.

### <a name="add-attribute-columns"></a>Ajouter des colonnes d’attribut

Après avoir ajouté les trois colonnes requises, vous pouvez ajouter des colonnes d’attribut facultatives. Ces attributs peuvent être utilisés pour filtrer les nœuds afin que vous puissiez sélectionner plus facilement ceux sur lesquels vous souhaitez publier des tâches. Il existe deux façons de définir vos attributs, selon que les valeurs de cet attribut s’excluent mutuellement.

|Méthodes d’ajout d’attributs|Description |Exemple  |
|---|---------|---------|
|Si les valeurs d’un attribut s’excluent mutuellement, le nom de colonne que vous spécifiez devient le nom de l’attribut.|Chaque ligne peut contenir une valeur pour cet attribut, et chaque colonne d’attribut peut avoir jusqu’à 50 valeurs uniques. Chaque valeur peut comporter jusqu’à 100 caractères. L’ensemble de valeurs d’attribut que vous spécifiez dans la colonne d’attribut s’affiche en tant que valeurs de filtre pour cet attribut lors de la sélection des équipes de destinataires à l’aide de la hiérarchie de ciblage d’équipe.|Vous souhaitez que les utilisateurs puissent filtrer les magasins par disposition. Les valeurs de cet attribut s’excluent mutuellement, car un magasin ne peut avoir qu’une seule disposition. <br><br>Pour ajouter un attribut aux magasins de filtres par disposition, ajoutez une colonne nommée Disposition du Magasin. Dans cet exemple, les valeurs de l’attribut de disposition Store sont Compact, Standard et Large.
|Si vous devez indiquer plusieurs valeurs pour un attribut et que les valeurs ne s’excluent pas mutuellement, utilisez le format **AttributeName:UniqueValue** pour les noms de colonne. <br><br>**IMPORTANT** Veillez à utiliser les deux-points uniquement en anglais (:) en tant que unicode n’est pas pris en charge en tant que délimiteur de colonne d’attribut. |Chaîne de texte avant le signe deux-points (:) devient le nom de l’attribut. Toutes les colonnes qui contiennent la même chaîne de texte avant les deux-points (:) sont regroupés dans une section du menu de filtrage. Chacune des chaînes après le signe deux-points devient les valeurs de cette section.<br><br>Chaque ligne peut avoir une valeur de 0 (zéro) ou 1 pour cet attribut. La valeur 0 signifie que l’attribut ne s’applique pas au nœud et que la valeur 1 signifie que l’attribut s’applique à ce nœud.|Vous souhaitez que les utilisateurs puissent filtrer les magasins par département. Un magasin peut avoir plusieurs services et donc les valeurs de cet attribut ne s’excluent pas mutuellement.<br><br>Dans cet exemple, nous ajoutons Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods en tant que colonnes d’attribut. Départements devient le nom de l’attribut et les utilisateurs peuvent filtrer par les départements Vêtements, Électronique, Aliments, Maison et Jardin et Articles de sport.|

Lorsque vous ajoutez une colonne d’attribut, gardez les points suivants à l’esprit :

* Nom de colonne que vous spécifiez ou nom de colonne que vous spécifiez avant les deux-points (:) devient le nom de l’attribut. Cette valeur s’affiche dans les applications Teams qui utilisent la hiérarchie.
* Vous pouvez avoir jusqu’à 50 colonnes d’attribut dans votre hiérarchie.
* Le nom de colonne peut contenir jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9, ainsi que des espaces. Les noms de colonnes doivent être uniques.

### <a name="add-bucket-columns"></a>Ajouter des colonnes de compartiment

Vous pouvez ajouter des colonnes de compartiment pour créer des compartiments, qui sont des regroupements dans lesquels les tâches peuvent être organisées. Chaque compartiment obtient sa propre colonne dans le fichier CSV. Les compartiments que vous créez sont mis à la disposition de l’équipe de publication. L’équipe de publication peut ensuite utiliser ces compartiments pour catégoriser les tâches des équipes destinataires. S’il n’existe pas encore de compartiment dans une équipe, les compartiments sont créés à la demande lors de la publication des tâches.

En catégorisant les éléments de travail une fois de manière centralisée, l’équipe de publication peut pré-organiser la liste des tâches pour toutes les dizaines, centaines ou milliers d’équipes destinataires qui reçoivent la liste des tâches. Les équipes destinataires peuvent ensuite trier et filtrer leurs tâches par compartiment pour se concentrer sur le domaine le plus pertinent pour leur travail.

Lorsque vous ajoutez une colonne de compartiment, notez les points suivants :

* Le nom de la colonne devient le nom du compartiment. Chaque compartiment que vous spécifiez apparaît dans la liste Compartiments des applications Teams qui utilisent la hiérarchie.
* Nous vous recommandons de ne pas inclure d’informations sensibles dans les noms de compartiments. Pour l’instant, les équipes de publication ne peuvent pas supprimer un compartiment par le biais de la publication après sa création.
* Le nom de la colonne doit être précédé d’un hashtag (#). Il peut contenir jusqu’à 100 caractères et contenir uniquement les caractères A-Z, a-z et 0-9. Par exemple, #Operations et #Frozen Goods.
* Une hiérarchie peut contenir jusqu’à 25 colonnes de compartiment. Nous prévoyons de travailler avec les clients pour augmenter cette limite pour les grandes organisations.

### <a name="example"></a>Exemple

Voici un exemple de fichier CSV de schéma qui serait créé pour prendre en charge la hiérarchie illustrée dans l’image précédente. Ce schéma contient les éléments suivants :

* Trois colonnes obligatoires nommées `TargetName`, `ParentName`et `TeamId`
* Trois colonnes d’attribut nommées `Store layout`, `Departments:Clothing`et `Departments:Foods`
* Trois colonnes de compartiment nommées `Fresh Foods`, `Frozen Foods`et `Women's Wear`

L’attribut `Store layout` a des valeurs qui incluent `Compact`, `Standard`et `Large`. Les `Departments` colonnes d’attribut peuvent être définies sur une valeur de `0` (zéro) ou `1`. La `Store` disposition et `Departments` les attributs ne sont pas affichés dans l’image ci-dessus. Ils sont ajoutés ici pour vous aider à montrer comment les attributs peuvent être ajoutés aux entrées de nœud. Il en va de même pour les trois colonnes de compartiment.

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>Appliquer votre hiérarchie

> [!NOTE]
> Pour effectuer cette étape, vous devez utiliser Microsoft applets de commande PowerShell Teams. Vous devez utiliser la version 4.6.0 ou ultérieure des applets de commande Microsoft Teams. Cette exigence s’applique également aux clients government Community Cloud (GCC).

Une fois que vous avez défini votre hiérarchie dans le fichier CSV de schéma, vous êtes prêt à la charger dans Teams. Pour ce faire, exécutez la commande suivante. Vous devez être administrateur général ou administrateur de service Teams pour effectuer cette étape.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Mettre à jour votre hiérarchie

Vous pouvez charger une nouvelle hiérarchie pour remplacer l’ancienne à l’aide de la même commande PowerShell que ci-dessus. Chaque fois que vous chargez une nouvelle hiérarchie, elle remplace la hiérarchie précédente.

### <a name="check-the-status-of-your-hierarchy"></a>Vérifier l’état de votre hiérarchie

Vous pouvez exécuter la commande suivante pour vérifier l’état du chargement de votre hiérarchie.

```powershell
Get-TeamTargetingHierarchyStatus
```

La commande retourne les champs suivants :

Champ|Description
-----|------------
Id | ID unique du chargement.
Statut | État du chargement. Les valeurs incluent **Démarrage**, **Validation**, **Réussite** et **Échec**
ErrorDetails | Détails en cas d’erreur de chargement. Pour plus d’informations sur les détails de l’erreur, consultez la section Résolution des problèmes. S’il n’y a pas d’erreur, ce champ est vide.
LastUpdatedAt | Horodatage et date de la dernière mise à jour du fichier.
LastModifiedBy | ID du dernier utilisateur qui a modifié le fichier.
FileName | Nom de fichier du fichier CSV.

## <a name="remove-your-hierarchy"></a>Supprimer votre hiérarchie

Si vous souhaitez désactiver immédiatement l’onglet **Listes publiées** pour tous les utilisateurs de votre organisation, vous pouvez supprimer votre hiérarchie. Les utilisateurs n’ont pas accès à l’onglet **Listes publiées** ou à l’une des fonctionnalités de l’onglet.  Cela inclut la possibilité de créer des listes de tâches pour publier, accéder à des brouillons de listes, publier, annuler la publication et dupliquer des listes, et afficher les rapports. La suppression de la hiérarchie n’annule pas la publication des tâches qui ont été publiées précédemment. Ces tâches resteront disponibles pour les équipes destinataires.

Pour supprimer votre hiérarchie, exécutez la commande suivante. Vous devez être administrateur pour effectuer cette étape.

```powershell
Remove-TeamTargetingHierarchy
```

Lors de la confirmation de la suppression, le message d’état affiche toujours le schéma précédent, bien que la tentative de suppression retourne une erreur indiquant que l’objet est null.

## <a name="create-a-sample-hierarchy"></a>Créer un exemple de hiérarchie

### <a name="install-the-teams-powershell-module"></a>Installer le module PowerShell Teams

> [!IMPORTANT]
> Pour effectuer cette étape, vous devez installer et utiliser le module PowerShell Teams à partir du [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/). Pour savoir comment installer le module, consultez [Installer Microsoft module PowerShell Teams](teams-powershell-install.md).

### <a name="sample-script"></a>Exemple de script

Le script suivant peut être utilisé pour créer les équipes et charger un fichier .csv dans votre locataire Microsoft Teams. Si vous avez une hiérarchie existante, ce script la remplace.

#### <a name="create-teams-for-a-simple-hierarchy"></a>Créer des équipes pour une hiérarchie simple

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Utiliser les données d’équipe pour créer une sortie séparée par des virgules (DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Enregistrer la sortie dans un fichier .csv dans le dossier **Téléchargements**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Charger la hiérarchie

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="how-to-view-error-details"></a>Comment afficher les détails de l’erreur

Vous pouvez exécuter la commande suivante pour comprendre ce qui provoque une erreur et retourner les détails de l’erreur.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Vous recevez un message d’erreur lorsque vous chargez votre fichier CSV de schéma

Notez le message d’erreur, car il doit inclure des informations de résolution des problèmes pour indiquer pourquoi le schéma n’a pas pu être chargé. Passez en revue et modifiez votre fichier CSV de schéma en fonction des informations contenues dans le message d’erreur, puis réessayez.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Vous recevez un message d’erreur « Erreur : InvalidTeamId » lorsque vous chargez votre fichier CSV de schéma

Lorsque vous essayez de charger votre fichier CSV de schéma, le message d’erreur suivant s’affiche :

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Vérifiez que vous utilisez le TeamId correct pour l’équipe dans votre fichier CSV de schéma. TeamId doit être identique à l’ID de groupe du groupe Microsoft 365 qui l’a soutenu. Vous pouvez rechercher l’ID de groupe de l’équipe dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du [centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/), accédez à **Teams** > **Gérer les équipes**.
2. Si la colonne **ID de groupe** n’est pas affichée dans la table, sélectionnez **Modifier les colonnes** dans le coin supérieur droit de la table, puis activez **l’ID de groupe**.
3. Recherchez l’équipe dans la liste, puis recherchez l’ID de groupe.

Assurez-vous que le TeamId dans votre fichier CSV de schéma correspond à l’ID de groupe affiché dans le centre d’administration Microsoft Teams.

## <a name="related-topics"></a>Rubriques connexes

* [Gérer l’application Tâches pour votre organisation dans Teams](manage-tasks-app.md)
* [Présentation de Teams PowerShell](teams-powershell-overview.md)
