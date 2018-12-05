---
title: Coexistence avec Skype Entreprise
author: jambirk
ms.author: francoid
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: Ce document décrit le comportement de la conversation, le routage des appels et la présence entre les utilisateurs des équipes et Skype pour les entreprises, de client et fédérés, selon les modes TeamsUpgrade affectés. Il inclut les optimisations de routage, le comportement de présence, ainsi que la modification du mode de TeamsUpgrade par défaut à partir de *hérité* *Îles* et la mise hors service imminente de *hérité*.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: c427f1cb342b64211aeabf042b0cb00d4a89759f
ms.sourcegitcommit: a0f2feb5d826fbb4414ac6644fdc3b65bbe224f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2018
ms.locfileid: "27156116"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

Coexistence et l’interopérabilité entre les utilisateurs et Skype pour les clients professionnels et les équipes est défini par les modes TeamsUpgrade, décrites dans la [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](migration-interop-guidance-for-teams-with-skype.md).

Mode TeamsUpgrade, par défaut ou explicitement par l’administrateur système toujours être affecté à un utilisateur donné. La valeur par défaut est *(îles)*. Les utilisateurs de la mise à niveau vers les équipes ont le mode de *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*et *SfBWithTeamsCollabAndMeetings* sont également possibles modes.

> [!NOTE]
> Mode *hérité* est déconseillé ; les utilisateurs qui ont été mode *hérité* ont été convertis en mode *(îles)* .

## <a name="routing-parameters"></a>Paramètres de routage

Le mode TeamsUpgrade du destinataire est la clé pour déterminer le comportement des conversations, appels et la présence, à la fois au sein d’un client et dans les clients fédérés.

Si l’expéditeur est à l’aide des équipes, la décision de routage est effectuée lors de la création d’un nouveau thread de conversation. Threads de conversation existants dans les équipes toujours conservent la méthode de routage déterminée lorsque le thread a été créé : prend en charge les équipes threads permanents.

 Méthodes de routage de thread sont les suivants :  

- *native* permettant aux équipes conversation équipes-client
- *interopérabilité* aux équipes de Skype pour conversation entreprise-client
- *fédérés* pour une conversation fédérée entre les clients

Les paramètres qui déterminent la méthode de routage de thread sont les suivants :

- Le mode TeamsUpgrade du destinataire
- Le client utilisé par l’expéditeur
- Si la conversation est nouveau, ou une partie d’un thread existant
- Si la conversation est fédérés ou de client
- Si la conversation est possible
    - Interopérabilité de client nécessite que le client est exclusivement en ligne ou Skype pour un environnement hybride Business. Clients purement locaux ne peut pas avoir d’interopérabilité de client.
    - Si le Skype pour un compte professionnel de l’expéditeur est hébergée sur site, que l’utilisateur ne peut pas utiliser le client d’équipes pour l’interopérabilité in client ou pour la fédération. Qui peut utiliser uniquement la Skype pour client d’entreprise pour l’interopérabilité et la fédération.
    - Aux équipes de communication équipes est toujours possible de client

> [!NOTE]
> Actuellement, toutes les fédérations impliquant des équipes exploitent le Skype pour le pipeline de fédération Business ainsi que les équipes – Skype pour l’interopérabilité de l’entreprise. Nous préparons équipes natives – fédération des équipes. Le présent document mis à jour dès la commercialisation de fédération native

# <a name="chat-and-call-routing"></a>Conversation et le routage des appels

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage des appels ou conversations nouveau client 

Les tableaux ci-dessous capturer le routage des appels et le client de conversation et sont valides pour les nouveaux appels ou des conversations qui ne sont pas démarrées à partir d’un thread préexistant. Il décrit également le client reçoit un nouvel appel ou une conversation, si à l’origine par un utilisateur à un utilisateur destinataire dans client sur la droite, gauche.

Messages envoyés aux utilisateurs TeamsOnly acheminera toujours aux équipes. Les messages envoyés au SfB\* utilisateurs acheminera toujours à Skype pour les entreprises, si la conversation n’est possible, comme indiqué ci-dessus. Messages envoyés aux utilisateurs (îles) achemine toujours sur le même client à partir de laquelle ils ont été envoyés.

Les tableaux ci-dessous montrent les clients dans un mode donné reçoit un appel à partir de l’expéditeur (trois colonnes à l’extrême gauche), selon le mode de l’expéditeur, le client choisi, et dans lequel est hébergé leur Skype pour client d’entreprise (sur prem ou en ligne).

Dans les tableaux qui suivent : 
- **SfB\* ** représente les modes suivants : *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Texte italique* met en évidence une conversation d’interopérabilité de base.

