---
title: Coexistence avec Skype Entreprise
author: kenwith
ms.author: kenwith
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
description: Comportement de coexistence entre les équipes & Skype entreprise, y compris les paramètres de routage, les discussions & le routage des appels, les conversations & les appels existants, les & de présence.
ms.openlocfilehash: ff5e94b16cd55374ec0aeb45aaffdda41fbe0498
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137304"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

La coexistence et l’interopérabilité entre les clients et les utilisateurs de Skype entreprise et équipes sont définis par TeamsUpgrade modes, décrits dans les [instructions de migration et d’interopérabilité pour les organisations qui utilisent des équipes conjointement avec Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).

Tout utilisateur donné sera toujours affecté au mode TeamsUpgrade, par défaut ou explicitement par l’administrateur. La valeur par défaut est *îlot*. Les utilisateurs mis à niveau vers les équipes disposent du mode *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*et *SfBWithTeamsCollabAndMeetings* sont également des modes possibles.


## <a name="routing-parameters"></a>Paramètres de routage

Le mode TeamsUpgrade du destinataire est essentiel pour déterminer le comportement des conversations, des appels et de la présence, à la fois au sein d’un client et dans les clients fédérés.

Si l’expéditeur utilise Teams, la décision de routage est prise lors de la création d’un fil de conversation. Les threads de conversation existants dans teams conservent toujours la méthode de routage déterminée lors de la création du thread : teams prend en charge les threads persistants.

 Les méthodes de routage de threads sont les suivantes :  

- *natif* pour une conversation teams en équipes dans le client
- *interopérabilité* d’une équipe vers une conversation Skype entreprise dans le client
- *fédéré* pour une conversation fédérée entre des clients

Les paramètres qui déterminent la méthode de routage du thread sont les suivants :

- Le mode TeamsUpgrade du destinataire
- Client utilisé par l’expéditeur
- S’il s’agit d’une conversation nouvelle ou d’une partie d’un thread existant
- S’il s’agit d’une conversation autonome ou fédérée
- Si la conversation est possible
    - Une interopérabilité *dans le client* nécessite que le client soit entièrement en ligne ou Skype entreprise hybride. Les clients exclusivement sur site ne peuvent pas avoir d’interopérabilité in-client.
    - La *Fédération entre clients* nécessite toujours une configuration de la Fédération Skype entreprise appropriée ainsi qu’une configuration de Fédération d’équipe appropriée pour les deux clients. Skype entreprise hybride n’est requis pour aucun client.
    - Si le compte Skype entreprise de l’initiateur est hébergé sur site, il ne peut pas utiliser le client teams pour une interopérabilité entre les clients ou pour la Fédération. Ce dernier peut uniquement utiliser le client Skype entreprise à des fins d’interopérabilité et de Fédération.
    - La communication équipes vers teams est toujours possible dans le client.

> [!NOTE]
> S’il s’agit du destinataire et de l’expéditeur dans le mode de mise à niveau de TeamsOnly, la conversation sera une expérience de chat native qui inclut l’ensemble des fonctionnalités d’appel et de messagerie complètes. Pour en savoir plus, consultez [l’interface de conversation native pour les utilisateurs externes dans teams](native-chat-for-external-users.md). Si l’un des participants à la conversation n’est pas en mode de mise à niveau TeamsOnly, la conversation reste une interface d’interopérabilité avec les messages texte uniquement.

## <a name="chat-and-call-routing"></a>Messagerie instantanée et routage des appels

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage dans le client pour les nouvelles conversations ou appels 

Les tableaux ci-dessous capturent le routage de discussions et d’appels dans le client et sont valides pour les nouveaux appels ou messages instantanés qui ne sont pas démarrés à partir d’un thread préexistant. Il décrit le client recevant un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur à gauche, à un utilisateur de destinataire dans le client sur la droite.

Les messages envoyés aux utilisateurs de TeamsOnly sont toujours routés vers Teams. Les messages envoyés aux\* utilisateurs de marketing sont toujours routés vers Skype entreprise, si la conversation est possible comme décrit ci-dessus. Les messages envoyés aux îlots utilisateurs seront toujours routés vers le client à partir duquel ils ont été envoyés.

Les tableaux ci-dessous indiquent le client dans un mode donné qui reçoit un appel de la part de l’expéditeur (trois colonnes la plus à gauche), en fonction du mode de l’expéditeur, du client choisi et de l’endroit où le client Skype entreprise est hébergé (locaux ou en ligne).

Dans les tableaux ci-dessous : 
- **Marketing\* ** représente l’un des modes suivants : *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- Le *texte en italique* met en évidence une conversation d’interopérabilité.

