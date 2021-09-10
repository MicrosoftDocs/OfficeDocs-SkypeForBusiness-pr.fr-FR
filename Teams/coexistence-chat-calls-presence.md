---
title: Coexistence avec Skype Entreprise
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Comportement de coexistence entre Teams & Skype Entreprise, y compris les paramètres de routage, le routage des & d’appel, les conversations & appels à partir de threads pré-existants, & présence.
ms.openlocfilehash: 5383ff8c68b8950b449b5159a530a1439156a945
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58972922"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

La coexistence et l’interopérabilité entre les clients et utilisateurs Skype Entreprise et Teams sont définies par les modes TeamsUpgrade, décrits dans les recommandations sur la migration et [l’interopérabilité](migration-interop-guidance-for-teams-with-skype.md)pour les organisations qui utilisent Teams avec Skype Entreprise.

Un utilisateur donné se voit toujours attribuer un mode TeamsUpgrade, par défaut ou explicitement par l’administrateur. La valeur par défaut est *Îles.* Les utilisateurs mis à Teams ont le mode *TeamsOnly.* *SfBOnly,* *SfBWithTeamsCollab* et *SfBWithTeamsCollabAndMeetings* sont également des modes possibles.

## <a name="routing-parameters"></a>Paramètres de routage

Le mode TeamsUpgrade du destinataire est essentiel pour déterminer le comportement des conversations, appels et présence, à la fois au sein d’un client et parmi des clients fédérés.

Si l’expéditeur utilise Teams, la décision de routage est prise lors de la création d’un fil de conversation. Les threads de conversation Teams conservent toujours la méthode de routage déterminée lors de la création du thread : Teams prend en charge les threads persistants.

 Les méthodes de routage de thread sont les autres :

- *native* pour une Teams à Teams conversation dans le client
- *interop* pour une conversation Teams à Skype entreprise dans le client
- *fédéré pour* une conversation fédérée entre des locataires

Les paramètres qui déterminent la méthode de routage de thread sont les suivants :

- Mode Degrade Teams du destinataire
- Client utilisé par l’expéditeur
- Si la conversation est nouvelle ou qu’elle fait partie d’un fil de discussion existant
- Si la conversation est en client ou fédérée
- Si la conversation est possible
  - *L’interopérabilité* au sein du client nécessite que le client soit en ligne ou Skype Entreprise hybride. Les locataires locaux ne peuvent pas avoir d’interopérabilité au sein du client.
  - *La fédération entre les* locataires nécessite toujours une configuration Skype Entreprise de fédération appropriée, ainsi que Teams configuration de la fédération appropriée à partir des deux locataires. Skype Entreprise hybride n’est nécessaire pour aucun client.
  - Si le compte Skype Entreprise de la personne à l’origine est homed local, cet utilisateur ne peut pas utiliser le client Teams pour l’interopérabilité au sein du client ou pour la fédération. Cet utilisateur peut uniquement utiliser le client Skype Entreprise’interopérabilité et de fédération.
  - Teams communication Teams client est toujours possible.

> [!NOTE]
> Si le récepteur et l’expéditeur sont tous deux en mode de mise à niveau TeamsOnly, la conversation sera une expérience de conversation native qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez l’expérience de conversation native des [utilisateurs externes (fédérés) dans Teams.](native-chat-for-external-users.md) Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’échange avec les messages texte uniquement.

## <a name="chat-and-call-routing"></a>Routage des appels et des discussions

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage dans le client pour les nouvelles conversations ou appels

Les tableaux ci-dessous capturent le routage des appels et des conversations dans le client, et sont valides pour les nouveaux appels ou conversations qui ne sont pas démarrés à partir d’un fil de discussion existant. Il décrit le client qui recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur de gauche, à un utilisateur destinataire dans le client de droite.

Les messages envoyés aux utilisateurs de TeamsOnly seront toujours acheminés vers Teams. Les messages envoyés aux utilisateurs de SfB seront toujours acheminés vers Skype Entreprise, si \* la conversation est possible comme décrit ci-dessus. Les messages envoyés aux utilisateurs des îles seront toujours acheminés vers le même client à partir duquel ils ont été envoyés.

Les tableaux ci-dessous indiquent quel client dans un mode donné recevra un appel de la part de l’origine (trois colonnes les plus à gauche), selon le mode de l’appelant, le client choisi et l’endroit où son client Skype Entreprise est domicile (en ligne ou en ligne).

Dans les tables qui suivent :

