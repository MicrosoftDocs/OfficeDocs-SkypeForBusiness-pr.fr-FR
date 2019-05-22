---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Cette section explique quelles données et autorisations sont demandées par les applications de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: b99507dcb37d86879bd495655da3d6f88a06f64a
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344732"
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
| ![Icône illustrant un point de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Utilisez le tableau ci-dessous pour connaître les autorisations que les applications que vous recherchez demandent.</li></ul> |
| ![Icône illustrant l’étape suivante](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Recherchez l’application ou le service proprement dit pour décider si vous voulez autoriser l’accès au sein de votre organisation. Par exemple, les robots envoient des messages à des utilisateurs et les reçoivent, à l’exception des robots d’entreprise, qui sont situés en dehors de la limite de conformité. Par conséquent, toute application incluant un bot nécessite ces autorisations et possède au moins ce profil de risques. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Autorisations et considérations générales pour les applications

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
  <tr>
    <td valign="top">Aucun</td>
    <td valign="top">Aucun</td>
    <td valign="top">Une application doit divulguer les données qu’elle utilise et quelles sont les données utilisées dans ses conditions générales d’utilisation et de politique de confidentialité.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Robots et extensions de messagerie

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le bot peut recevoir des messages des utilisateurs et y répondre. <sup>1</sup></li><li>POST_MESSAGE_USER. Dès qu’un utilisateur a envoyé un message à un bot, le bot peut lui envoyer les messages directs (également appelés <em>messages</em>proactifs) à tout moment.</li><li>GET_CHANNEL_LIST. Les robots ajoutés aux équipes peuvent obtenir une liste de noms et d’ID des canaux d’une équipe.</li></ul></td>
    <td valign="top"><ul><li>Stockage. Lorsque it& # 39; s est utilisé dans un canal, les robots app& # 39; s peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom, nom d’utilisateur principal [UPN], adresse de messagerie); Lorsque it& # 39; s est utilisé dans une conversation personnelle ou de groupe, le bot peut accéder aux mêmes informations pour ces utilisateurs.</li><li> POST_MESSAGE_TEAM. Permet aux robots d’app& # 39; s d’envoyer des messages directs à n’importe quel membre de l’équipe à tout moment, même si ceux-ci n’ont jamais parlé au bot auparavant.</li><li>Les éléments suivants ne sont pas des autorisations explicites, mais sont implicites par RECEIVE_MESSAGE et REPLYTO_MESSAGE, ainsi que les étendues dans lesquelles les robots peuvent être utilisés, et déclarés dans le manifeste: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. <sup>3</sup> contrôle si un bot peut envoyer et recevoir des fichiers dans la conversation personnelle (pas encore pris en charge pour les conversations ou canaux de groupe).</li></ul></td>
    <td valign="top"><ul><li>Les robots ont uniquement accès aux équipes auxquelles they& # 39; ai été ajoutées ou aux utilisateurs qui les ont installés.</li><li>Les robots reçoivent uniquement les messages au sein desquels they& # 39; explicitement mentionné par les utilisateurs. Ces données quittent le réseau d’entreprise.</li><li>    Les robots peuvent uniquement répondre aux conversations pour lesquelles they& # 39; re-mentionné.</li><li>Après que l’utilisateur a été conversé avec un bot, si ce dernier stocke ce numéro user& # 39; s, il peut envoyer à tout moment cet utilisateur directement. </li><li>Le message bot peut en théorie contenir des liens vers des sites de hameçonnage ou des logiciels malveillants, mais les robots peuvent être bloqués par l’utilisateur, l’administrateur client ou globalement par Microsoft. </li><li>Un bot peut récupérer (et peut stocker) des informations d’identité de base pour les membres de l’équipe auxquelles l’application a été ajoutée ou pour des utilisateurs individuels dans des discussions personnelles ou de groupe. Pour plus d’informations sur ces utilisateurs, le bot doit avoir besoin de se connecter à Azure Active Directory (Azure AD). </li><li>Les robots peuvent récupérer (et peut-être stocker) la liste de canaux dans une équipe; ces données quittent le réseau d’entreprise. </li><li>Lorsqu’un fichier est envoyé à un bot, le fichier quitte le réseau d’entreprise. Pour envoyer et recevoir des fichiers, l’utilisateur doit approuver chaque fichier. </li><li>Par défaut, les robots don& # 39; t peuvent agir de la part de l’utilisateur, mais les robots peuvent demander aux utilisateurs de se connecter; dès que l’utilisateur se connecte, le bot dispose d’un jeton d’accès permettant d’effectuer d’autres actions. Exactement ce que ces éléments supplémentaires dépendent du bot et de l’endroit où l’utilisateur se connecte: un bot est une application Azure <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> ad inscrite sur et peut avoir son propre jeu d’autorisations.</li><li>Les robots sont informés lorsque les utilisateurs sont ajoutés ou supprimés d’une équipe.</li><li>Bots don& # 39; t voir users& # 39; Adresses IP ou autres informations de renvoi. Toutes les informations proviennent de Microsoft. (Il existe une seule exception: si un bot implémente son propre ouverture de connexion, l’interface utilisateur de connexion verra le users& # 39; Adresses IP et informations de renvoi.</li><li>En revanche, les extensions de messagerie, à l’inverse, apparaissent users& # 39; Adresses IP et informations de renvoi.</li><li>Recommandations en matière d’applications (et notre processus de vérification de AppSource) demander la validation de messages de discussion personnelle aux utilisateurs (via l’autorisation POST_MESSAGE_TEAM) pour des raisons valides. En cas d’abus, les utilisateurs peuvent bloquer le bot, les administrateurs de clients peuvent bloquer l’application et Microsoft peut bloquer les robots de manière centralisée, le cas échéant.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Certains robots envoient uniquement des messages (POST_MESSAGE_USER). They& # 39; vous avez &quot;de nouveau appelé&quot; uniquement les robots de notifications, mais le terme doesn& # 39; t fait référence à ce qu’un bot est autorisé ou qu’il n’est pas autorisé à faire, cela signifie que le bot doesn& # 39; t veut exposer une conversation. Teams utilise ce champ pour désactiver les fonctionnalités de l’interface utilisateur qui seraient en principe activées; le bot isn& # 39; t limité à ce que it& # 39; s est autorisé à faire comparé aux robots qui présentent une connaissance de conversation.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Pour le moment dans la version préliminaire du développeur.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Régie par la <code>supportsFiles</code> propriété booléenne de l’objet bot dans le fichier manifest. JSON de l’application.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Si un bot dispose de sa propre connexion, il y a une deuxième fonction de consentement pour la première fois que l’utilisateur se connecte.</li><li>Pour l’instant, les autorisations Azure AD associées à toutes les fonctionnalités à l’intérieur d’une application Teams (bot, onglet, connecteur ou extension de messagerie) sont entièrement distinctes des autorisations d’équipe répertoriées ici.</li></ul>


## <a name="tabs"></a>Onglets

Un onglet est un site Web qui s’exécute dans Teams.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Aucun (actuellement).</td>
    <td valign="top"><ul><li>Le profil de risque d’un onglet est presque identique au même site Web exécuté dans un onglet de navigateur. </li><li>Un objet Tab obtient également le contexte dans lequel it& # 39; s en cours d’exécution, y compris le nom de connexion et le nom d’utilisateur principal (UPN) de l’utilisateur actuel, l’ID d’objet Azure AD pour l’utilisateur actuel, l’ID du groupe Office 365 dans lequel il se trouve (s’il s’agit d’une équipe) , l’ID de locataire et l’emplacement actuel de l’utilisateur. Toutefois, pour mapper ces ID à des informations user& # 39; s, l’onglet doit permettre à l’utilisateur de se connecter à Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Lien

Un connecteur publie des messages vers un canal lorsque des événements dans un système externe se produisent.

  <table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge des <em>messages</em>interactifs, ce qui permet aux utilisateurs de publier des réponses ciblées au message du connecteur, par exemple en ajoutant une réponse à un problème de GitHub ou en ajoutant une date à une carte Trello.</td>
    <td valign="top"><ul><li>Le système qui publie les messages de connecteur doesn& # 39; l indique qui it& # 39; s ou qui reçoit les messages: aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, et non le locataire; Microsoft effectue le billet réel sur le canal.)</li><li>Aucune donnée ne quitte le réseau d’entreprise lorsque des messages de connecteur sont publiés dans un canal.</li><li>Connecteurs prenant en charge des messages interactifs (autorisation REPLYTO_CONNECTOR_MESSAGE) également don& # 39; t voir les informations d’adresse IP et de renvoi; ces informations sont envoyées à Microsoft, puis routées aux points de terminaison HTTP déjà enregistrés auprès de Microsoft dans le portail de connecteurs.</li><li>Chaque fois qu’un connecteur est configuré pour un canal, une URL unique est créée pour cette instance de connecteur. Si cette instance de connecteur est supprimée, l’URL ne peut plus être utilisée.</li><li>Messages de connecteur can& # 39; t contiennent des pièces jointes.</li><li>L’URL d’instance du connecteur doit être considérée comme secrète/confidentiel: toute personne disposant de cette URL peut la publier dans celle-ci, comme une adresse de messagerie. C’est la raison pour laquelle il n’y a donc pas de risques de courrier indésirable ou de liens vers des sites de hameçonnage. Si tel est le cas, les propriétaires d’équipe peuvent supprimer l’instance de connecteur.</li><li>Si le service qui envoie des messages de connecteur a été compromis et qu’ils commencent à envoyer des courriers indésirables/de hameçonnage/malveillants, un administrateur client peut empêcher la création d’instances de connecteur et Microsoft peut les bloquer de manière centralisée.</li></ul></td>
  </tr>
</table>

> [!Note]
> Il n’est pas possible actuellement de savoir quels connecteurs prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Raccordements Web sortants

__ Les Webhook sortants sont créés à la volée par les propriétaires d’équipe ou les membres de l’équipe si chargement indépendant est activé pour un client. Elles ne sont pas des fonctionnalités des applications Teams. ces informations sont disponibles à des fins d’exhaustivité.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et y répondre.</td>
    <td valign="top">Aucun</td>
    <td valign="top"><ul><li>Les raccordements Web sortants sont similaires aux robots, mais ils ont moins de privilèges. Elles doivent être mentionnées explicitement, comme les robots.</li><li>Lors de l’enregistrement d’un webhook sortant, une <em>clé secrète</em> est générée, ce qui permet au webhook sortant de vérifier que l’expéditeur est Microsoft teams plutôt qu’à un attaquant malveillant. Ce secret doit rester secret; toute personne qui y a accès peut emprunter l’identité de Microsoft Teams. Si la clé secrète est compromise, le webhook sortant peut être supprimé, recréé et un nouveau secret est généré.</li><li>Même si vous pouvez créer un webhook sortant qui doesn& # 39; t a-t-il it&, nous vous recommandons de le valider.</li><li>À l’instar de la réception et de la réponse aux messages, les webhook sortants can& # 39; t-en-un: les can& # 39; t envoient des messages de manière proactive, ils can& # 39; t envoyer ou recevoir des fichiers, ils can& # 39; t do contenus.</li></ul></td>
  </tr>
</table>