- **N’est pas Possible** représente une situation dans laquelle la conversation ou un appel n’est pas possible. L’expéditeur doit utiliser Skype pour les entreprises à la place dans ces cas. C’est une des raisons pourquoi les conseils normatifs de Microsoft pour les clients hybride/le prem consiste à utiliser un mode autre qu’îles (généralement SfBWithTeamsCollab) comme point de départ de leur parcours aux équipes de mise à niveau.

**Tableau 1 : nouvelle conversation dans le client ou un appel de routage à un destinataire de mode (îles)**

| <br/><br/> Mode | Expéditeur <br/><br/> Client | <br/><br/> SfB&nbsp;hébergés | | Destinataire <br/><br/> (Îles)  |
|--- |--- |--- |--- |--- |
| (Îles) | Teams <br/> Skype Entreprise<br/> Teams<br/> Skype Entreprise| En ligne<br/> En ligne<br/> Sur prem<br/>Sur prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype Entreprise<br/> Teams<br/> Skype Entreprise|
|SfB\* <br/> | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Sur prem<br/> |&boxv;<br/>&boxv;|Skype Entreprise<br/>Skype Entreprise<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tableau 1 b : nouvelle conversation dans le client ou un appel de routage à un destinataire dans un SfB\* mode**

| <br/><br/> Mode   | Expéditeur <br/><br/> Client | <br/><br/> SfB&nbsp;hébergés | |   Destinataire <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| (Îles) |Teams<br/>Skype Entreprise<br/>Teams <br/>Skype Entreprise  |En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise<br/> **N’est pas Possible** <br/>Skype Entreprise<br/> |
|SfB\* <br/> | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Sur prem<br/> |&boxv;<br/>&boxv; |  Skype Entreprise<br/>Skype Entreprise<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype Entreprise* <br/>| 
| | | | | |

**Tableau 1c : nouvelle conversation dans le client ou à un destinataire de mode TeamsOnly le routage d’appel**

| <br/><br/> Mode   | Expéditeur <br/><br/> Client | <br/><br/> SfB&nbsp;hébergés | |   Destinataire <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| (Îles)   |Teams<br/>Skype Entreprise<br/>Teams <br/>Skype Entreprise<br/>|En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype Entreprise<br/>Skype Entreprise<br/> | Online<br/> Sur prem<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>Fédérés de routage des appels ou conversations nouveau
  
Les tableaux ci-dessous capturer le routage des appels fédérés et de salles de conversation et sont valides pour les nouveaux appels ou des conversations. Ils décrivent le client reçoit un nouvel appel ou une conversation, si à l’origine par un utilisateur sur la gauche, à un utilisateur fédéré cible sur la droite.

En résumé, si la conversation n’est possible, comme indiqué ci-dessus, les messages envoyés aux utilisateurs TeamsOnly seront toujours atteindre dans les équipes ; les messages envoyés au SfB\* les utilisateurs seront toujours atteindre dans Skype pour les entreprises ; messages envoyés aux utilisateurs (îles) seront toujours atteindre dans Skype pour les entreprises, quel que soit le client à partir de laquelle ils ont été envoyés. Routage pour fédérés des conversations et appels diffère in client routage dans la mesure où les utilisateurs (îles) reçoit toujours une communication fédérée dans Skype pour les entreprises.

Il s’agit, car nous ne pouvons partons du principe qu’un Skype des partenaires fédéré utilise déjà équipes s’ils sont en mode (îles). (Îles) est le mode par défaut, mais nous ne pouvons supposent que tous les utilisateurs (îles) exécutent équipes. Par le routage Skype pour les entreprises, nous vous assurer qu’aucune communication à un utilisateur (îles) n’échoue. Si nous acheminés vers les équipes, que la communication peut manquer si la cible n’utilisez pas les équipes. Routage à Skype pour les entreprises garantit que le message sera toujours reçu.  

> [!NOTE]
> Implémentation en cours de fédération équipes repose sur Skype pour la fédération de l’entreprise, par conséquent, il s’appuie sur l’infrastructure d’interopérabilité (qui requiert le client de l’expéditeur s’agir pur en ligne ou Skype pour un environnement hybride Business) et fournit un jeu de fonctionnalités par rapport à un thread natif réduit. Nous prévoyons de fournir des équipes natives équipes fédération à l’avenir, à partir de laquelle le thread sera native et fournissent des fonctions complètes.

Les tableaux ci-dessous décrivent le client reçoit un appel à partir de l’expéditeur (trois colonnes à l’extrême gauche), selon le mode de l’expéditeur, choisi client, et dans lequel est hébergé leur Skype pour client d’entreprise (sur prem ou en ligne).