- Il n’est **pas possible** de représenter une situation dans laquelle la discussion ou l’appel n’est pas possible. Le créateur doit utiliser Skype entreprise plutôt que dans ces cas-là. C’est l’une des raisons pour lesquelles les instructions d’ordre normatif de Microsoft pour les clients locaux/hybrides est d’utiliser un autre mode que les îlots (généralement SfBWithTeamsCollab) comme point de départ de la mise à niveau vers Teams.

**Tableau 1a : nouvelle conversation ou routage d’appel vers un destinataire du mode insulaire**

| <br/><br/> Veille | Autorité <br/><br/> Client | <br/><br/> Marketing&nbsp;famille | | Destinataire <br/><br/> Île  |
|--- |--- |--- |--- |--- |
| Île | Teams <br/> Skype Entreprise<br/> Teams<br/> Skype Entreprise| En ligne<br/> En ligne<br/> Locaux<br/>Locaux| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype Entreprise<br/> Teams<br/> Skype Entreprise|
|Marketing\* <br/> | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Locaux<br/> |&boxv;<br/>&boxv;|Skype Entreprise<br/>Skype Entreprise<br/>|
|TeamsOnly |Équipes| Online<br/>|&boxv;<br/>|Équipes|
| | | | | |

**Tableau 1b : nouvelle conversation ou routage d’appel dans un destinataire dans un mode marketing\***

| <br/><br/> Veille   | Autorité <br/><br/> Client | <br/><br/> Marketing&nbsp;famille | |   Destinataire <br/><br/> Marketing\*   |
|--- |--- |--- |---   |--- |
| Île |Teams<br/>Skype Entreprise<br/>Teams <br/>Skype Entreprise  |En ligne<br/> En ligne<br/> Locaux<br/> Locaux<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise<br/> **Ce n’est pas possible** <br/>Skype Entreprise<br/> |
|Marketing\* <br/> | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Locaux<br/> |&boxv;<br/>&boxv; |  Skype Entreprise<br/>Skype Entreprise<br/> |
|TeamsOnly |Équipes| Online<br/>|&boxv;<br/> |  *Skype Entreprise* <br/>| 
| | | | | |

**Tableau 1C : nouvelle conversation ou routage d’appel en mode TeamsOnly sur un client**

| <br/><br/> Veille   | Autorité <br/><br/> Client | <br/><br/> Marketing&nbsp;famille | |   Destinataire <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Île   |Équipes<br/>Skype Entreprise<br/>Teams <br/>Skype Entreprise<br/>|En ligne<br/> En ligne<br/> Locaux<br/> Locaux<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Équipes <br/>*Teams* <br/>Équipes <br/>*Teams*  |
|Marketing\*  | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Locaux<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Équipes | Online |  &boxv; |Équipes   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Routage fédéré pour de nouvelles conversations ou appels
  
Les tableaux ci-dessous capturent le routage des appels et des discussions fédéré et sont valides pour les nouveaux appels ou les discussions. Ils indiquent quel client recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur à gauche, à un utilisateur cible fédéré sur la droite.

En résumé, si la conversation est possible comme décrit ci-dessus, les messages envoyés aux utilisateurs de TeamsOnly seront toujours terrains dans Teams. les messages envoyés aux\* utilisateurs de marketing seront toujours dans Skype entreprise. les messages envoyés aux îlots utilisateurs seront toujours terrains dans Skype entreprise, quel que soit le client à partir duquel ils ont été envoyés. L’acheminement pour les conversations et les appels fédérés est différent du routage dans le client au sein desquels les utilisateurs peuvent toujours bénéficier d’une communication fédérée dans Skype entreprise.

En effet, nous ne sommes pas en mesure de supposer qu’un partenaire Skype entreprise fédéré utilise déjà teams s’il est en mode îlot. Îles est le mode par défaut, mais nous ne pouvons pas supposer que tous les utilisateurs des îles exécutent Teams. En routant vers Skype entreprise, nous assurons qu’aucune communication avec un utilisateur d’îlot ne fonctionne. S’il est routé vers Teams, cette communication peut être manquée si la cible n’a pas utilisé Teams. Le routage vers Skype entreprise garantit que le message sera toujours reçu.  

> [!NOTE]
> La mise en œuvre actuelle de la Fédération teams repose sur la Fédération Skype entreprise, elle tire donc parti de l’infrastructure d’interopérabilité (qui nécessite que le client de l’expéditeur soit en ligne pure ou Skype entreprise hybride) et dispose d’un ensemble de fonctionnalités réduites par rapport à un thread natif. Nous nous attendons d’offrir des équipes natives à Teams, à partir du moment où le thread sera natif et fournira des fonctionnalités complètes.

