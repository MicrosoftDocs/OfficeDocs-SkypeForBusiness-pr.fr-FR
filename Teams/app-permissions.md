---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lehewe
description: Cette section explique quelles données et autorisations sont demandées par les applications de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb8a6b6785e3cc4bcbf65bceeb51bf650b63a830
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883065"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorisations d’applications Microsoft Teams et points à prendre en compte

Les applications Microsoft Teams permettent de regrouper une ou plusieurs fonctionnalités dans un _package d’applications_ qui peut être installé, mis à niveau et désinstallé. Ces fonctionnalités incluent les éléments suivants :

-   Bots
-   Extensions de messagerie
-   Onglets
-   Connecteurs

Les bots sont acceptés par les utilisateurs et gérés par le service informatique de vue stratégique. Cependant, pour la plupart d’entre eux, des autorisations d’applications et un profil de risque sont définis par les autorisations et les profils de risque des fonctionnalités qu'ils contiennent. Cet article est donc axé sur les autorisations et les éléments à prendre en compte au niveau des fonctionnalités.

Les autorisations répertoriées ci-dessous en majuscules, comme par exemple RECEIVE_MESSAGE et REPLYTO_MESSAGE, n’apparaissent pas partout dans la [documentation destinée aux développeurs Microsoft Teams](https://aka.ms/teamsdevdocs) ou les [autorisations de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Il ne s’agit que d’une description aux fins de cet article.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Utilisez les tableaux ci-dessous comme guide pour comprendre quelles autorisations sont demandées par les applications que vous examinez.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Recherchez l’application ou le service pour décider si vous souhaitez autoriser les utilisateurs au sein de votre organisation à y accéder. Par exemple, les bots envoient et reçoivent des messages des utilisateurs et - à l’exception des bots métier de l’entreprise - sont situés en dehors du périmètre de conformité. Par conséquent, une application qui inclut un bot nécessite ces autorisations et possède au minimum ce profil de risque. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Autorisations d’applications globales et points à prendre en compte

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Points à prendre en compte</th>
  </tr>
  <tr>
    <td valign="top">Aucun</td>
    <td valign="top">Aucun</td>
    <td valign="top">Une application doit divulguer les données qu’elle utilise et à quelle fin elles sont utilisées dans ses conditions d’utilisation et liens vers la politique de confidentialité.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots et extensions de messagerie

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Points à prendre en compte</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le bot peut recevoir des messages des utilisateurs et leur répondre.<sup>1</sup></li><li>POST_MESSAGE_USER. Lorsqu'un utilisateur a envoyé un message à un bot, le bot peut envoyer à l’utilisateur des messages directs (également appelés _messages proactifs_) à n’importe quel moment.</li><li>GET_CHANNEL_LIST. Les bots ajoutés à des équipes peuvent obtenir la liste des noms et des ID des canaux d’une équipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY. Lorsque cette autorisation est utilisée dans un canal, les bots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom, nom d’utilisateur principal (UPN), adresse e-mail) ; lorsqu’elle est utilisée dans une conversation privée ou de groupe, le bot peut accéder aux mêmes informations de ces utilisateurs.</li><li> POST_MESSAGE_TEAM. Cette autorisation permet aux bots d’envoyer des messages directs (proactifs) à n’importe quel membre de l’équipe à tout moment, même si l’utilisateur n’a jamais parlé au bot auparavant.</li><li>Les autorisations suivants ne sont pas des autorisations explicites, mai sont sous-entendues par RECEIVE_MESSAGE et REPLYTO_MESSAGE et l’étendue dans laquelle les bots peuvent être utilisés, déclarée dans le manifeste : <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Cette autorisation contrôle si un bot peut envoyer et recevoir des fichiers dans une conversation privée (pas encore pris en charge pour les conversations de groupe ou les canaux).</li></ul></td>
    <td valign="top"><ul><li>Les bots ont accès uniquement aux équipes dans lesquelles ils ont été ajoutés ou aux utilisateurs qui les ont installés.</li><li>Les bots ne reçoivent que les messages dans lesquels ils sont mentionnés de façon explicite par les utilisateurs. Ces données ne restent pas sur le réseau d’entreprise.</li><li>    Les bots ne peuvent répondre qu’aux conversations dans lesquelles ils sont mentionnés.</li><li>Lorsqu’un utilisateur a discuté avec un bot, si le bot stocke l’ID de cet utilisateur, il peut envoyer des messages à cet utilisateur à n’importe quel moment. </li><li>Il est théoriquement impossible que les messages des bots contiennent des liens vers des sites de hameçonnage ou de logiciels malveillants, mais les bots peuvent être bloqués par l’utilisateur, l’administrateur du client ou globalement par Microsoft. </li><li>Un bot peut récupérer (et peut stocker) les informations d’identité de base des membres de l’équipe à laquelle l’application a été ajoutée, ou des utilisateurs individuels dans des conversations privées ou de groupe. Pour obtenir des informations supplémentaires sur ces utilisateurs, le bot doit leur demander de se connecter à Azure Active Directory (Azure AD). </li><li>Les bots peuvent récupérer (et peuvent stocker) la liste des canaux d’une équipe. Ces données ne restent pas sur le réseau d’entreprise. </li><li>Lorsqu'un fichier est envoyé à un bot, il ne reste pas sur le réseau d’entreprise. L’envoi et la réception de fichiers nécessite l’approbation de l’utilisateur pour chaque fichier. </li><li>Pat défaut, les bots n’ont pas la possibilité d’agir pour le compte de l’utilisateur, mais les bots peuvent demander aux utilisateurs de se connecter et, dès que l’utilisateur est connecté, le bot disposera d’un jeton d’accès avec lequel il peut effectuer d’autres actions. Ce que sont ces autres actions exactement dépend du bot et de l’élément auquel l’utilisateur se connecte : un bot est une application Azure AD inscrite sur <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> et peut avoir son propre ensemble d’autorisations.</li><li>Les bots sont informés à chaque fois que des utilisateurs sont ajoutés ou supprimés d'une équipe.</li><li>Les bots ne voient pas les adresses IP des utilisateurs ni d’autres informations du référent. Toutes les informations proviennent de Microsoft. (Il existe une seule exception : si un bot met en œuvre sa propre expérience de connexion, l’interface utilisateur de connexion verra les adresses IP des utilisateurs et les informations du référent.)</li><li>Les extensions de messagerie, d’autre part, voient les adresses IP des utilisateurs et les informations du référent.</li><li>Les recommandations des applications (et notre processus d’examen AppSource) demandent de la discrétion lors de la publication de messages de conversation aux utilisateurs (via l’autorisation POST_MESSAGE_TEAM) pour des motifs valables. En cas d’abus, les utilisateurs peuvent bloquer le bot, les administrateurs du client peuvent bloquer l’application et Microsoft peut bloquer les bots de manière centrale si nécessaire.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Certains bots envoient seulement des messages (POST_MESSAGE_USER). Ils sont appelés des bots de « notification-seulement », mais le terme ne désigne pas ce qu’un bot est autorisé ou non à faire. Cela signifie que le bot ne souhaite pas révéler une expérience de conversation. Teams utilise ce champ pour désactiver une fonctionnalité dans l’interface utilisateur qui ne serait normalement pas activée ; ce que peut faire le bot n’est pas limité par rapport aux bots qui révèlent une expérience de conversation.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Actuellement dans la version préliminaire pour les développeurs.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Actuellement dans la version préliminaire pour les développeurs. Régi par la propriété booléenne <code>supportsFiles</code> sur l'objet bot dans le fichier manifest.json de l’application.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un bot a sa propre connexion, il y a une seconde expérience - différente - lors de la première connexion de l’utilisateur.</li><li>Actuellement, les autorisations Azure AD associées avec des fonctionnalités dans une application Teams (bot, onglet, connecteur ou extension de messagerie) sont complètement séparées des autorisations Teams répertoriées ici.</li></ul>


## <a name="tabs"></a>Onglets

Un onglet est un site Web au sein de Teams.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Points à prendre en compte</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Aucune (actuellement).</td>
    <td valign="top"><ul><li>Le profil de risque d’un onglet est presque identique à ce même site Web qui s’exécute dans un onglet de navigateur. </li><li>Un onglet obtient le contexte dans lequel il s’exécute, y compris le nom de connexion et le nom d’utilisateur principal de l’utilisateur actuel, l’ID d’objet Azure AD de l’utilisateur actuel, l’ID du groupe (équipe) Office 365, l’ID du client et les paramètres régionaux de l’utilisateur. Cependant, pour mapper ces ID dans les informations de l’utilisateur, l'onglet aurait besoin que l’utilisateur se connecte à Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Connecteurs

Un connecteur publie les messages dans un canal lorsque des événements dans un système externe se produisent.

  <table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Points à prendre en compte</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge les _messages exploitables_, qui permettent aux utilisateurs de publier des réponses ciblées dans le connecteur de messages, en ajoutant une réponse à une question GitHub ou en ajoutant une date à une carte Trello par exemple.</td>
    <td valign="top"><ul><li>Le système qui publie les messages du connecteur ne sait pas qui les publie ni qui les reçoit : aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, pas le client ; c’est Microsoft qui publie les messages dans le cana;).</li><li>Aucune donnée ne quitte le réseau d’entreprise lorsque les messages du connecteur sont publiés dans un canal.</li><li>Les connecteurs qui prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE) ne voient pas non plus l'adresse IP et les informations du référent. Ces informations sont envoyées à Microsoft puis routées vers les points de terminaison HTTP qui ont été enregistrés auparavant auprès de Microsoft dans le portail des connecteurs.</li><li>Chaque fois qu’un connecteur est configuré pour un canal, une URL unique pour cette instance du connecteur est créée. Si cette instance du connecteur est supprimée, l’URL ne peut plus être utilisée.</li><li>Les messages des connecteurs peuvent contenir des pièces jointes.</li><li>L’URL de l’instance du connecteur doit être traitée comme étant secrète/confidentielle : toutes les personnes qui ont cette URL peuvent publier dessus, comme une adresse e-mail. Il existe donc un risque de courrier indésirable ou de liens vers des sites de hameçonnage ou de logiciels malveillants. Si cela se produit, les propriétaires d’équipe peuvent supprimer l’instance du connecteur.</li><li>Si le service qui envoie les messages des connecteurs était compromis et commençait à envoyer des liens de spam/hameçonnage/logiciel malveillant, l’administrateur du client peut empêcher la création de nouvelles instances du connecteur et Microsoft peut les bloquer de manière centrale.</li></ul></td>
  </tr>