- **SfB \** _ représente l’un des modes suivants : _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings.*
- *Le texte en italique* met en évidence une conversation interop.
- **Impossible de** représenter une situation dans laquelle la conversation ou l’appel n’est pas possible. Dans ce cas, l’Skype Entreprise doit utiliser une Skype Entreprise' C’est l’une des raisons pour lesquelles les conseils en exposant de Microsoft aux clients sur site/hybrides sont d’utiliser un mode autre que Islands (généralement SfBWithTeamsCollab) comme point de départ de leur parcours de mise à niveau vers Teams.

#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tableau 1a : nouvelle conversation dans le client ou routage d’appel vers un destinataire du mode Îles

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Page d’accueil SfB &nbsp;|<br><br>Route-->|Destinataire<br><br>Île|
|---|---|---|:---:|---|
|Île|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|En ligne <br> En ligne<br> Sur-prém<br>Sur-prém|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|
|SfB\*|Skype Entreprise <br>Skype Entreprise|Online <br> Sur-prém|&boxv;<br>&boxv;|Skype Entreprise <br> Skype Entreprise|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>Tableau 1b : nouvelle conversation ou routage d’appel dans un client en mode SfB \*

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Page d’accueil SfB &nbsp;|<br><br>Route-->|Destinataire<br><br>SfB\*|
|---|---|---|:---:|---|
|Île|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|En ligne <br> En ligne <br> Sur-prém <br> Sur-prém|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype Entreprise* <br> Skype Entreprise <br> **Impossible** <br> Skype Entreprise|
|SfB\*|Skype Entreprise <br> Skype Entreprise|Online <br> Sur-prém|&boxv;<br>&boxv;|Skype Entreprise <br> Skype Entreprise|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tableau 1c : nouvelle conversation ou routage d’appel dans le client vers un destinataire en mode TeamsOnly

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Page d’accueil SfB &nbsp;|<br><br>Route-->|Destinataire<br><br>TeamsOnly|
|---|---|---|:---:|---|
|Île|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|En ligne <br> En ligne <br> Sur-prém <br> Sur-prém|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Équipes <br> *Teams* <br> Teams <br> *Teams*|
|SfB\*|Skype Entreprise <br> Skype Entreprise|Online <br> Sur-prém|&boxv;<br>&boxv;|*Teams* <br> *Teams*|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
||||||

### <a name="federated-routing-for-new-chats-or-calls"></a>Routage fédéré pour les nouvelles conversations ou appels

Les tableaux ci-dessous capturent le routage des appels et des conversations fédérés, et sont valides pour les nouveaux appels ou les nouvelles conversations. Ils décrivent le client qui recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur sur la gauche, à un utilisateur cible fédéré sur la droite.

En résumé, si la conversation est possible comme décrit ci-dessus, les messages envoyés aux utilisateurs de TeamsOnly seront toujours Teams ; Les messages envoyés aux utilisateurs de SfB seront toujours reçus dans Skype Entreprise; les messages envoyés aux utilisateurs des îles seront toujours reçus dans Skype Entreprise quel que soit le client à partir duquel ils ont \* été envoyés. Le routage pour les conversations et appels fédérés diffère du routage dans le client, car les utilisateurs des îles recevront toujours une communication fédérée dans Skype Entreprise.

Cela est dû au fait que nous ne pouvons pas supposer qu’un partenaire Skype Entreprise fédéré utilise déjà Teams s’il est en mode Îles. Il s’agit du mode par défaut, mais nous ne pouvons pas supposer que tous les utilisateurs d’îles exécutent Teams. En routant vers un Skype Entreprise nous nous assurons qu’aucune communication avec un utilisateur d’îles échoue. Si nous nous sommes acheminés vers Teams, cette communication pourrait être manquée si la cible n’a pas utilisé Teams. Un routage Skype Entreprise s’assure que le message sera toujours reçu.

> [!NOTE]
> L’implémentation actuelle de la fédération Teams est basée sur la fédération Skype Entreprise, par conséquent elle tire parti de l’infrastructure d’interopérabilité (qui nécessite que le client de la personne à l’origine soit hybride en ligne pure ou Skype Entreprise) et offre un ensemble réduit de fonctionnalités par rapport à un thread natif. Nous prévoyons de fournir des Teams natives à Teams fédération à l’avenir, auquel cas le fil de discussion sera natif et proposera des fonctionnalités complètes.

Les tableaux ci-dessous décrivent le client qui recevra un appel de la part de l’origine (trois colonnes les plus à gauche), selon le mode de l’origine, le client choisi et le lieu de résidence de son client Skype Entreprise (en ligne ou en ligne).