Les tableaux ci-dessous décrivent le client recevant un appel de la part de l’expéditeur (trois colonnes la plus à gauche), en fonction du mode de l’expéditeur, du client choisi et de l’emplacement de l’hébergement du client Skype entreprise (locaux ou en ligne).

**Tableau 2a : nouvelle conversation ou routage d’appel vers un destinataire d’îlots**

| <br/><br/>Veille   | Autorité<br/><br/> Client| <br/><br/>Marketing famille| | Destinataire<br/><br/> Île |
|--- |--- |--- |--- |--- |
| Île |Équipes<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise  |En ligne<br/> En ligne<br/> Locaux<br/> Locaux<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise <br/> **Ce n’est pas possible**   <br/> Skype Entreprise |
| Marketing\* |Skype Entreprise <br/>Skype Entreprise |Online<br/> Locaux<br/> | &boxv;<br/>&boxv;|Skype Entreprise <br/>Skype Entreprise |
| TeamsOnly |Équipes |Online| &boxv;|*Skype Entreprise* |
|  | | | | 

**Tableau 2b : nouvelle conversation ou routage d’appel vers un destinataire dans un mode\* marketing**

| <br/><br/>Veille   | Autorité<br/><br/> Client| <br/><br/>Marketing famille| |  Destinataire<br/><br/> Marketing\* |  
|--- |--- |--- |--- |--- |
| Île |Équipes<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise <br/>|En ligne<br/> En ligne<br/> Locaux<br/> Locaux<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise <br/> **Ce n’est pas possible** <br/>Skype Entreprise <br/> |  
| Marketing\* |Skype Entreprise <br/>Skype Entreprise  |Online<br/> Locaux<br/>  |&boxv;<br/>&boxv; | Skype Entreprise <br/>Skype Entreprise  |
| TeamsOnly | Équipes|Online |&boxv; |*Skype Entreprise*  |
|  | | | | |

**Tableau 2C : nouvelle conversation ou routage d’appel vers un destinataire du mode TeamsOnly**

| <br/><br/>Veille | Autorité<br/><br/> Client| <br/><br/>Marketing famille| |  Destinataire<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Île  |Équipes<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise <br/>|En ligne<br/> En ligne<br/> Locaux<br/> Locaux<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Équipes <br/>*Teams* <br/>**Ce n’est pas possible** <br/>*Teams* |
| Marketing\* |Skype Entreprise <br/>Skype Entreprise  | Online<br/> Locaux| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Équipes |Online |&boxv; |Équipes |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et appels à partir de fils préexistants

### <a name="from-teams"></a>À partir d’équipes

Les appels ou les discussions lancés à partir d’un thread persistant préexistant dans teams seront routés de la même manière que ce thread, si cette option de routage est toujours disponible.

Si le thread persistant préexistant dans Teams était un thread natif (routé vers Teams), des messages de conversation et des appels supplémentaires depuis ce thread seront placés dans Teams. S’il s’agissait d’un thread d’interopérabilité (routé vers Skype entreprise), des messages et appels supplémentaires seront acheminés vers Skype entreprise (en supposant que les options de routage sont disponibles).

> [!NOTE]
> Il est possible que les threads préexistant dans Teams ne soient plus routables, par exemple lorsque le thread est un thread d’interopérabilité pour un utilisateur qui est désormais mis à niveau vers Teams. Étant donné qu’il a été créé comme thread d’interopérabilité, le thread devait être routé vers Skype entreprise, mais cet utilisateur ne peut plus utiliser Skype entreprise pour la discussion et les appels. Dans ce cas, le thread sera désactivé et ne permettra plus de communication.

### <a name="from-skype-for-business"></a>À partir de Skype entreprise

Les threads Skype entreprise ne persistent pas au-delà du délai d’expiration de session SIP de 10 minutes. Les conversations et les appels à partir d’un thread existant dans Skype entreprise avant la date d’expiration de la session SIP seront routés comme le thread. Les appels et les messages instantanés à partir d’une conversation existante dans Skype entreprise au-delà du délai d’expiration de la session SIP seront routés vers Skype entreprise de la part de la partie distante, quel que soit le client d’origine du thread de l’autre partie.

### <a name="availability"></a>Disponibilité

Les comportements dans le client et fédéré décrits ci-dessus sont disponibles, avec les limitations suivantes :

- Les participants externes dont les clients résident dans un déploiement GoLocal différent ou la géographie ne verront pas la discussion par messagerie instantanée pendant une réunion fédérée.
- La Fédération et l’interopérabilité entre un client O365 et un Cloud souverain ne sont pas pris en charge

## <a name="presence"></a>Présence

