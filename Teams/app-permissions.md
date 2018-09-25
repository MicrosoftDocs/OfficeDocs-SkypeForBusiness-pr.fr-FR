---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_PracticalGuidance
search.appverid: MET150
ms.reviewer: lehewe
description: Cette section explique quelles données et autorisations sont demandées par les applications de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 960f54f27b7019d15d287c637c7c58f73dfdef0f
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014186"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Autorisations d’applications Microsoft Teams et points à prendre en compte

Applications Microsoft Teams sont un moyen pour une ou plusieurs fonctionnalités dans un _package d’application_ qui peut être installé, mis à niveau et désinstallation d’agrégation. Les fonctionnalités sont les suivantes :

-   Bots
-   Extensions de messagerie
-   Onglets
-   Connecteurs

Les applications sont souhaitez par les utilisateurs et gérées par informatique du point de vue de la stratégie. Toutefois, pour l’essentiel, les autorisations et le profil de risque d’une application sont définies par les autorisations et les profils de risque des fonctions qu’elle contient. Par conséquent, cet article se concentre sur les autorisations et les considérations au niveau de la fonctionnalité.

Les autorisations répertoriées ci-dessous en majuscules, par exemple RECEIVE_MESSAGE et REPLYTO_MESSAGE, n’apparaissent pas n’importe où dans la [documentation du développeur Microsoft équipes](https://aka.ms/teamsdevdocs) ou les [autorisations pour Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Ils sont simplement une forme abrégée descriptive pour les besoins de cet article.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Utilisez les tableaux ci-dessous comme guide pour comprendre quelles autorisations sont demandées par les applications que vous examinez.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>L’application de recherche ou de service lui-même pour décider si vous souhaitez accorder l’accès au sein de votre organisation. Par exemple, robots envoyer et recevoir des messages des utilisateurs, et, à l’exception des robots de métier d’entreprise, ils se trouvent en dehors de la limite de la conformité. Par conséquent, n’importe quelle application qui inclut un robot requiert ces autorisations et a profil risque, au minimum. </li></ul>|

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le robot peut recevoir des messages des utilisateurs et y répondre. <sup>1</sup></li><li>POST_MESSAGE_USER. Un utilisateur a envoyé un message à un robot, le robot peut envoyer l’utilisateur directs messages (également appelées _messages proactives_) à tout moment.</li><li>GET_CHANNEL_LIST. Ajout aux équipes de robots peuvent obtenir une liste de noms et les ID des canaux dans une équipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTITÉ. Lorsqu’il est utilisé dans un canal, robots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom de famille, nom d’utilisateur principal [UPN], adresse de messagerie) ; Lorsqu’il est utilisé dans une conversation personnelle ou de groupe, le robot peut accéder aux informations même pour ces utilisateurs.</li><li> POST_MESSAGE_TEAM. Permet de robots d’une application envoyer des messages (proactives) directs à n’importe quel membre de l’équipe à tout moment, même si l’utilisateur n’a jamais parlé pour le composant WebBot avant.</li><li>Les autorisations suivants ne sont pas des autorisations explicites, mai sont sous-entendues par RECEIVE_MESSAGE et REPLYTO_MESSAGE et l’étendue dans laquelle les bots peuvent être utilisés, déclarée dans le manifeste : <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Cette autorisation contrôle si un bot peut envoyer et recevoir des fichiers dans une conversation privée (pas encore pris en charge pour les conversations de groupe ou les canaux).</li></ul></td>
    <td valign="top"><ul><li>Les bots ont accès uniquement aux équipes dans lesquelles ils ont été ajoutés ou aux utilisateurs qui les ont installés.</li><li>Robots recevoir uniquement des messages dans lequel elles sont mentionnées explicitement par les utilisateurs. Ces données quittent le réseau d’entreprise.</li><li>    Les bots ne peuvent répondre qu’aux conversations dans lesquelles ils sont mentionnés.</li><li>Lorsqu’un utilisateur a discuté avec un bot, si le bot stocke l’ID de cet utilisateur, il peut envoyer des messages à cet utilisateur à n’importe quel moment. </li><li>Il est théoriquement impossible que les messages des bots contiennent des liens vers des sites de hameçonnage ou de logiciels malveillants, mais les bots peuvent être bloqués par l’utilisateur, l’administrateur du client ou globalement par Microsoft. </li><li>Un robot peut récupérer (et peut stocker) les informations d’identité de base pour l’application a été ajoutée à des membres de l’équipe, ou pour des utilisateurs spécifiques à des conversations personnelles ou de groupe. Pour obtenir plus d’informations sur ces utilisateurs, le robot doit tenus de se connecter à Azure Active Directory (AD Azure). </li><li>Les bots peuvent récupérer (et peuvent stocker) la liste des canaux d’une équipe. Ces données ne restent pas sur le réseau d’entreprise. </li><li>Lorsqu’un fichier est envoyé à un robot, le fichier quitte le réseau d’entreprise. Envoi et réception de fichiers nécessitent l’approbation de l’utilisateur pour chaque fichier. </li><li>Par défaut, robots n’ont pas la possibilité d’agir au nom de l’utilisateur, mais robots peuvent demander aux utilisateurs de se connecter ; dès que l’utilisateur se connecte, le composant WebBot aura un jeton d’accès avec lequel il peut effectuer des opérations supplémentaires. Exactement quels sont les éléments supplémentaires varie selon le composant WebBot et où l’utilisateur se connecte : un robot est une application Azure AD inscrit sur <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> et peut avoir son propre ensemble d’autorisations.</li><li>Les bots sont informés à chaque fois que des utilisateurs sont ajoutés ou supprimés d'une équipe.</li><li>Robots ne voyez pas les adresses IP des utilisateurs ou autres informations du point d’accès. Toutes les informations provenant de Microsoft. (Il existe une exception : si un robot implémente son propre expérience de connexion, l’interface utilisateur de connexion s’affiche des informations du point d’accès et les adresses IP des utilisateurs.)</li><li>Les extensions de messagerie, d’autre part, voient les adresses IP des utilisateurs et les informations du référent.</li><li>Instructions de l’application (et notre processus de révision AppSource) nécessitent discrétion de validation des messages de conversation personnelle aux utilisateurs (par le biais de l’autorisation POST_MESSAGE_TEAM) pour des raisons valides. En cas d’abus, les utilisateurs peuvent bloquer le robot et administrateurs du client peut bloquer l’application Microsoft peut bloquer robots de façon centralisée si nécessaire.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Certains composants WebBot uniquement envoyer des messages (POST_MESSAGE_USER). Ils sont appelés robots « notification uniquement », mais le terme ne fait pas référence à un robot de rôle est autorisé ou non autorisé à faire, cela signifie que le robot ne souhaitez exposer une expérience CONVERSATIONNELLE. Les équipes utilise ce champ pour désactiver la fonctionnalité dans l’interface utilisateur qui serait normalement activé ; le robot n’est pas limité dans qu’il est autorisé à faire par rapport aux composants WebBot qui expose une expérience CONVERSATIONNELLE.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Actuellement dans la version préliminaire pour les développeurs.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Actuellement dans l’aperçu pour les développeurs. Régi par le <code>supportsFiles</code> propriété booléenne sur l’objet bot dans le fichier manifest.json pour l’application.</td>
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
    <td valign="top"><ul><li>Le profil de risque d’un onglet est presque identique à ce même site Web qui s’exécute dans un onglet de navigateur. </li><li>Un onglet obtient également le contexte dans lequel il est en cours d’exécution, y compris le nom de connexion et UPN de l’utilisateur actuel, l’objet AD Azure ID de l’utilisateur actuel, l’ID de l’Office 365 groupe (équipe) dans lequel il réside, l’ID de client et les paramètres régionaux de l’utilisateur. Cependant, pour mapper les ID aux informations d’un utilisateur, l’onglet aurait pour qu’un utilisateur se connecter à Azure AD.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge _des messages_, qui permettent aux utilisateurs de publier des réponses ciblées sur le message de connecteur, par exemple en ajoutant une réponse à un problème de référentiels ou une date pour une carte de Trello.</td>
    <td valign="top"><ul><li>Le système qui publie des messages du connecteur ne sait pas qui il est report ou qui reçoit les messages : aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, pas le client ; Microsoft effectue la publication sur le canal réelle.)</li><li>Aucune donnée ne quitte le réseau d’entreprise lorsque les messages du connecteur sont publiés dans un canal.</li><li>Les connecteurs qui prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE) ne voient pas non plus l'adresse IP et les informations du référent. Ces informations sont envoyées à Microsoft puis routées vers les points de terminaison HTTP qui ont été enregistrés auparavant auprès de Microsoft dans le portail des connecteurs.</li><li>Chaque fois qu’un connecteur est configuré pour une chaîne, une URL unique pour cette instance de connecteur est créée. Si cette instance de connecteur est supprimée, l’URL peut ne plus être utilisée.</li><li>Les messages des connecteurs peuvent contenir des pièces jointes.</li><li>L’instance du connecteur URL doit être traitée comme une clé secrète/confidentielles : toute personne ayant que peut publier des URL, comme une adresse de messagerie. Par conséquent, il existe certaines risque de courrier indésirable ou des liens vers les sites de phishing ou un programme malveillant. Si qui était le cas, les propriétaires de l’équipe peuvent supprimer l’instance du connecteur.</li><li>Si le service qui envoie les messages des connecteurs était compromis et commençait à envoyer des liens de spam/hameçonnage/logiciel malveillant, l’administrateur du client peut empêcher la création de nouvelles instances du connecteur et Microsoft peut les bloquer de manière centrale.</li></ul></td>
  </tr>
