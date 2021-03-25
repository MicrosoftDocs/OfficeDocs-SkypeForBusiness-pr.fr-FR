---
title: Coexistence avec Skype Entreprise
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Comportement de coexistence entre Teams & Skype Entreprise, y compris les paramètres de routage, le routage des & d’appel, les conversations & appels à partir de threads & existants.
ms.openlocfilehash: 603356df5e6f5006ea67f6a84141acf1347c1235
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122338"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

La coexistence et l’interopérabilité entre les clients et utilisateurs de Skype Entreprise et Teams sont définies par les modes TeamsUpgrade, décrits dans les instructions de migration et d’interopérabilité pour les organisations qui utilisent Teams avec [Skype Entreprise.](migration-interop-guidance-for-teams-with-skype.md)

Un utilisateur donné se voit toujours attribuer un mode TeamsUpgrade, par défaut ou explicitement par l’administrateur. La valeur par défaut est *Îles.* Les utilisateurs mis à niveau vers Teams ont le mode *TeamsOnly.* *SfBOnly,* *SfBWithTeamsCollab* et *SfBWithTeamsCollabAndMeetings* sont également des modes possibles.


## <a name="routing-parameters"></a>Paramètres de routage

Le mode TeamsUpgrade du destinataire est essentiel pour déterminer le comportement des conversations, appels et présence, à la fois au sein d’un client et parmi des clients fédérés.

Si l’expéditeur utilise Teams, la décision de routage est prise lors de la création d’un fil de conversation. Dans Teams, les threads de conversation existants conservent toujours la méthode de routage déterminée lors de la création du thread : Teams prend en charge les threads persistants.

 Les méthodes de routage de thread sont les autres :  

- *natif* pour une conversation Teams à Teams dans le client
- *interop* for a Teams to Skype for business conversation in-tenant
- *fédéré pour* une conversation fédérée entre des locataires

Les paramètres qui déterminent la méthode de routage de thread sont les suivants :

- Mode Degrade Teams du destinataire
- Client utilisé par l’expéditeur
- Si la conversation est nouvelle ou qu’elle fait partie d’un fil de discussion existant
- Si la conversation est en client ou fédérée
- Si la conversation est possible
    - *L’interopérabilité* au sein du client nécessite que le client soit hybride en ligne ou Skype Entreprise. Les locataires locaux ne peuvent pas avoir d’interopérabilité au sein du client.
    - *La fédération entre clients nécessite* toujours une configuration de fédération Skype Entreprise appropriée, ainsi que la configuration appropriée de la fédération Teams des deux clients. Skype Entreprise hybride n’est requis pour aucun client.
    - Si le compte Skype Entreprise de la personne à l’origine est home local, cet utilisateur ne peut pas utiliser le client Teams pour l’interopérabilité au sein du client ou pour la fédération. Cet utilisateur peut uniquement utiliser le client Skype Entreprise pour l’interopérabilité et la fédération.
    - La communication entre équipes est toujours possible au cours d’un client.

> [!NOTE]
> Si le récepteur et l’expéditeur sont tous deux en mode de mise à niveau TeamsOnly, la conversation sera une expérience de conversation native qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez l’expérience de conversation native pour [les utilisateurs externes (fédérés) dans Teams.](native-chat-for-external-users.md) Si l’un des participants à la conversation n’est PAS en mode de mise à niveau TeamsOnly, la conversation reste une expérience d’échange avec les messages texte uniquement.

## <a name="chat-and-call-routing"></a>Routage des appels et des discussions

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage dans le client pour les nouvelles conversations ou appels 

Les tableaux ci-dessous capturent le routage des appels et des conversations dans le client, et sont valides pour les nouveaux appels ou conversations qui ne sont pas démarrés à partir d’un fil de discussion existant. Il décrit le client qui recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur de gauche, à un utilisateur destinataire dans le client de droite.

Les messages envoyés aux utilisateurs de TeamsOnly seront toujours acheminés vers Teams. Les messages envoyés aux utilisateurs de SfB seront toujours acheminés vers Skype Entreprise, si la \* conversation est possible comme décrit ci-dessus. Les messages envoyés aux utilisateurs des îles seront toujours acheminés vers le même client à partir duquel ils ont été envoyés.

Les tableaux ci-dessous indiquent quel client dans un mode donné recevra un appel de la part de l’origine (trois colonnes à l’extrême gauche), selon le mode de l’appelant, le client choisi et l’endroit où est situé son client Skype Entreprise (en équipe ou en ligne).

Dans les tables qui suivent : 
- **SfB \** _ représente l’un des modes suivants : _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings.*

- *Le texte en italique* met en évidence une conversation interop.