#### <a name="table-2a-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tableau 2a : nouvelle conversation fédérée ou routage d’appel vers un destinataire d’îles

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Page d’accueil SfB|<br><br>Route-->|Destinataire<br><br>Île|
|---|---|---|:---:|---|
|Île|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|En ligne <br> En ligne <br> Sur-prém <br> Sur-prém|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype Entreprise* <br> Skype Entreprise <br> **Impossible** <br> Skype Entreprise|
|SfB\*|Skype Entreprise <br> Skype Entreprise|Online <br> Sur-prém|&boxv;<br>&boxv;|Skype Entreprise <br> Skype Entreprise|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|||||

#### <a name="table-2b-federated-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>Tableau 2b : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode SfB \*

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Page d’accueil SfB|<br><br>Route-->|Destinataire<br><br> SfB\*|
|---|---|---|:---:|---|
|Île|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|En ligne <br> En ligne <br> Sur-prém <br> Sur-prém|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype Entreprise* <br> Skype Entreprise <br> **Impossible** <br> Skype Entreprise|
|SfB\*|Skype Entreprise <br> Skype Entreprise|Online <br> Sur-prém|&boxv;<br>&boxv;|Skype Entreprise <br> Skype Entreprise|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
||||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tableau 2c : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode TeamsOnly

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Page d’accueil SfB|<br><br>Route-->|Destinataire<br><br>TeamsOnly|
|---|---|---|:---:|---|
|Île|Teams <br> Skype Entreprise <br> Teams <br> Skype Entreprise|En ligne <br> En ligne <br> Sur-prém <br> Sur-prém|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Équipes <br> *Teams* <br> **Impossible** <br> *Teams*|
|SfB\*|Skype Entreprise <br> Skype Entreprise|Online <br> Sur-prém|&boxv;<br>&boxv;|*Teams* <br> *Teams*|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
||||||

## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et appels de threads pré-existants

### <a name="from-teams"></a>À partir de Teams

Les appels ou conversations démarrés à partir d’un fil de conversation permanente existant dans Teams seront acheminés de la même façon que celui du thread, si cette option de routage est toujours disponible.

Si le thread persistant existant dans Teams était un thread natif (c’est-à-dire, acheminé vers Teams), d’autres messages de conversation et appels de ce thread seront Teams. S’il s’agit d’un thread interop (c’est-à-dire, acheminé vers Skype Entreprise), les messages et appels de conversation supplémentaires sont acheminés vers le Skype Entreprise (en supposant que des options de routage sont à nouveau disponibles).

> [!NOTE]
> Il est possible pour les threads existants dans Teams de ne plus être routables, par exemple, lorsque le thread était un thread interop vers un utilisateur qui est mis à niveau vers Teams. Étant donné qu’il a été créé en tant que thread interop, le thread est acheminé jusqu’à Skype Entreprise, mais cet utilisateur ne peut plus utiliser les Skype Entreprise pour la conversation et les appels. Dans ce cas, le fil de discussion est désactivé et ne permet pas d’autres communications.

### <a name="from-skype-for-business"></a>À partir de Skype Entreprise

Skype Entreprise threads ne sont pas persistantes au-delà de 10 min. Délai d’délai de session SIP. Les conversations et appels d’un thread existant dans Skype Entreprise avant l’expiration de la session SIP sont acheminés de la même manière que le thread. Les appels et conversations d’un fil de discussion existant dans Skype Entreprise au-delà du délai d’délai de la session SIP sont acheminés vers la Skype Entreprise distante, quel que soit le client d’origine issu du thread de l’autre partie.

### <a name="availability"></a>Disponibilité

Les comportements au niveau du client et fédérés décrits ci-dessus sont disponibles, avec les limitations suivantes :

- Les participants externes dont les locataires résident dans un autre déploiement GoLocal ou dans une géographie ne voient pas les discussions par messagerie instantanée pendant une réunion « fédérée »
- La fédération et l’interopation entre les Office 365 et Office 365 gérés par 21Vianet sont pris en charge dans des scénarios limités.


## <a name="presence"></a>Présence

Lorsqu’il se peut que certains de vos utilisateurs utilisent le client Teams et que d’autres utilisent toujours le client Skype Entreprise, il se peut qu’un certain nombre d’utilisateurs utilisent les deux clients. Vous souhaitez toujours que les états de présence soient partagés avec tous les utilisateurs, quel que soit le client dont dispose un utilisateur individuel. Lorsqu’il est partagé au sein de l’organisation, les utilisateurs peuvent mieux déterminer s’il convient de lancer une conversation ou d’effectuer un appel.

Par exemple, si la conversation ou l’appel d’un créateur doit se trouver sur le client Skype Entreprise de la cible, c’est la présence du client Skype Entreprise qui doit être affichée à l’origine. Si elle doit se poser sur le client Teams cible, c’est la présence du client Teams qui doit être affichée.

Pour savoir à quoi s’attendre, vous devez comprendre que la présence est partagée en fonction du mode de coexistence d’un utilisateur :