</table>

> [!Note]
> Il n’est pas possible actuellement de savoir quels connecteurs prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks sortants

_Webhooks sortant_ sont créés par les propriétaires de l’équipe ou les membres de l’équipe à la volée si chargement de version test est activé pour un client. Ils ne sont pas des fonctionnalités des applications d’équipes ; Cette information est incluse par souci d’intégralité.

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Points à prendre en compte</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Peut recevoir des messages des utilisateurs et y répondre.</td>
    <td valign="top">Aucun</td>
    <td valign="top"><ul><li>Webhooks sortants sont similaires aux composants WebBot mais ont moins de privilèges. Elles doivent être explicitement mentionnées, à l’instar des robots.</li><li>Lorsqu’un webhook sortant est inscrit, une _clé secrète_ est généré, qui permet la webhook sortant vérifier que l’expéditeur est Microsoft Teams par opposition à un utilisateur malveillant. Ce mot de passe doit rester secret ; toute personne ayant accès à celui-ci peut emprunter l’identité Teams Microsoft. Si la clé secrète est compromise, le webhook sortant peut être supprimé et recréé et une nouvelle clé secrète sera générée.</li><li>Bien qu'il soit possible de créer un webhook sortant qui ne valide pas le code secret, cela n’est pas recommandé.</li><li>Les webhooks sortants ne peuvent pas faire plus que recevoir et répondre à des messages : ils ne peuvent pas envoyer des messages de façon proactive, ils ne peuvent pas envoyer ni recevoir de fichiers, ils ne peuvent pas faire autre chose que ce que peuvent faire les bots excepté recevoir et répondre à des messages.</li></ul></td>
  </tr>
</table>