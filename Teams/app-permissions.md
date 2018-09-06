---
title: Considérations et les autorisations des applications Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Découvrez ce que les applications de données et les autorisations qui demandent à partir de votre organisation.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.openlocfilehash: 789e1a52b9a195cc353e120a769fa98c26343e88
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251593"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Considérations et les autorisations des applications Microsoft Teams

Applications Microsoft Teams sont un moyen pour une ou plusieurs fonctionnalités dans un _package d’application_ qui peut être installé, mis à niveau et désinstallation d’agrégation. Les fonctionnalités sont les suivantes :

-   Composants WebBot
-   Extensions de messagerie
-   Onglets
-   Connecteurs

Les applications sont souhaitez par les utilisateurs et gérées par informatique du point de vue de la stratégie. Toutefois, pour l’essentiel, les autorisations et le profil de risque d’une application sont définies par les autorisations et les profils de risque des fonctions qu’elle contient. Par conséquent, cet article se concentre sur les autorisations et les considérations au niveau de la fonctionnalité.

Les autorisations répertoriées ci-dessous en majuscules, par exemple RECEIVE_MESSAGE et REPLYTO_MESSAGE, n’apparaissent pas n’importe où dans la [documentation du développeur Microsoft équipes](https://aka.ms/teamsdevdocs) ou les [autorisations pour Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Ils sont simplement une forme abrégée descriptive pour les besoins de cet article.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Utilisez les tableaux ci-dessous comme un guide pour comprendre les autorisations qui demandent des applications que vous êtes étudier.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>L’application de recherche ou de service lui-même pour décider si vous souhaitez accorder l’accès au sein de votre organisation. Par exemple, robots envoyer et recevoir des messages des utilisateurs, et, à l’exception des robots de métier d’entreprise, ils se trouvent en dehors de la limite de la conformité. Par conséquent, n’importe quelle application qui inclut un robot requiert ces autorisations et a profil risque, au minimum. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Considérations et les autorisations d’application globaux

<table>
  <tr>
    <th width="25%">Autorisations requises</th>
    <th width="25%">Autorisations facultatives</th>
    <th width="50%">Inconvénients</th>
  </tr>
  <tr>
    <td valign="top">Aucun</td>
    <td valign="top">Aucun</td>
    <td valign="top">Une application doit indiquer les données qu’il utilise et les données sont utilisées dans les termes de liaisons de stratégie de confidentialité et d’utilisation.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Robots et les extensions de messagerie

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Le robot peut recevoir des messages des utilisateurs et y répondre. <sup>1</sup></li><li>POST_MESSAGE_USER. Un utilisateur a envoyé un message à un robot, le robot peut envoyer l’utilisateur directs messages (également appelées _messages proactives_) à tout moment.</li><li>GET_CHANNEL_LIST. Ajout aux équipes de robots peuvent obtenir une liste de noms et les ID des canaux dans une équipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTITÉ. Lorsqu’il est utilisé dans un canal, robots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom de famille, nom d’utilisateur principal [UPN], adresse de messagerie) ; Lorsqu’il est utilisé dans une conversation personnelle ou de groupe, le robot peut accéder aux informations même pour ces utilisateurs.</li><li> POST_MESSAGE_TEAM. Permet de robots d’une application envoyer des messages (proactives) directs à n’importe quel membre de l’équipe à tout moment, même si l’utilisateur n’a jamais parlé pour le composant WebBot avant.</li><li>Les éléments suivants ne sont pas des autorisations explicites, mais sont implicites par RECEIVE_MESSAGE et REPLYTO_MESSAGE et les étendues, dans lequel les composants WebBot peut être utilisé, déclaré dans le manifeste : <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. Contrôles <sup>3</sup> si un robot peut envoyer et recevoir des fichiers dans la conversation personnelle (non pris en charge pour la conversation de groupe ou les canaux).</li></ul></td>
    <td valign="top"><ul><li>Robots ont uniquement accès aux équipes à laquelle ils ont été ajoutés ou les utilisateurs qui ont installé les.</li><li>Robots recevoir uniquement des messages dans lequel elles sont mentionnées explicitement par les utilisateurs. Ces données quittent le réseau d’entreprise.</li><li>    Robots uniquement pour répondre aux conversations dans lequel elles sont mentionnées.</li><li>Une fois que l’utilisateur a conversed avec un robot, si le composant WebBot stocke les ID de l’utilisateur, il peut envoyer des messages directs cet utilisateur à tout moment. </li><li>Il est théoriquement possible de robot messages contiennent des liens vers des sites de hameçonnage ou des programmes malveillants, mais robots peuvent être bloquées par l’utilisateur, l’administrateur du client, ou globalement par Microsoft. </li><li>Un robot peut récupérer (et peut stocker) les informations d’identité de base pour l’application a été ajoutée à des membres de l’équipe, ou pour des utilisateurs spécifiques à des conversations personnelles ou de groupe. Pour obtenir plus d’informations sur ces utilisateurs, le robot doit tenus de se connecter à Azure Active Directory (AD Azure). </li><li>Robots peuvent récupérer (et peuvent stocker) la liste des chaînes dans une équipe ; ces données quittent le réseau d’entreprise. </li><li>Lorsqu’un fichier est envoyé à un robot, le fichier quitte le réseau d’entreprise. Envoi et réception de fichiers nécessitent l’approbation de l’utilisateur pour chaque fichier. </li><li>Par défaut, robots n’ont pas la possibilité d’agir au nom de l’utilisateur, mais robots peuvent demander aux utilisateurs de se connecter ; dès que l’utilisateur se connecte, le composant WebBot aura un jeton d’accès avec lequel il peut effectuer des opérations supplémentaires. Exactement quels sont les éléments supplémentaires varie selon le composant WebBot et où l’utilisateur se connecte : un robot est une application Azure AD inscrit sur <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> et peut avoir son propre ensemble d’autorisations.</li><li>Robots sont informés lorsque les utilisateurs sont ajoutés ou supprimés à partir d’une équipe.</li><li>Robots ne voyez pas les adresses IP des utilisateurs ou autres informations du point d’accès. Toutes les informations provenant de Microsoft. (Il existe une exception : si un robot implémente son propre expérience de connexion, l’interface utilisateur de connexion s’affiche des informations du point d’accès et les adresses IP des utilisateurs.)</li><li>En revanche, les extensions de messagerie, voyez des informations du point d’accès et les adresses IP des utilisateurs.</li><li>Instructions de l’application (et notre processus de révision AppSource) nécessitent discrétion de validation des messages de conversation personnelle aux utilisateurs (par le biais de l’autorisation POST_MESSAGE_TEAM) pour des raisons valides. En cas d’abus, les utilisateurs peuvent bloquer le robot et administrateurs du client peut bloquer l’application Microsoft peut bloquer robots de façon centralisée si nécessaire.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Certains composants WebBot uniquement envoyer des messages (POST_MESSAGE_USER). Ils sont appelés robots « notification uniquement », mais le terme ne fait pas référence à un robot de rôle est autorisé ou non autorisé à faire, cela signifie que le robot ne souhaitez exposer une expérience CONVERSATIONNELLE. Les équipes utilise ce champ pour désactiver la fonctionnalité dans l’interface utilisateur qui serait normalement activé ; le robot n’est pas limité dans qu’il est autorisé à faire par rapport aux composants WebBot qui expose une expérience CONVERSATIONNELLE.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Actuellement dans l’aperçu pour les développeurs.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Actuellement dans l’aperçu pour les développeurs. Régi par le <code>supportsFiles</code> propriété booléenne sur l’objet bot dans le fichier manifest.json pour l’application.</td>
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
    <td valign="top"><ul><li>Le profil de risque d’un onglet est pratiquement identique à ce même site en cours d’exécution dans un onglet du navigateur. </li><li>Un onglet obtient également le contexte dans lequel il est en cours d’exécution, y compris le nom de connexion et UPN de l’utilisateur actuel, l’objet AD Azure ID de l’utilisateur actuel, l’ID de l’Office 365 groupe (équipe) dans lequel il réside, l’ID de client et les paramètres régionaux de l’utilisateur. Cependant, pour mapper les ID aux informations d’un utilisateur, l’onglet aurait pour qu’un utilisateur se connecter à Azure AD.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Certains connecteurs prennent en charge _des messages_, qui permettent aux utilisateurs de publier des réponses ciblées sur le message de connecteur, par exemple en ajoutant une réponse à un problème de référentiels ou une date pour une carte de Trello.</td>
    <td valign="top"><ul><li>Le système qui publie des messages du connecteur ne sait pas qui il est report ou qui reçoit les messages : aucune information sur le destinataire n’est divulguée. (Microsoft est le destinataire réel, pas le client ; Microsoft effectue la publication sur le canal réelle.)</li><li>Aucune donnée ne quitte le réseau d’entreprise lors de la validation des messages du connecteur à un canal.</li><li>Les connecteurs qui prennent en charge des messages (autorisation REPLYTO_CONNECTOR_MESSAGE) ne s’affichent les informations d’adresse et le point d’accès IP ; Ces informations sont envoyées à Microsoft et ensuite acheminées vers les points de terminaison HTTP qui ont été précédemment inscrit auprès de Microsoft dans le portail de connecteurs.</li><li>Chaque fois qu’un connecteur est configuré pour une chaîne, une URL unique pour cette instance de connecteur est créée. Si cette instance de connecteur est supprimée, l’URL peut ne plus être utilisée.</li><li>Messages du connecteur ne peut pas contenir de pièces jointes.</li><li>L’instance du connecteur URL doit être traitée comme une clé secrète/confidentielles : toute personne ayant que peut publier des URL, comme une adresse de messagerie. Par conséquent, il existe certaines risque de courrier indésirable ou des liens vers les sites de phishing ou un programme malveillant. Si qui était le cas, les propriétaires de l’équipe peuvent supprimer l’instance du connecteur.</li><li>Si le service qui envoie des messages du connecteur ont été plus sécurisé et commencer à envoyer des liens de courrier indésirable/hameçonnage/programmes malveillants, un administrateur de clients permettre empêcher la création des instances de connecteur d’et Microsoft les bloquer centralisée.</li></ul></td>
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
    <td valign="top"><ul><li>Webhooks sortants sont similaires aux composants WebBot mais ont moins de privilèges. Elles doivent être explicitement mentionnées, à l’instar des robots.</li><li>Lorsqu’un webhook sortant est inscrit, une _clé secrète_ est généré, qui permet la webhook sortant vérifier que l’expéditeur est Microsoft Teams par opposition à un utilisateur malveillant. Ce mot de passe doit rester secret ; toute personne ayant accès à celui-ci peut emprunter l’identité Teams Microsoft. Si la clé secrète est compromise, le webhook sortant peut être supprimé et recréé et une nouvelle clé secrète sera générée.</li><li>Bien qu’il soit possible de créer un webhook sortant qui ne valide pas la clé secrète, il est recommandé par rapport à celui-ci.</li><li>Autre que la réception et répondre à des messages, sortant webhooks ne peut pas faire beaucoup : ils ne peuvent pas envoyer proactive des messages, qu’ils ne peuvent pas envoyer ou recevoir des fichiers, mais ils ne peuvent pas chose qui robots peuvent à l’exception de réception et répondre à des messages.</li></ul></td>
  </tr>
</table>