- Si un utilisateur est en mode TeamsOnly, tout autre utilisateur (que ce soit en Teams ou en Skype Entreprise) verra la présence de cet utilisateur Teams TeamsOnly
- Si un utilisateur est dans l’un des modes SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), tout autre utilisateur (que ce soit dans Teams ou Skype Entreprise) verra la présence Skype Entreprise de cet utilisateur SfB \*
- Si un utilisateur est en mode Îles (ou hérité), la présence dans Teams et la présence dans Skype Entreprise sont indépendantes (les valeurs ne doivent pas correspondre) et les autres utilisateurs voient l’une ou l’autre présence de l’utilisateur des îles, selon qu’il se trouve dans le même client ou dans un client fédéré et quel client il utilise
  - À partir Teams, tout autre utilisateur au sein du même client verra la présence de l’Teams des îles. aligné sur la table de routage dans le client ci-dessus
  - À partir Teams, tous les autres utilisateurs d’un client fédéré voient la présence Skype Entreprise de l’utilisateur des îles. aligné sur le tableau de routage fédéré ci-dessus
  - À partir Skype Entreprise, les autres utilisateurs verront la présence Skype Entreprise de l’utilisateur des îles (à la fois au sein du client et fédéré) ; aligné sur les tables de routage ci-dessus

### <a name="in-tenant-presence"></a>Présence dans le client

Les messages envoyés aux utilisateurs de TeamsOnly seront toujours reçus Teams. Les messages envoyés aux utilisateurs de SfB seront toujours Skype Entreprise conversation, si la \* conversation est possible comme décrit ci-dessus. Les messages envoyés aux utilisateurs des îles sont toujours reçus dans le client dont ils proviennent.

Le tableau décrit la présence du Publisher visible par un watcher, selon le mode de la Publisher et le client de l’observeur (pour une nouvelle conversation).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tableau 3 : présence dans le client (nouveau thread)

<br>

|Watcher<br><br>Client|<br><br>Route-->|<br><br>Île|Publisher<br><br>SfB\*|<br>Teams Uniquement|
|---|:---:|---|---|---|
|Skype Entreprise|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
|Teams|&boxv;|Teams|Skype Entreprise|Teams|
|||||

### <a name="federated-presence"></a>Présence fédérée

La présence fédérée est basée sur la capacité d’accès fédérée affichée dans le tableau 2.

Le tableau ci-dessous décrit la présence du Publisher visible par un watcher, en fonction du mode de la Publisher et du client de l’watcher (pour une nouvelle conversation). Dans la pratique, le client de l’Watcher ne fait aucune différence dans la fédération à ce stade.

#### <a name="table-4-federated-presence-new-thread"></a>Tableau 4 : présence fédérée (nouveau thread)

<br>

|Watcher<br><br>Client|<br><br>Route-->|<br><br>Île|Publisher<br><br>SfB\*|<br><br>Teams Uniquement|
|---|:---:|---|---|---|
|Skype Entreprise|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
|Teams|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Présence dans des threads pré-existants

Pour aligner la présence et l’accessibilité dans les threads pré-existants, la présence de la cible exposée dans ce thread doit être alignée sur le routage du thread, en supposant que le routage est possible.

En particulier, si un destinataire avec qui vous avez précédemment eu un thread de conversation permanente interop a été mis à niveau vers Teams, ce thread ne reflète plus la présence précise et ne sera plus routable. Vous devez commencer un nouveau thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Fédération et interop. Office 365 par 21Vianet

La fédération et l’interopation entre les Office 365 à plusieurs clients et Office 365 gérés par 21Vianet sont pris en charge lorsque les utilisateurs Office 365 client multiples sont en mode Teams seul. Dans ce scénario, les utilisateurs de Skype Entreprise Online dans Office 365 géré par 21Vianet pourront communiquer avec Teams Seuls les utilisateurs des Office 365 à plusieurs clients par le biais de conversations et d’appels. Le tableau suivant indique les scénarios pris en charge dans cette configuration :
 
|Scénario|Origine|Destinataire|Pris en charge ?|
|---|---|---|---|
|Présence|Teams <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui<br>Oui|
|Conversation|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui(1:1 uniquement)|
|Appels audio|Teams <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui (1:1 uniquement)|
|Appels vidéo|Teams <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui (1:1 uniquement)|
|Partage d’écran|Teams <br> Skype Entreprise <br> | Skype Entreprise <br> Teams |Oui (via une réunion Teams promue)<br>Oui (via une réunion SfB promue)|
|||||


## <a name="related-links"></a>Liens connexes
[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Vidéo : Gérer la coexistence et l’interopérabilité entre SfB et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