</table>

> [!Note]
> Il n’est pas possible actuellement de savoir quels connecteurs prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks sortants

Les _webhooks sortants_ sont créés à la volée par les propriétaires d’équipe ou les membres d’une équipe si le chargement indépendant est activé pour un client. Il ne s’agit pas de fonctionnalités des applications Teams ; ces informations sont incluses par souci d'exhaustivité.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Points à prendre en compte</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et leur répondre.</td>
    <td valign="top">Aucun</td>
    <td valign="top"><ul><li>Les webhooks sortants sont similaires aux bots mais ont moins de privilèges. Ils doivent être mentionnés explicitement, comme les bots.</li><li>Lorsqu’un webhook sortant est enregistré, une _clé secrète_ est générée, qui lui permet de vérifier que l’expéditeur est Microsoft Teams et pas une personne malveillante. Ce code secret doit rester secret ; toutes les personnes qui y ont accès peuvent emprunter l’identité Microsoft Teams. Si le code secret est compromis, le webhook sortant peut être supprimé puis créé à nouveau, et un nouveau code secret sera généré.</li><li>Bien qu'il soit possible de créer un webhook sortant qui ne valide pas le code secret, cela n’est pas recommandé.</li><li>Les webhooks sortants ne peuvent pas faire plus que recevoir et répondre à des messages : ils ne peuvent pas envoyer des messages de façon proactive, ils ne peuvent pas envoyer ni recevoir de fichiers, ils ne peuvent pas faire autre chose que ce que peuvent faire les bots excepté recevoir et répondre à des messages.</li></ul></td>
  </tr>
</table>