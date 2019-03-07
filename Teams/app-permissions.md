---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: lehewe
description: Cette section explique quelles données et autorisations sont demandées par les applications de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c7394690cc59ce56e22fcc94076d5a90800c850
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460291"
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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le bot peut recevoir des messages des utilisateurs et leur répondre.<sup>1</sup></li><li>POST_MESSAGE_USER. Lorsqu'un utilisateur a envoyé un message à un bot, le bot peut envoyer à l’utilisateur des messages directs (également appelés <em>messages proactifs</em>) à n’importe quel moment.</li><li>GET_CHANNEL_LIST. Les bots ajoutés à des équipes peuvent obtenir la liste des noms et des ID des canaux d’une équipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY. Lorsque it& #39 ; s est utilisé dans un canal, l’app& #39 ; robots s peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom de famille, nom d’utilisateur principal [UPN], adresse de messagerie) ; Lorsque it& #39 ; est utilisé dans un personnel ou la conversation de groupe, le robot peut accéder aux informations même pour ces utilisateurs.</li><li> POST_MESSAGE_TEAM. Permet à un app& #39 ; robots s pour envoyer des messages (proactives) directs à n’importe quel membre de l’équipe à tout moment, même si l’utilisateur n’a jamais parlé pour le composant WebBot avant.</li><li>Les autorisations suivants ne sont pas des autorisations explicites, mai sont sous-entendues par RECEIVE_MESSAGE et REPLYTO_MESSAGE et l’étendue dans laquelle les bots peuvent être utilisés, déclarée dans le manifeste : <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Cette autorisation contrôle si un bot peut envoyer et recevoir des fichiers dans une conversation privée (pas encore pris en charge pour les conversations de groupe ou les canaux).</li></ul></td>
    <td valign="top"><ul><li>Robots ont accès uniquement aux équipes qui they& #39 ; ve été ajoutés ou aux utilisateurs qui ont installé les.</li><li>Robots uniquement recevoir des messages dans les they& #39 ; re mentionné explicitement par les utilisateurs. Ces données ne restent pas sur le réseau d’entreprise.</li><li>    Robots peuvent répondre uniquement à des conversations dans les they& #39 ; re mentionné.</li><li>Après un utilisateur a conversed avec un robot, si le composant WebBot stocke cette user& #39 ; s ID, il peut envoyer à l’utilisateur des messages directs à tout moment. </li><li>Il est théoriquement impossible que les messages des bots contiennent des liens vers des sites de hameçonnage ou de logiciels malveillants, mais les bots peuvent être bloqués par l’utilisateur, l’administrateur du client ou globalement par Microsoft. </li><li>Un bot peut récupérer (et peut stocker) les informations d’identité de base des membres de l’équipe à laquelle l’application a été ajoutée, ou des utilisateurs individuels dans des conversations privées ou de groupe. Pour obtenir des informations supplémentaires sur ces utilisateurs, le bot doit leur demander de se connecter à Azure Active Directory (Azure AD). </li><li>Les bots peuvent récupérer (et peuvent stocker) la liste des canaux d’une équipe. Ces données ne restent pas sur le réseau d’entreprise. </li><li>Lorsqu'un fichier est envoyé à un bot, il ne reste pas sur le réseau d’entreprise. L’envoi et la réception de fichiers nécessite l’approbation de l’utilisateur pour chaque fichier. </li><li>Par défaut, les composants WebBot don& #39 ; t ont la possibilité d’agir au nom de l’utilisateur, mais robots peuvent demander aux utilisateurs de se connecter ; dès que l’utilisateur se connecte, le composant WebBot aura un jeton d’accès avec lequel il peut effectuer des opérations supplémentaires. Ce que sont ces autres actions exactement dépend du bot et de l’élément auquel l’utilisateur se connecte : un bot est une application Azure AD inscrite sur <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> et peut avoir son propre ensemble d’autorisations.</li><li>Les bots sont informés à chaque fois que des utilisateurs sont ajoutés ou supprimés d'une équipe.</li><li>Robots don& #39 ; t voir users& #39 ; Adresses IP ou autres informations du point d’accès. Toutes les informations proviennent de Microsoft. (Il existe une exception : si un robot implémente son propre expérience de connexion, l’interface utilisateur de connexion s’affiche users& #39 ; Adresses IP et les informations du point d’accès.)</li><li>Extensions de messagerie, voir quant à eux, users& #39 ; Adresses IP et les informations du point d’accès.</li><li>Les recommandations des applications (et notre processus d’examen AppSource) demandent de la discrétion lors de la publication de messages de conversation aux utilisateurs (via l’autorisation POST_MESSAGE_TEAM) pour des motifs valables. En cas d’abus, les utilisateurs peuvent bloquer le bot, les administrateurs du client peuvent bloquer l’application et Microsoft peut bloquer les bots de manière centrale si nécessaire.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Certains bots envoient seulement des messages (POST_MESSAGE_USER). They& #39 ; re appelée &quot;notification seule&quot; robots, mais la doesn& termes #39 ; t faire référence à un robot de rôle est autorisé ou non autorisé à faire, cela signifie que le robot de doesn& #39 ; t souhaitez exposer une expérience CONVERSATIONNELLE. Les équipes utilise ce champ pour désactiver la fonctionnalité dans l’interface utilisateur qui serait normalement activé ; le robot d’isn& #39 ; t restreint dans quel it& #39 ; s autorisés à effectuer par rapport aux composants WebBot qui expose une expérience CONVERSATIONNELLE.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Actuellement dans la version préliminaire pour les développeurs.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Régi par le <code>supportsFiles</code> propriété booléenne sur l’objet bot dans le fichier manifest.json pour l’application.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un robot possède sa propre connexion dans, il est une seconde — différents : expérience de consentement de l’utilisateur la première fois que l’utilisateur se connecte.</li><li>Actuellement, les autorisations d’Azure AD associées à une des fonctionnalités à l’intérieur d’une application d’équipes (robot, onglet, connecteur ou extension de messagerie) sont complètement séparées les autorisations équipes répertoriées ici.</li></ul>


