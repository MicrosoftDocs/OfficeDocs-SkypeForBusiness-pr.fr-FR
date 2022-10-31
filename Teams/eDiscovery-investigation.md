---
title: Mener une investigation eDiscovery du contenu
description: Découvrez ce qu’il faut faire lorsque vous avez besoin d’effectuer une découverte électronique, par exemple lorsque vous devez soumettre toutes les informations stockées électroniquement pour des procédures judiciaires.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- ediscovery
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9bca2e40263bdbce65a64bf0da2d5864941fc46
ms.sourcegitcommit: 57616ad45eaa8be7f78dd0126d324c8777c5a367
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68792793"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams

Les grandes entreprises sont souvent exposées à des procédures judiciaires à haute peine qui exigent la soumission de toutes les informations stockées par voie électronique (ESI). Le contenu de Microsoft Teams peut être recherché et utilisé pendant les enquêtes eDiscovery.

## <a name="overview"></a>Vue d’ensemble

Toutes les conversations microsoft Teams 1:1 ou de groupe sont journalisé dans les boîtes aux lettres des utilisateurs respectifs. Tous les messages de canal standard sont journalisé dans la boîte aux lettres de groupe représentant l’équipe. Les fichiers chargés dans des canaux standard sont couverts par la fonctionnalité eDiscovery pour SharePoint Online et OneDrive Entreprise.