- **Impossible de** représenter une situation dans laquelle la conversation ou l’appel n’est pas possible. Dans ce cas, l’origineur doit utiliser Skype Entreprise. C’est l’une des raisons pour lesquelles les recommandations en exposant de Microsoft aux clients sur site/hybrides sont d’utiliser un mode autre que Islands (généralement SfBWithTeamsCollab) comme point de départ de leur parcours de mise à niveau vers Teams.

**Tableau 1a : nouvelle conversation dans le client ou routage d’appel vers un destinataire du mode Îles**

| <br/><br/> Mode | Originator <br/><br/> Client | <br/><br/> Page d’accueil SfB &nbsp; |<br/><br/>Route-->| Destinataire <br/><br/> Île  |
|--- |--- |--- |--- |--- |
| Île | Teams <br/> Skype Entreprise<br/> Teams<br/> Skype Entreprise| En ligne<br/> En ligne<br/> Sur-prém<br/>Sur-prém| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype Entreprise<br/> Teams<br/> Skype Entreprise|
|SfB\* <br/> | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Sur-prém<br/> |&boxv;<br/>&boxv;|Skype Entreprise<br/>Skype Entreprise<br/>|
|TeamsOnly |Équipes| Online<br/>|&boxv;<br/>|Équipes|
| | | | | |

**Tableau 1b : nouvelle conversation ou routage d’appel dans un client en mode SfB \***

| <br/><br/> Mode   | Originator <br/><br/> Client | <br/><br/> Page d’accueil SfB &nbsp; |<br/><br/>Route--> |   Destinataire <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Île |Teams<br/>Skype Entreprise<br/>Teams <br/>Skype Entreprise  |En ligne<br/> En ligne<br/> Sur-prém<br/> Sur-prém<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise<br/> **Impossible** <br/>Skype Entreprise<br/> |
|SfB\* <br/> | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Sur-prém<br/> |&boxv;<br/>&boxv; |  Skype Entreprise<br/>Skype Entreprise<br/> |
|TeamsOnly |Équipes| Online<br/>|&boxv;<br/> |  *Skype Entreprise* <br/>| 
| | | | | |

**Tableau 1c : nouvelle conversation ou routage d’appel dans le client vers un destinataire en mode TeamsOnly**

| <br/><br/> Mode   | Originator <br/><br/> Client | <br/><br/> Page d’accueil SfB &nbsp; |<br/><br/>Route-->|   Destinataire <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Île   |Teams<br/>Skype Entreprise<br/>Teams <br/>Skype Entreprise<br/>|En ligne<br/> En ligne<br/> Sur-prém<br/> Sur-prém<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Équipes <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Sur-prém<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Équipes | Online |  &boxv; |Équipes   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Routage fédéré pour les nouvelles conversations ou appels
  
Les tableaux ci-dessous capturent le routage des appels et conversations fédérés, et sont valides pour les nouveaux appels ou les nouvelles conversations. Ils décrivent le client qui recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur sur la gauche, à un utilisateur cible fédéré sur la droite.

En résumé, si la conversation est possible comme décrit ci-dessus, les messages envoyés aux utilisateurs de TeamsOnly seront toujours reçus dans Teams ; Les messages envoyés aux utilisateurs de SfB seront toujours reçus dans Skype Entreprise. Les messages envoyés aux utilisateurs des îles seront toujours reçus dans Skype Entreprise, quel que soit le client à partir duquel ils \* ont été envoyés. Le routage pour les conversations et appels fédérés diffère du routage dans le client, car les utilisateurs des îles recevront toujours une communication fédérée dans Skype Entreprise.

Cela est dû au fait qu’il est impossible d’supposer qu’un partenaire Skype Entreprise fédéré utilise déjà Teams s’il est en mode Îles. Il s’agit du mode par défaut, mais nous ne pouvons pas supposer que tous les utilisateurs d’îles exécutent Teams. En routant vers Skype Entreprise, nous nous assurons qu’aucune communication avec un utilisateur d’îles échoue. Si nous routeons vers Teams, cette communication risque d’être manquée si la cible n’utilise pas Teams. Un routage vers Skype Entreprise garantit que le message sera toujours reçu.  

> [!NOTE]
> L’implémentation actuelle de la fédération teams est basée sur la fédération Skype Entreprise, par conséquent elle tire parti de l’infrastructure d’interopérabilité (qui nécessite que le client de la personne à l’origine soit hybride en ligne pure ou Skype Entreprise) et offre un ensemble réduit de fonctionnalités par rapport à un thread natif. Nous prévoyons de fournir des équipes natives à la fédération Teams à l’avenir, auquel point le fil de discussion sera natif et fournir des fonctionnalités complètes.

