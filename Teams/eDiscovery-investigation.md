---
title: Effectuer une enquête eDiscovery sur du contenu
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez ce que vous devez faire lorsque vous devez effectuer une eDiscovery, par exemple, lorsque vous devez envoyer toutes les informations stockées électroniquement pour les procédures légales.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a35afa53a8f94a5d0106e67d2f9f87eacfaca63
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974461"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams

Les grandes entreprises sont souvent exposées à de hautes procédures juridiques qui demandent l’envoi de toutes les informations stockées électroniquement (ESI). Microsoft Teams de contenu peut être recherché et utilisé pendant les enquêtes de découverte électronique.

## <a name="overview"></a>Vue d’ensemble

Toutes Microsoft Teams conversations en tête-à-tête ou de groupe sont journalées dans les boîtes aux lettres des utilisateurs respectifs. Tous les messages de canal standard sont journalés dans la boîte aux lettres du groupe représentant l’équipe. Les fichiers téléchargés dans les canaux standard sont couverts par la fonctionnalité eDiscovery pour SharePoint Online et OneDrive Entreprise.

La découverte électronique des messages et des fichiers dans des [](private-channels.md) canaux privés fonctionne différemment que dans les canaux standard. Pour en savoir plus, [voir eDiscovery des canaux privés](#ediscovery-of-private-channels).

Il n’est Teams contenu eDiscoverable. Le tableau suivant indique les types de contenu que vous pouvez rechercher à l’aide des outils de découverte électronique Microsoft :

| Type de contenu | eDiscoverable | Remarques |
|:--- | :--- |:--- |
|Enregistrements audio | Non | |
|Contenu de la carte|Oui|Pour [plus d’informations, voir](#search-for-card-content) Rechercher le contenu d’une carte.|
|Liens de conversation | Oui | |
|Messages de conversation | Oui |Cela inclut le contenu Teams, les conversations en tête-à-tête, les conversations de groupe 1:N et les conversations avec des participants invités.  |
|Extraits de code | Non | |
|Messages modifiés | Oui | Si l’utilisateur est en attente, les versions précédentes des messages modifiés sont également conservées. |
|Emojis, GIF et autocollants | Oui | |
|Notifications de flux | Non | |
|Images en ligne | Oui | |
|Composants de boucle| Oui|Le contenu d’un composant de boucle est enregistré dans un fichier .fluid stocké dans le compte OneDrive Entreprise de l’utilisateur qui envoie le composant de boucle. Cela signifie que vous devez inclure OneDrive source de données lors de la recherche de contenu dans des composants de boucle. |
|Conversations de réunion par messagerie instantanée | Oui | |
|Métadonnées de <sup>réunion1</sup> | Oui |  |
|Nom du canal | Oui | |
|Messages de canal privé | Oui | |
|Devis | Oui | Le contenu cité peut faire l’l’objectif d’une recherche. Toutefois, les résultats de la recherche n’indiquent pas que le contenu a été cité. |
|Réactions (par exemple, likes, cœurs et autres réactions) | Non | |
|Objet | Oui | |
|Tableaux | Oui | |
||||

<sup>1 Métadonnées</sup> de réunion (et d’appel) inclut les informations suivantes :

- Heure de début et de fin et durée de la réunion
- Participer à une réunion et quitter des événements pour chaque participant
- VoIP joins/calls
- Jointeurs anonymes
- Jointeurs utilisateur fédérés
- Guest user joins

  L’image montre un exemple de métadonnées de réunion.

  > [!div class="mx-imgBorder"]
  > ![Métadonnées de la réunion à partir de la copie de conformité.](media/conversationOption3.png)

Voici un exemple de conversation par messagerie instantanée entre des participants au cours de la réunion.

![Conversation entre les participants dans Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversation entre les participants dans les résultats de recherche eDiscovery.](media/MeetingImConversation2.png)

Pour plus d’informations sur la conduite d’une investigation eDiscovery, voir Commencer [avec la découverte électronique principale](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams données s’affichent sous la la mesure d’une messagerie instantanée ou de conversations Excel la sortie d’exportation eDiscovery. Vous pouvez ouvrir le fichier `.pst` dans Outlook pour afficher ces messages après les avoir exportés.

Lorsque vous affichez le fichier .pst pour l’équipe, toutes les conversations sont situées dans le dossier Conversation d’équipe sous Historique des conversations. Le titre du message contient le nom de l’équipe et le nom du canal. Par exemple, l’image ci-dessous montre un message d’Bob qui a envoyé un message au Project 7 standard de l’équipe Spécifications de fabrication.

![Capture d’écran d’un dossier Conversation d’équipe dans la boîte aux lettres d’un Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Les conversations privées dans la boîte aux lettres d’un utilisateur sont stockées dans le dossier Conversation d’équipe sous Historique des conversations.

## <a name="ediscovery-of-private-channels"></a>Découverte électronique de canaux privés

Les copies de conformité des messages envoyés dans un canal privé sont remises dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des copies de conformité sont formatés pour indiquer de quel canal privé elles proviennent.

Chaque canal privé possède son propre site SharePoint distinct du site d’équipe parent, les fichiers dans un canal privé sont gérés indépendamment de l’équipe parente.

Teams ne prend pas en charge la recherche eDiscovery pour un seul canal au sein d’une équipe, la recherche doit donc s’effectuer dans toute l’équipe. Pour effectuer une recherche eDiscovery de contenu dans un canal privé, recherchez dans l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure les messages).

Pour identifier les fichiers et messages d’un canal privé à inclure dans votre recherche eDiscovery, utilisez les étapes suivantes.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Inclure des fichiers de canal privé dans une recherche eDiscovery

Avant d’effectuer ces étapes, installez [SharePoint Online Management Shell et connectez-vous à SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Exécutez l’information suivante pour obtenir la liste de SharePoint collections de sites associées à des canaux privés de l’équipe.

    ```PowerShell
    Get-SPOSite
    ```

2. Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et à l’ID du groupe parent.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents, `$groupID` à savoir l’ID de groupe de l’équipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```
> [!NOTE]
> SharePoint sites pour les canaux privés créés après le 28 juin 2021 `teamchannel#1` utilisent la valeur de l’ID de modèle personnalisé. Par exemple, pour les canaux privés créés après cette date, utilisez la valeur `teamchannel#1` lors de l’exécution des deux scripts précédents.

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Inclure les messages de canal privé dans une recherche eDiscovery

Avant d’effectuer ces étapes, assurez-vous que vous avez installé la [dernière version Teams module PowerShell](teams-powershell-overview.md).

1. Exécutez la commande suivante pour obtenir l’ID de groupe de l’équipe qui contient les canaux privés que vous souhaitez rechercher.

   ```powershell
   Get-Team -MailNickName <mail alias of the associated Office 365 Group>
   ```

   > [!TIP]
   > Exécutez **la cmdlet Get-Team** sans aucun paramètre pour afficher la liste des Teams dans votre organisation. La liste contient l’ID de groupe et MailNickName pour chaque équipe.

2. Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe. Utilisez l’ID de groupe pour l’équipe obtenue à l’étape 1.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupId> -MembershipType Private
    ```

3. Exécutez la commande suivante pour obtenir la liste des propriétaires et membres d’un canal privé.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupId> -DisplayName "Engineering" 
    ```

4. Incluez les boîtes aux lettres de tous les propriétaires et membres de chaque canal privé dans l’équipe dans votre requête de recherche [eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery).

## <a name="search-for-content-for-guest-users"></a>Rechercher du contenu pour les utilisateurs invités

Vous pouvez utiliser les outils eDiscovery pour rechercher du contenu Teams associé aux utilisateurs invités de votre organisation. Teams contenu de conversation associé à un utilisateur invité est conservé dans un emplacement de stockage cloud et peut être recherché à l’aide de la découverte électronique. Cela inclut la recherche de contenu dans les conversations de conversation 1:1 et 1:N dans lesquelles un utilisateur invité est participant avec d’autres utilisateurs de votre organisation. Vous pouvez également rechercher des messages de canal privé dans lesquels un utilisateur invité est participant et rechercher du contenu dans les conversations invité *:* invité où seuls les participants sont des utilisateurs invités.

Pour rechercher du contenu pour les utilisateurs invités :

1. Connecter à Azure AD PowerShell. Pour obtenir des instructions, voir la section « Connecter avec la Azure Active Directory PowerShell » dans Connecter à [Microsoft 365 PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Veillez à effectuer les étapes 1 et 2 de la rubrique précédente.

2. Une fois connecté à Azure AD PowerShell, exécutez la commande suivante pour afficher le nom d’utilisateur principal (UPN) de tous les utilisateurs invités de votre organisation. Vous devez utiliser le nom d’utilisateur utilisateur (UPN) de l’utilisateur invité lorsque vous créez la recherche à l’étape 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Au lieu d’afficher une liste de noms d’utilisateur principaux sur l’écran d’ordinateur, vous pouvez rediriger la sortie de la commande vers un fichier texte. Pour ce faire, vous pouvez l’appending `> filename.txt` à la commande précédente. Le fichier texte avec les noms d’utilisateur principaux sera enregistré dans le dossier actuel.

3. Dans une autre fenêtre Windows PowerShell, connectez-vous au PowerShell & conformité du Centre de sécurité et conformité. Pour obtenir des instructions à ce [Connecter powerShell du Centre de conformité & sécurité](/powershell/exchange/connect-to-scc-powershell). Vous pouvez vous connecter avec ou sans utiliser l’authentification multifacteur.

4. Créez une recherche de contenu qui recherche tout le contenu (tels que les messages de conversation et les messages électroniques) dans lequel l’utilisateur invité spécifié était participant en exécutant la commande suivante.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Par exemple, pour rechercher le contenu associé à l’utilisateur invité Sara Monnais, vous devez exécuter la commande suivante.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Pour plus d’informations sur l’utilisation de PowerShell pour créer des recherches de contenu, voir [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Exécutez la commande suivante pour lancer la recherche de contenu que vous avez créée à l’étape 4 :

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Allez à [https://compliance.microsoft.com](https://compliance.microsoft.com), puis cliquez **sur Afficher la** >  **recherche allContent**.

7. Dans la liste des recherches, sélectionnez la recherche que vous avez créée à l’étape 4 pour afficher la page de survol.

8. Dans la page de survol, vous pouvez faire les choses suivantes :

   - Cliquez **sur Afficher les résultats** pour afficher les résultats de la recherche et afficher un aperçu du contenu.

   - À côté du **champ Requête** , cliquez sur **Modifier** pour modifier, puis réexécutez la recherche. Par exemple, vous pouvez ajouter une requête de recherche pour affiner les résultats.

   - Cliquez **sur Exporter les résultats** pour exporter et télécharger les résultats de recherche.

## <a name="search-for-card-content"></a>Rechercher le contenu d’une carte

Le contenu de la carte généré par les applications Teams, les conversations en deux temps et les conversations 1xN sont stockés dans des boîtes aux lettres et peuvent faire l’effet d’une recherche. Une *carte est* un conteneur d’interface utilisateur pour de courts éléments de contenu. Les cartes peuvent avoir plusieurs propriétés et pièces jointes, et peuvent inclure des boutons qui peuvent déclencher des actions de carte. Pour plus d’informations, voir [Cartes](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Comme les autres Teams, où le contenu de la carte est stocké est basé sur l’endroit où la carte a été utilisée. Le contenu des cartes utilisées dans un Teams est stocké dans la boîte aux lettres Teams groupe. Le contenu des cartes pour les conversations 1:1 et 1xN est stocké dans les boîtes aux lettres des participants à la conversation.

Pour rechercher du contenu de carte, vous pouvez utiliser les conditions `kind:microsoftteams` ou `itemclass:IPM.SkypeTeams.Message` les conditions de recherche. Lors de l’examen des résultats de la recherche, le contenu de la carte généré par des bots dans un canal Teams a la propriété de courrier Expéditeur **/** `<appname>@teams.microsoft.com``appname` Auteur, comme , où se trouve le nom de l’application qui a généré le contenu de la carte. Si le contenu de la carte a été généré par un utilisateur, la valeur **Expéditeur/Auteur** identifie l’utilisateur.

Lorsque vous affichez le contenu d’une carte dans les résultats de la recherche de contenu, celui-ci s’affiche en tant que pièce jointe du message. La pièce jointe s’appelle `appname.html`, à `appname` l’endroit où se trouve le nom de l’application qui a généré le contenu de la carte. Les captures d’écran suivantes montrent comment le contenu de la carte (pour une application nommée Asana) apparaît dans Teams résultats d’une recherche.

**Contenu de la carte dans Teams**

![Contenu de la carte Teams message de canal.](media/CardContentTeams.png)

**Contenu de la carte dans les résultats de recherche**
  
![Même contenu de carte dans les résultats d’une recherche de contenu.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Pour afficher des images à partir du contenu de la carte dans les résultats de recherche à ce moment-là (par exemple, les cocher dans la capture d’écran précédente), vous devez être inscrit à Teams (https://teams.microsoft.com)dans un autre onglet au cours de la session de navigateur que vous utilisez pour afficher les résultats de la recherche. Dans le cas contraire, les espaces pour images s’affichent.

## <a name="related-topics"></a>Sujets associés

- [Microsoft 365 solutions eDiscovery](/microsoft-365/compliance/ediscovery)
- [Commencer à travailler avec core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams flux de travail dans Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