La découverte électronique des messages et des fichiers dans [les canaux privés](private-channels.md) fonctionne différemment des canaux standard. Pour plus d’informations, consultez [eDiscovery des canaux privés](#ediscovery-of-private-and-shared-channels).

Tout le contenu Teams n’est pas eDiscoverable. Le tableau suivant présente les types de contenu que vous pouvez rechercher à l’aide des outils Microsoft eDiscovery :

|**Type de contenu**|**Notes**|
|:---------------|:--------|
|Enregistrements audio||
|Contenu de la carte|Pour plus d’informations, [consultez Rechercher du contenu de carte](#search-for-card-content) .|
|Liens de conversation||
|Messages de conversation|Cela inclut le contenu des canaux Teams standard, des conversations 1:1, des conversations de groupe 1:N et des conversations avec des participants utilisateur invités.|
|Extraits de code||
|Messages modifiés|Si l’utilisateur est en attente, les versions précédentes des messages modifiés sont également conservées.|
|Emojis, GIF et autocollants||
|Images incorporées||
|Composants de boucle|Le contenu d’un composant de boucle est enregistré dans un fichier .fluid stocké dans le compte OneDrive Entreprise de l’utilisateur qui envoie le composant de boucle. Cela signifie que vous devez inclure OneDrive comme source de données lors de la recherche de contenu dans des composants de boucle.|
|Conversations de messagerie instantanée de réunion||
|Métadonnées de réunion<sup>1</sup>||
|Nom du canal||
|Citations|Le contenu entre guillemets peut faire l’objet d’une recherche. Toutefois, les résultats de la recherche n’indiquent pas que le contenu a été cité.|
|Réactions (telles que des j’aime, des cœurs et d’autres réactions)|Les réactions sont prises en charge pour tous les clients commerciaux après le 1er juin 2022. Les réactions antérieures à cette date ne sont pas disponibles pour eDiscovery. La prise en charge du cloud pour le secteur public est prévue. Il n’y a pas d’appui juridique pour les réactions.|
|Objet||
|Tables||
|Clip vidéo Teams (TVC)|Recherchez TVC avec le mot clé « Video-Clip » et « save as » un fichier .mp4 pour chaque pièce jointe TVC en cliquant avec le bouton droit sur l’aperçu (la recherche par mot clé sera disponible en octobre 2022). Les données TVC sont détectables dans les [ensembles de révision](/microsoft-365/compliance/add-data-to-review-set) eDiscovery.

<a name="teams-metadata"></a><sup>1</sup> Les métadonnées de réunion (et d’appel) incluent les éléments suivants :

- Heure de début et de fin de la réunion, et durée
- Participer à une réunion et quitter des événements pour chaque participant
- Appels/jointures VOIP
- Jointures anonymes
- Jointures d’utilisateur fédérées
- Jointures d’utilisateurs invités

Voici un exemple de conversation entre participants pendant une réunion.

![Conversation entre les participants dans Teams.](media/MeetingIMConversations.png)

Voici un exemple de copie de conformité de la même conversation de conversation consultée dans un outil eDiscovery.

![Conversation entre les participants dans les résultats de recherche eDiscovery.](media/MeetingImConversation2.png)

Voici un exemple de métadonnées de réunion.

![Métadonnées de réunion de la copie de conformité.](media/conversationOption3.png)

Pour plus d’informations sur la conduite d’une investigation eDiscovery, consultez [Prise en main d’eDiscovery (Standard).](/microsoft-365/compliance/get-started-core-ediscovery)

Les données Microsoft Teams s’affichent sous forme de messagerie instantanée ou de conversations dans la sortie d’exportation Excel eDiscovery. Vous pouvez ouvrir le `.pst` fichier dans Outlook pour afficher ces messages après les avoir exportés.

Lorsque vous affichez le fichier .pst de l’équipe, toutes les conversations se trouvent dans le dossier Conversation d’équipe sous Historique des conversations. Le titre du message contient le nom de l’équipe et le nom du canal. Par exemple, l’image ci-dessous montre un message de Bob qui a envoyé un message sur le canal standard Project 7 de l’équipe Manufacturing Specs.

![Capture d’écran d’un dossier De conversation d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Les conversations privées dans la boîte aux lettres d’un utilisateur sont stockées dans le dossier Conversation d’équipe sous Historique des conversations.

## <a name="ediscovery-of-private-and-shared-channels"></a>eDiscovery des canaux privés et partagés

Les copies de conformité des messages dans les canaux privés et partagés sont envoyées à différentes boîtes aux lettres en fonction du type de canal. Cela signifie que vous devez rechercher différents emplacements de boîte aux lettres en fonction du type de canal dont un utilisateur est membre.

- **Canaux privés**. Les copies de conformité sont envoyées à la boîte aux lettres de tous les membres du canal privé. Cela signifie que vous devez effectuer une recherche dans la boîte aux lettres de l’utilisateur lors de la recherche de contenu dans les messages de canal privé.

- **Canaux partagés**. Les copies de conformité sont envoyées à une boîte aux lettres système associée à l’équipe parente. Étant donné que Teams ne prend pas en charge la recherche eDiscovery d’une boîte aux lettres système unique pour un canal partagé, vous devez rechercher dans la boîte aux lettres l’équipe parente (en sélectionnant le nom de la boîte aux lettres d’équipe) lors de la recherche de contenu de message dans des canaux partagés.

Chaque canal privé et partagé possède son propre site SharePoint distinct du site d’équipe parent. Cela signifie que les fichiers dans les canaux privés et partagés sont stockés dans son propre site et gérés indépendamment de l’équipe parente. Cela signifie que vous devez identifier et rechercher le site spécifique associé à un canal lors de la recherche de contenu dans des fichiers et des pièces jointes de message de canal.

Utilisez les sections suivantes pour identifier le canal privé ou partagé à inclure dans votre recherche eDiscovery.

### <a name="identifying-the-members-of-a-private-channel"></a>Identification des membres d’un canal privé

Utilisez la procédure décrite dans cette section pour identifier les membres d’un canal privé afin de pouvoir utiliser les outils eDiscovery pour rechercher dans la boîte aux lettres du membre du contenu dans les messages de canal privé.

Avant d’effectuer ces étapes, vérifiez que la [dernière version du module PowerShell Teams](teams-powershell-overview.md) est installée.

1. Exécutez la commande suivante pour obtenir l’ID de groupe de l’équipe qui contient les canaux partagés que vous souhaitez rechercher.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Exécutez l’applet **de commande Get-Team** sans aucun paramètre pour afficher la liste de tous les teams de votre organisation. La liste contient l’ID de groupe et displayName pour chaque équipe.

2. Exécutez la commande suivante pour obtenir la liste des canaux privés dans l’équipe parente. Utilisez l’ID de groupe pour l’équipe que vous avez obtenue à l’étape 1.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Exécutez la commande suivante pour obtenir la liste des propriétaires de canaux privés et des membres d’un canal privé spécifique.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Incluez les boîtes aux lettres des propriétaires et des membres d’un canal privé dans le cadre de votre [requête de recherche eDiscovery dans eDiscovery (Standard)](/microsoft-365/compliance/search-for-content-in-core-ediscovery) ou lors de l’identification [et de la collecte du contenu de consignataire dans eDiscovery (Premium)](/microsoft-365/compliance/add-custodians-to-case) .

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identification du site SharePoint pour les canaux privés et partagés

Comme expliqué précédemment, les fichiers partagés dans des canaux privés et partagés (et les fichiers joints aux messages de canal) sont stockés dans la collection de sites associée au canal. Utilisez la procédure de cette section pour identifier l’URL du site associé à un canal privé ou partagé spécifique. Vous pouvez ensuite utiliser les outils eDiscovery pour rechercher du contenu dans le site.

Avant d’effectuer ces étapes, [installez SharePoint Online Management Shell et connectez-vous à SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Si vous le souhaitez, exécutez la commande suivante pour obtenir la liste de toutes les collections de sites SharePoint associées aux canaux partagés dans l’équipe parente.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > La convention de nommage de l’URL d’un site associé à des canaux privés et partagés est `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Par exemple, l’URL du canal partagé nommé « Partner Collaboration », qui se trouve dans l’équipe parente « Engineer Team » de l’organisation Contoso est `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`.

2. Exécutez les commandes PowerShell suivantes pour afficher l’URL de tous les sites SharePoint associés aux canaux privés et partagés de votre organisation. La sortie du script inclut également l’ID de groupe de l’équipe parente, dont vous avez besoin pour exécuter les commandes à l’étape 3.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > Les sites SharePoint pour les canaux privés créés avant le 28 juin 2021 utilisent la valeur `"TEAMCHANNEL#0"` pour l’ID de modèle personnalisé. Pour afficher les canaux privés créés après cette date, utilisez la valeur `"TEAMCHANNEL#1"` lors de l’exécution des deux scripts précédents. Les canaux partagés utilisent uniquement la valeur de `"TEAMCHANNEL#1"`.

3. Pour chaque équipe parente, exécutez les commandes PowerShell suivantes pour identifier les sites de canal privé et partagé, où `$groupID` est l’ID de groupe de l’équipe parente.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. Incluez le site associé à un canal privé ou partagé dans le cadre de votre [requête de recherche eDiscovery dans eDiscovery (Standard)](/microsoft-365/compliance/search-for-content-in-core-ediscovery) ou lors de [l’identification et de la collecte du contenu de consignataire dans eDiscovery (Premium)](/microsoft-365/compliance/add-custodians-to-case).

## <a name="search-for-content-for-guest-users"></a>Rechercher du contenu pour les utilisateurs invités

Vous pouvez utiliser les outils eDiscovery pour rechercher du contenu Teams lié aux utilisateurs invités de votre organisation. Le contenu de conversation Teams associé à un utilisateur invité est conservé dans un emplacement de stockage basé sur le cloud et peut être recherché à l’aide d’eDiscovery. Cela inclut la recherche de contenu dans les conversations de conversation 1:1 et 1:N dans lesquelles un utilisateur invité est un participant avec d’autres utilisateurs de votre organisation. Vous pouvez également rechercher des messages de canal privé dans lesquels un utilisateur invité est un participant et rechercher du contenu dans les conversations *de conversation invité:invité* où les seuls participants sont des utilisateurs invités.

Pour rechercher du contenu pour les utilisateurs invités :

1. Connectez-vous à Azure AD PowerShell. Pour obtenir des instructions, consultez la section « Se connecter avec Azure Active Directory PowerShell » dans [Se connecter à Microsoft 365 avec PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Veillez à effectuer les étapes 1 et 2 de l’article précédent.

2. Une fois que vous vous êtes connecté à Azure AD PowerShell, exécutez la commande suivante pour afficher le nom d’utilisateur principal (UPN) de tous les utilisateurs invités de votre organisation. Vous devez utiliser l’UPN de l’utilisateur invité lorsque vous créez la recherche à l’étape 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Au lieu d’afficher une liste de noms d’utilisateur principal sur l’écran de l’ordinateur, vous pouvez rediriger la sortie de la commande vers un fichier texte. Pour ce faire, `> filename.txt` ajoutez à la commande précédente. Le fichier texte avec les noms d’utilisateur principal est enregistré dans le dossier actif.

3. Dans une autre fenêtre Windows PowerShell, connectez-vous à Sécurité & Compliance Center PowerShell. Pour obtenir des instructions, consultez [Se connecter à Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell). Vous pouvez vous connecter avec ou sans l’authentification multifacteur.

4. Créez une recherche de contenu qui recherche tout le contenu (tel que les messages de conversation et les messages électroniques) dans lequel l’utilisateur invité spécifié était un participant en exécutant la commande suivante.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Par exemple, pour rechercher du contenu associé à l’utilisateur invité Sara Davis, vous devez exécuter la commande suivante.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Pour plus d’informations sur l’utilisation de PowerShell pour créer des recherches de contenu, consultez [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Exécutez la commande suivante pour démarrer la recherche de contenu que vous avez créée à l’étape 4 :

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Accédez à [https://compliance.microsoft.com](https://compliance.microsoft.com) , puis cliquez sur **Afficher toute** > **la recherche de contenu**.

7. Dans la liste des recherches, sélectionnez la recherche que vous avez créée à l’étape 4 pour afficher la page de menu volant.

8. Dans la page de menu volant, vous pouvez effectuer les opérations suivantes :

   - Cliquez sur **Afficher les résultats** pour afficher les résultats de la recherche et afficher un aperçu du contenu.

   - En regard du champ **Requête** , cliquez sur **Modifier** pour modifier, puis réexécutez la recherche. Par exemple, vous pouvez ajouter une requête de recherche pour affiner les résultats.

   - Cliquez sur **Exporter les résultats** pour exporter et télécharger les résultats de la recherche.

## <a name="search-for-card-content"></a>Rechercher le contenu de la carte

Le contenu de carte généré par les applications dans les canaux Teams, les conversations 1:1 et les conversations 1xN est stocké dans des boîtes aux lettres et peut faire l’objet d’une recherche. Une *carte* est un conteneur d’interface utilisateur pour de courts éléments de contenu. Les cartes peuvent avoir plusieurs propriétés et pièces jointes, et peuvent inclure des boutons qui peuvent déclencher des actions de carte. Pour plus d’informations, consultez [Cartes](/microsoftteams/platform/task-modules-and-cards/what-are-cards).

Comme pour les autres contenus Teams, où le contenu de la carte est stocké est basé sur l’emplacement où la carte a été utilisée. Le contenu des cartes utilisées dans un canal Teams est stocké dans la boîte aux lettres de groupe Teams. Le contenu des cartes pour les conversations 1:1 et 1xN est stocké dans les boîtes aux lettres des participants à la conversation.

Pour rechercher du contenu de carte, vous pouvez utiliser les conditions de `kind:microsoftteams` recherche ou `itemclass:IPM.SkypeTeams.Message` . Lors de l’examen des résultats de la recherche, le contenu de carte généré par les bots dans un canal Teams a la propriété **Sender/Author** email as `<appname>@teams.microsoft.com`, où `appname` est le nom de l’application qui a généré le contenu de la carte. Si le contenu de la carte a été généré par un utilisateur, la valeur **expéditeur/auteur** identifie l’utilisateur.

Lors de l’affichage du contenu de carte dans les résultats de la recherche de contenu, le contenu s’affiche sous forme de pièce jointe au message. La pièce jointe est nommée `appname.html`, où `appname` est le nom de l’application qui a généré le contenu de la carte. Les captures d’écran suivantes montrent comment le contenu de carte (pour une application nommée Asana) apparaît dans Teams et dans les résultats d’une recherche.

### <a name="card-content-in-teams"></a>Contenu de carte dans Teams

![Contenu de la carte dans le message du canal Teams.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Contenu de la carte dans les résultats de la recherche

![Même contenu de carte dans les résultats d’une recherche de contenu.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Pour afficher des images à partir du contenu de carte dans les résultats de recherche à ce stade (comme les coches de la capture d’écran précédente), vous devez être connecté à Teams (à <https://teams.microsoft.com>) dans un autre onglet de la même session de navigateur que vous utilisez pour afficher les résultats de la recherche. Sinon, les espaces réservés d’image s’affichent.

## <a name="ediscovery-in-federated-and-non-federated-environments"></a>eDiscovery dans les environnements fédérés et non fédérés

Les administrateurs peuvent utiliser eDiscovery pour rechercher du contenu dans les messages de conversation dans une réunion Teams dans des environnements fédérés (appelés *accès externe*) et non fédérés (appelés *accès invité*) en fonction des restrictions suivantes :

- **Fédéré :** dans une réunion Teams avec des utilisateurs de votre organisation et des utilisateurs d’une organisation externe (qui ont un accès externe dans votre organisation), les administrateurs des deux organisations peuvent rechercher du contenu dans les messages de conversation de la réunion.

- **Non fédéré :** dans une réunion Teams avec des utilisateurs de votre organisation et des utilisateurs invités, seuls les administrateurs de l’organisation qui hébergent la réunion Teams peuvent rechercher du contenu dans les messages de conversation de la réunion.

## <a name="related-topics"></a>Rubriques connexes

- [Solutions Microsoft 365 eDiscovery](/microsoft-365/compliance/ediscovery)
- [Prise en main d’eDiscovery (Standard)](/microsoft-365/compliance/get-started-core-ediscovery)
- [Flux de travail Teams dans eDiscovery (Premium)](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