## <a name="tabs"></a>Onglets

Un objet tab est un site Web en cours d’exécution à l’intérieur des équipes.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">None (actuellement).</td>
    <td valign="top"><ul><li>Le profil de risque d’un onglet est pratiquement identique à ce même site en cours d’exécution dans un onglet du navigateur. </li><li>Un onglet obtient également le contexte dans les it& #39 ; s en cours d’exécution, y compris le nom de connexion et le nom UPN de l’utilisateur actuel, l’objet AD Azure ID de l’utilisateur actuel, l’ID de l’Office 365 groupe dans lequel il réside (s’il s’agit d’une équipe) , l’ID de client et les paramètres régionaux de l’utilisateur. Cependant, pour mapper les ID sur un user& #39 ; informations s, l’onglet aurait pour qu’un utilisateur se connecter à Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Connecteurs

Un connecteur publie des messages sur un canal lorsque les événements se produisent dans un système externe.

  <table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge <em>des messages</em>, qui permettent aux utilisateurs de publier des réponses ciblées sur le message de connecteur, par exemple en ajoutant une réponse à un problème de référentiels ou une date pour une carte de Trello.</td>
    <td valign="top"><ul><li>Le système qui publie connecteur doesn& messages #39 ; t sait it& #39 ; s de validation ou qui reçoit les messages : aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, pas le client ; Microsoft effectue la publication sur le canal réelle.)</li><li>Aucune donnée ne quitte le réseau d’entreprise lors de la validation des messages du connecteur à un canal.</li><li>Les connecteurs qui prennent en charge des messages (autorisation REPLYTO_CONNECTOR_MESSAGE) également don& #39 ; t voir IP du point d’accès informations d’adresse et ; Ces informations sont envoyées à Microsoft et ensuite acheminées vers les points de terminaison HTTP qui ont été précédemment inscrit auprès de Microsoft dans le portail de connecteurs.</li><li>Chaque fois qu’un connecteur est configuré pour une chaîne, une URL unique pour cette instance de connecteur est créée. Si cette instance de connecteur est supprimée, l’URL peut ne plus être utilisée.</li><li>Connecteur messages can& #39 ; t contiennent des pièces jointes.</li><li>L’instance du connecteur URL doit être traitée comme une clé secrète/confidentielles : toute personne ayant que peut publier des URL, comme une adresse de messagerie. Par conséquent, there& #39 ; s risque de courrier indésirable ou des liens vers les sites de phishing ou un programme malveillant. Si qui était le cas, les propriétaires de l’équipe peuvent supprimer l’instance du connecteur.</li><li>Si le service qui envoie des messages du connecteur ont été plus sécurisé et commencer à envoyer des liens de courrier indésirable/hameçonnage/programmes malveillants, un administrateur de clients permettre empêcher la création des instances de connecteur d’et Microsoft les bloquer centralisée.</li></ul></td>
  </tr>
</table>

> [!Note]
> Il n’est pas actuellement possible de savoir quels connecteurs prennent en charge des messages (autorisation REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks sortant

_Webhooks sortant_ sont créés par les propriétaires de l’équipe ou les membres de l’équipe à la volée si chargement de version test est activé pour un client. Ils ne sont pas des fonctionnalités des applications d’équipes ; Cette information est incluse par souci d’intégralité.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et y répondre.</td>
    <td valign="top">Aucun</td>
    <td valign="top"><ul><li>Webhooks sortants sont similaires aux composants WebBot mais ont moins de privilèges. Elles doivent être explicitement mentionnées, à l’instar des robots.</li><li>Lorsqu’un webhook sortant est inscrit, une <em>clé secrète</em> est généré, qui permet la webhook sortant vérifier que l’expéditeur est Microsoft Teams par opposition à un utilisateur malveillant. Ce mot de passe doit rester secret ; toute personne ayant accès à celui-ci peut emprunter l’identité Teams Microsoft. Si la clé secrète est compromise, le webhook sortant peut être supprimé et recréé et une nouvelle clé secrète sera générée.</li><li>Bien qu’it& #39 ; s possible de créer un webhook sortant qui doesn& #39 ; t valider la clé secrète, il est recommandé par rapport à celui-ci.</li><li>Autre que la réception et répondre à des messages, sortant webhooks can& #39 ; t suffit : ils can& #39 ; t proactive envoyer des messages, qu’ils can& #39 ; t envoyer ou recevoir des fichiers, ils can& #39 ; pas à le faire quelque chose qui robots peuvent à l’exception de réception et répondez à messages.</li></ul></td>
  </tr>
</table>