Les tableaux ci-dessous décrivent le client qui recevra un appel de la part de l’origine (trois colonnes tout à gauche), selon le mode de l’origine, le client choisi et le lieu de résidence de son client Skype Entreprise (sur site ou en ligne).

**Tableau 2a : nouvelle conversation fédérée ou routage d’appel vers un destinataire d’îles**

| <br/><br/>Mode   | Originator<br/><br/> Client| <br/><br/>Page d’accueil SfB|<br/><br/>Route--> | Destinataire<br/><br/> Île |
|--- |--- |--- |--- |--- |
| Île |Teams<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise  |En ligne<br/> En ligne<br/> Sur-prém<br/> Sur-prém<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise <br/> **Impossible**   <br/> Skype Entreprise |
| SfB\* |Skype Entreprise <br/>Skype Entreprise |Online<br/> Sur-prém<br/> | &boxv;<br/>&boxv;|Skype Entreprise <br/>Skype Entreprise |
| TeamsOnly |Équipes |Online| &boxv;|*Skype Entreprise* |
|  | | | | 

**Tableau 2b : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode SfB \***

| <br/><br/>Mode   | Originator<br/><br/> Client| <br/><br/>Page d’accueil SfB|<br/><br/>Route-->|  Destinataire<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Île |Teams<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise <br/>|En ligne<br/> En ligne<br/> Sur-prém<br/> Sur-prém<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise <br/> **Impossible** <br/>Skype Entreprise <br/> |  
| SfB\* |Skype Entreprise <br/>Skype Entreprise  |Online<br/> Sur-prém<br/>  |&boxv;<br/>&boxv; | Skype Entreprise <br/>Skype Entreprise  |
| TeamsOnly | Équipes|Online |&boxv; |*Skype Entreprise*  |
|  | | | | |

**Tableau 2c : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode TeamsOnly**

| <br/><br/>Mode | Originator<br/><br/> Client| <br/><br/>Page d’accueil SfB|<br/><br/>Route-->|  Destinataire<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Île  |Teams<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise <br/>|En ligne<br/> En ligne<br/> Sur-prém<br/> Sur-prém<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Équipes <br/>*Teams* <br/>**Impossible** <br/>*Teams* |
| SfB\* |Skype Entreprise <br/>Skype Entreprise  | Online<br/> Sur-prém| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Équipes |Online |&boxv; |Équipes |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et appels de threads pré-existants

### <a name="from-teams"></a>À partir de Teams

Les appels ou conversations démarrés à partir d’un fil de conversation permanente pré-existant dans Teams sont acheminés de la même manière que ce thread, si cette option de routage est toujours disponible.

Si le fil de conversation permanente pré-existant dans Teams était un thread natif (c’est-à-dire, acheminé vers Teams), les messages et appels de conversation supplémentaires de ce thread seront acheminés vers Teams. S’il s’agit d’un thread interop (c’est-à-dire, acheminé vers Skype Entreprise), d’autres messages et appels de conversation sont acheminés vers Skype Entreprise (en supposant que des options de routage sont à nouveau disponibles).

> [!NOTE]
> Il est possible pour les threads pré-existants dans Teams de ne plus être routables, par exemple, lorsque le thread était un fil de discussion interop vers un utilisateur qui est désormais mis à niveau vers Teams. Étant donné qu’il a été créé sous la direction d’un thread interop, le thread est acheminé vers Skype Entreprise, mais cet utilisateur ne peut plus utiliser Skype Entreprise pour les discussions et les appels. Dans ce cas, le fil de discussion est désactivé et ne permet pas d’autres communications.

### <a name="from-skype-for-business"></a>À partir de Skype Entreprise

Les threads Skype Entreprise ne sont pas persistantes au-delà de 10 min. Délai d’application de la session SIP. Les conversations et appels d’un thread existant dans Skype Entreprise avant l’expiration de la session SIP sont acheminés de la même manière que le thread. Les appels et conversations d’un fil de discussion existant dans Skype Entreprise au-delà du délai d’délai de la session SIP sont acheminés vers le client Skype Entreprise du tiers distant, quel que soit le client d’origine issu du thread de discussion de l’autre partie.

### <a name="availability"></a>Disponibilité

Les comportements au niveau du client et fédérés décrits ci-dessus sont disponibles, avec les limitations suivantes :

- Les participants externes dont les locataires résident dans un autre déploiement GoLocal ou dans une géographie ne voient pas les discussions par messagerie instantanée pendant une réunion « fédérée »
- La fédération et l’interopion entre O365 multitenant et les nuages souverains ne sont pas pris en charge

## <a name="presence"></a>Présence