**Tableau 2 : fédérés nouvelle conversation ou le routage des appels à un destinataire (îles)**

| <br/><br/>Mode   | Expéditeur<br/><br/> Client| <br/><br/>SfB hébergés| | Destinataire<br/><br/> (Îles) |
|--- |--- |--- |--- |--- |
| (Îles) |Teams<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise  |En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise <br/> **N’est pas Possible**   <br/> Skype Entreprise |
| SfB\* |Skype Entreprise <br/>Skype Entreprise |Online<br/> Sur prem<br/> | &boxv;<br/>&boxv;|Skype Entreprise <br/>Skype Entreprise |
| TeamsOnly |Teams |Online| &boxv;|*Skype Entreprise* |
|  | | | | 

**2 b table : fédérés nouvelle conversation ou le routage des appels à un destinataire dans un SfB\* mode**

| <br/><br/>Mode   | Expéditeur<br/><br/> Client| <br/><br/>SfB hébergés| |  Destinataire<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| (Îles) |Teams<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise <br/>|En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype Entreprise* <br/> Skype Entreprise <br/> **N’est pas Possible** <br/>Skype Entreprise <br/> |  
| SfB\* |Skype Entreprise <br/>Skype Entreprise  |Online<br/> Sur prem<br/>  |&boxv;<br/>&boxv; | Skype Entreprise <br/>Skype Entreprise  |
| TeamsOnly | Teams|Online |&boxv; |*Skype Entreprise*  |
|  | | | | |

**Tableau 2c : fédérés nouvelle conversation ou le routage des appels à un destinataire de mode TeamsOnly**

| <br/><br/>Mode | Expéditeur<br/><br/> Client| <br/><br/>SfB hébergés| |  Destinataire<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| (Îles)  |Teams<br/>Skype Entreprise <br/>Teams <br/>Skype Entreprise <br/>|En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**N’est pas Possible** <br/>*Teams* |
| SfB\* |Skype Entreprise <br/>Skype Entreprise  | Online<br/> Sur prem| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et les appels de threads existants

### <a name="from-teams"></a>Des équipes

Les appels ou conversations lancé depuis un préexistant thread persistant dans les équipes est routé de la même manière que ce thread, si cette option de routage est toujours disponible.

Si le thread permanent existant dans les équipes a un thread natif (c'est-à-dire acheminé vers les équipes), les appels à partir de ce thread et les messages de conversation supplémentaires seront dirigés vers les équipes. S’il s’agissait d’un thread d’interopérabilité de base (c'est-à-dire acheminé vers Skype pour les entreprises), les appels et les messages de conversation supplémentaires seront dirigés vers Skype pour les entreprises (à nouveau en supposant que les options de routage sont disponibles).

> [!NOTE]
> Il est possible de threads existants dans les équipes ne peut plus être routable, telles que lorsque le thread a un thread d’interopérabilité de base à un utilisateur qui est maintenant mise à niveau pour les équipes. Car il a été créé en tant qu’un thread d’interopérabilité de base, achemine le thread à Skype pour les entreprises, mais que l’utilisateur n’est plus peut utiliser Skype pour les entreprises de conversation et d’appel. Dans ce cas, le thread sera désactivé et ne pas permettre les communications.

### <a name="from-skype-for-business"></a>À partir de Skype pour les entreprises

Skype pour les threads de l’entreprise ne sont pas conservées au-delà de l’expiration de la session SIP 10 min. Seront acheminés dans la même manière que le thread de conversations et les appels à partir d’un thread existant dans Skype pour les entreprises avant l’expiration de la session SIP. Les appels et les conversations d’un thread existant dans Skype pour les entreprises au-delà de l’expiration de la session SIP sont acheminées vers Skype de tiers pour les entreprises, quel que soit le client que le thread d’origine provenance située à l’autre partie.

## <a name="availability"></a>Disponibilité

Les deux comportements de client et fédérés décrits ci-dessus sont disponibles, ainsi que les limitations suivantes :

- Les participants externes dont les clients se trouvent dans un autre déploiement GoLocal ou zone géographique ne verra par messagerie instantanée conversation dans une réunion « fédérée »
- Fédération et l’interopérabilité entre O365 pouvant être partagée et nuages souverains n’est pas pris en charge

# <a name="presence"></a>Présence

Lorsque vous avez une situation où certains de vos utilisateurs utilisent le client d’équipes et d’autres personnes sont toujours à l’aide du Skype Business client, vous pouvez être un nombre d’utilisateurs qui utilisent les deux clients. Vous souhaitez toujours statuts de présence à partager avec tous les utilisateurs, quel que soit le client dispose d’un utilisateur individuel. Lorsque cela est partagé entre l’organisation, les utilisateurs peuvent mieux déterminer s’il convient initier une conversation ou d’émettre un appel.