Si certains de vos utilisateurs utilisent le client teams et que d’autres personnes utilisent le client Skype entreprise, il est possible que vous ayez un certain nombre d’utilisateurs qui utilisent les deux clients. Vous voulez tout de même que les États de présence soient partagés avec tous les utilisateurs, sans tenir compte du client qu’un utilisateur particulier possède. Lorsque celle-ci est partagée au sein de l’organisation, les utilisateurs peuvent mieux déterminer s’il est approprié de lancer une conversation ou de passer un appel.

Par exemple, si une discussion ou un appel d’un expéditeur doit débarquer sur le client Skype entreprise de la cible, il s’agit de la présence du client Skype entreprise qui devrait être affichée auprès de l’expéditeur. S’il devrait débarquer sur le client teams de la cible, c’est la présence du client teams qui doit être affichée.

Pour savoir quel comportement vous attend, vous devez comprendre que la présence est partagée en fonction du mode de coexistence d’un utilisateur :

* Si un utilisateur est en mode TeamsOnly, tout autre utilisateur (dans teams ou Skype entreprise) verra la présence des équipes des utilisateurs TeamsOnly
* Si un utilisateur se trouve dans l’un des\* modes marketing (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), tout autre utilisateur (dans teams ou Skype entreprise) verra la présence de l'\* utilisateur
* Si un utilisateur est en mode îlots (ou hérité), la présence dans teams et la présence dans Skype entreprise est indépendante (les valeurs ne correspondent pas), et les autres utilisateurs peuvent voir l’utilisateur de l’îlot de travail, selon qu’ils se trouvent dans le même client ou dans un client fédéré et quel client ils utilisent
    * À partir de teams, tout autre utilisateur au sein d’un même client verra la présence des équipes de l’utilisateur de l’îlot ; Ceci est aligné avec la table de routage dans le client ci-dessus.
    * À partir de teams, tout utilisateur d’un client fédéré verra la présence de l’utilisateur de l’îlot. Ceci est aligné avec la table de routage fédérée ci-dessus.
    * À partir de Skype entreprise, tout autre utilisateur verra la présence Skype entreprise de l’utilisateur (à la fois dans le client et fédéré); elle est alignée avec les tables de routage ci-dessus.


### <a name="in-tenant-presence"></a>Présence dans le client

Les messages envoyés aux utilisateurs de TeamsOnly seront toujours en équipe. Les messages envoyés aux\* utilisateurs de marketing seront toujours disponibles dans Skype entreprise, si la conversation est possible comme décrit ci-dessus. Les messages envoyés aux îlots utilisateurs s’afficheront toujours dans le client à partir duquel ils ont été créés.

Le tableau décrit la présence de l’éditeur qui sera vue par un observateur, en fonction du mode de l’éditeur et du client de l’observateur (pour un nouveau thread).

**Tableau 3 : présence dans le client (nouveau thread)**

|Observateurs <br/><br/>Client| |<br/><br/>Île |Publisher <br/><br/>Marketing\* |<br/>Équipes uniquement|
|--- |--- |--- |--- |---|
|Skype Entreprise |&boxv;|Skype Entreprise | Skype Entreprise | Teams|
|Teams |&boxv; |Teams |Skype Entreprise |Teams |
| | | | |

### <a name="federated-presence"></a>Présence fédérée

La présence fédérée repose sur l’accessibilité fédérée figurant dans le tableau 2.

Le tableau ci-dessous décrit la présence de l’éditeur qui sera visible par un observateur, en fonction du mode de l’éditeur et du client de l’observateur (pour un nouveau thread). Dans la pratique, le client de l’observateur n’apporte aucune différence dans la Fédération à ce stade.

**Tableau 4 : présence fédérée (nouveau thread)**

|Observateurs <br/><br/> Client | |<br/><br/> Île  |Publisher <br/><br/> Marketing\* |<br/><br/> Équipes uniquement |
|--- |--- |--- |--- |---|
|Skype Entreprise |&boxv; |Skype Entreprise  | Skype Entreprise  | Teams  |
|Teams | &boxv;|Skype Entreprise |Skype Entreprise |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Présence dans les threads préexistants

Pour aligner la présence et l’accessibilité dans des threads préexistants, la présence de Target exposée dans ce thread doit être alignée sur le routage du thread, en partant du principe que le routage est possible.

Par exemple, si un destinataire du thread de conversation d’interopérabilité persistant a été mis à niveau vers Teams, ce thread ne reflétera plus une présence précise et ne pourra plus être routable. Commencez un nouveau thread.

## <a name="related-links"></a>Liens connexes
[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Vidéo : gérer la coexistence et l’interopérabilité entre marketing et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