Dans le cas où certains de vos utilisateurs utilisent le client Teams et que d’autres utilisent toujours le client Skype Entreprise, il est possible que certains de vos utilisateurs utilisent les deux clients. Vous souhaitez toujours que les états de présence soient partagés avec tous les utilisateurs, quel que soit le client dont dispose un utilisateur individuel. Lorsqu’il est partagé au sein de l’organisation, les utilisateurs peuvent mieux déterminer s’il convient de lancer une conversation ou d’effectuer un appel.

Par exemple, si la conversation ou l’appel d’un créateur doit se trouver sur le client Skype Entreprise de la cible, c’est la présence du client Skype Entreprise qui doit être affichée à l’auteur de l’appel. Si elle doit se poser sur le client Teams de la cible, c’est bien la présence du client Teams qui doit être affichée.

Pour savoir à quoi s’attendre, vous devez comprendre que la présence est partagée en fonction du mode de coexistence d’un utilisateur :

* Si un utilisateur est en mode TeamsOnly, tout autre utilisateur (que ce soit dans Teams ou Skype Entreprise) verra cette présence dans Teams de cet utilisateur
* Si un utilisateur est dans l’un des modes SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), tout autre utilisateur (que ce soit dans Teams ou Skype Entreprise) verra la présence Skype Entreprise de cet utilisateur SfB \*
* Si un utilisateur est en mode Îles (ou hérité), la présence dans Teams et la présence dans Skype Entreprise sont indépendantes (les valeurs ne doivent pas correspondre) et les autres utilisateurs voient l’une ou l’autre présence de l’utilisateur des îles, selon qu’il se trouve dans le même client ou dans un client fédéré et quel client il utilise
    * À partir de Teams, tout autre utilisateur au sein du même client verra la présence teams de l’utilisateur des îles ; aligné sur la table de routage dans le client ci-dessus
    * Dans Teams, tous les autres utilisateurs d’un client fédéré voient la présence de l’utilisateur des îles Skype Entreprise. aligné sur le tableau de routage fédéré ci-dessus
    * À partir de Skype Entreprise, les autres utilisateurs verront la présence de l’utilisateur des îles (à la fois au sein du client et fédéré) ; aligné sur les tables de routage ci-dessus


### <a name="in-tenant-presence"></a>Présence dans le client

Les messages envoyés aux utilisateurs de TeamsOnly seront toujours reçus dans Teams. Les messages envoyés aux utilisateurs de SfB seront toujours reçus dans Skype Entreprise, si la \* conversation est possible comme décrit ci-dessus. Les messages envoyés aux utilisateurs des îles sont toujours reçus dans le client dont ils proviennent.

Le tableau décrit la présence de Publisher visible par un watcher, en fonction du mode de l’Éditeur et du client de l’watcher (pour une nouvelle conversation).

**Tableau 3 : présence dans le client (nouveau thread)**

|Watcher <br/><br/>Client|<br/><br/>Route--> |<br/><br/>Île |Publisher <br/><br/>SfB\* |<br/>Teams uniquement|
|--- |--- |--- |--- |---|
|Skype Entreprise |&boxv;|Skype Entreprise | Skype Entreprise | Teams|
|Teams |&boxv; |Teams |Skype Entreprise |Teams |
| | | | |

### <a name="federated-presence"></a>Présence fédérée

La présence fédérée est basée sur la capacité d’accès fédérée affichée dans le tableau 2.

Le tableau ci-dessous décrit la présence de Publisher visible par un watcher, en fonction du mode de l’Éditeur et du client de l’watcher (pour un nouveau thread). Dans la pratique, le client de l’Watcher ne fait aucune différence dans la fédération à ce stade.

**Tableau 4 : présence fédérée (nouveau thread)**

|Watcher <br/><br/> Client |<br/><br/>Route-->|<br/><br/> Île  |Publisher <br/><br/> SfB\* |<br/><br/> Teams uniquement |
|--- |--- |--- |--- |---|
|Skype Entreprise |&boxv; |Skype Entreprise  | Skype Entreprise  | Teams  |
|Teams | &boxv;|Skype Entreprise |Skype Entreprise |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Présence dans des threads pré-existants

Pour aligner la présence et l’accessibilité dans les threads pré-existants, la présence de la cible exposée dans ce thread doit être alignée sur le routage du thread, en supposant que le routage est possible.

En particulier, si un destinataire avec qui vous avez précédemment eu un fil de conversation permanente interop a été mis à niveau vers Teams, ce thread ne reflète plus la présence précise et ne sera plus routable. Vous devez commencer un nouveau thread.

## <a name="related-links"></a>Liens connexes
[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Vidéo : Gérer la coexistence et l’interopérabilité entre SfB et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)