Par exemple, si la conversation ou un appel d’un expéditeur doit atteindre Skype la cible pour client d’entreprise, il est le Skype de présence du client de l’entreprise qui doit être présenté à l’expéditeur. Si elle doit atteindre client des équipes de la cible, il est la présence du client les équipes qui doit être affichée.

Pour savoir quel comportement s’attendre, vous devez comprendre que la présence est partagée en fonction de cohabitation d’un utilisateur :

* Si un utilisateur est en mode TeamsOnly, un autre utilisateur (qu’il s’agisse des équipes ou Skype pour les entreprises) verront présence des équipes de cet utilisateur TeamsOnly
* Si un utilisateur est dans un de la SfB\* modes (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), puis un autre utilisateur (qu’il s’agisse des équipes ou Skype pour les entreprises) verront que SfB\* Skype de l’utilisateur pour la présence de l’entreprise
* Si un utilisateur se trouve dans (îles) (ou hérités) en mode, de présence dans les équipes et de présence dans Skype pour les entreprises sont indépendants (les valeurs n’est pas forcément) et les autres utilisateurs verront une ou autres la présence de l’utilisateur (îles), selon qu’ils sont dans le même domaine ou dans un federat client ED et dont ils utilisent des clients
    * Équipes, les autres utilisateurs au sein du même client verront présence équipes de l’utilisateur (îles) ; Il est aligné sur la table de routage dans client ci-dessus
    * Équipes, les autres utilisateurs dans un client fédéré verront Skype de l’utilisateur (îles) pour la présence de l’entreprise ; Il est aligné sur la table de routage fédérée ci-dessus
    * À partir de Skype pour les entreprises, les autres utilisateurs verront Skype de l’utilisateur (îles) pour la présence d’entreprise (dans client et fédéré) ; Il est aligné sur les tables de routage ci-dessus

> [!NOTE]
> Il s’agit d’une modification récente de l’implémentation précédente (appelée présence unifiée) montrant la présence d’un combiné, agrégée des équipes et Skype de la cible pour les clients d’entreprise. Cette approche précédente est la confusion pour les utilisateurs car elle produirait fréquemment dans l’affichage de présence précise, par exemple, un utilisateur n’est pas accessible même si leur présence montré les en ligne.

## <a name="in-tenant-presence"></a>Présence dans le client

Messages envoyés aux utilisateurs TeamsOnly seront toujours atteindre dans les équipes. Les messages envoyés au SfB\* les utilisateurs seront toujours atteindre dans Skype pour les entreprises, si la conversation n’est possible, comme indiqué ci-dessus. Messages envoyés aux utilisateurs (îles) seront toujours atteindre dans le client à partir de laquelle ils ont été à l’origine.

Le tableau décrit la présence de l’éditeur qui peuvent être vus par un observateur, selon le mode de l’éditeur et le client de l’Observateur (pour un nouveau thread).

**Tableau 3 : présence (nouveau thread) de client**

|Observateur <br/><br/>Client| |<br/><br/>(Îles) |Publisher <br/><br/>SfB\* |<br/>Équipes uniquement|
|--- |--- |--- |--- |---|
|Skype Entreprise |&boxv;|Skype Entreprise | Skype Entreprise | Teams|
|Teams |&boxv; |Teams |Skype Entreprise |Teams |
| | | | |

## <a name="federated-presence"></a>Présence fédéré

Présence fédéré est basé sur l’accessibilité fédérée indiquée dans le tableau 2.

Le tableau ci-dessous décrit la présence de l’éditeur qui peuvent être vus par un observateur, selon le mode de l’éditeur et le client de l’Observateur (pour un nouveau thread). Dans la pratique le client de l’Observateur ne fait aucune différence de fédération à ce stade.

**Tableau 4 : fédéré présence (nouveau thread)**

|Observateur <br/><br/> Client | |<br/><br/> (Îles)  |Publisher <br/><br/> SfB\* |<br/><br/> Équipes uniquement |
|--- |--- |--- |--- |---|
|Skype Entreprise |&boxv; |Skype Entreprise  | Skype Entreprise  | Teams  |
|Teams | &boxv;|Skype Entreprise |Skype Entreprise |Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Présence dans les threads existants

Pour aligner la présence et l’accessibilité dans les threads existants, la présence de la cible exposé dans cette thread a besoin d’être aligné avec le routage du thread, en supposant que le routage est possible.

En particulier, si un destinataire précédemment un thread de conversation interopérabilité permanente avec a été mis à niveau vers des équipes que thread ne reflète plus précis présence et ne pourra plus être routable. Vous devez démarrer un nouveau thread.
