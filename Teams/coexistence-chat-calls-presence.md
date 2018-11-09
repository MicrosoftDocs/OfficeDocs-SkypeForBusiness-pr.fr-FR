---
title: Coexistence avec Skype pour les entreprises
author: jambirk
ms.author: francoid
manager: Serdars
ms.date: 11/7/2018
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: Ce document décrit le comportement de la conversation, le routage des appels et la présence entre les utilisateurs des équipes et Skype pour les entreprises, de client et fédérés, selon les modes TeamsUpgrade affectés. Il inclut les optimisations de routage, le comportement de présence, ainsi que la modification du mode de TeamsUpgrade par défaut à partir de *hérité* *Îles* et la mise hors service imminente de *hérité*.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0d6e4ad171ffc99e1f0aaa1c3b93e0fd61443bc
ms.sourcegitcommit: 42143176c46ba9496a0fd401c8e4774075106b98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238105"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype pour les entreprises

Coexistence et l’interopérabilité entre les équipes et Skype pour les entreprises est défini par les modes TeamsUpgrade, décrits la [Migration et l’interopérabilité pour les organisations](migration-interop-guidance-for-teams-with-skype.md)à l’aide d’équipes avec Skype pour les entreprises.

Mode TeamsUpgrade, par défaut ou explicitement par l’administrateur système toujours être affecté à un utilisateur donné. La valeur par défaut est *(îles)*. Les utilisateurs de la mise à niveau vers les équipes ont le mode de *TeamsOnly*.

> [!NOTE]
> Mode *hérité* est déconseillé ; les utilisateurs reste en mode *hérité* seront convertis en mode *(îles)* après le 15 novembre 2018.

## <a name="routing-parameters"></a>Paramètres de routage

Le mode TeamsUpgrade du destinataire est la clé pour déterminer le comportement des conversations, appels et la présence, à la fois au sein d’un client et dans les clients fédérés.

Si l’expéditeur est à l’aide des équipes, la décision de routage est effectuée lors de la création d’un nouveau thread de conversation. Threads de conversation existants dans les équipes conservent toujours la méthode de routage déterminée lorsque le thread a été créé. Les équipes prend en charge les threads permanents.

 Méthodes de routage de thread sont les suivants :  
* *native* permettant aux équipes conversation équipes-client
* *interopérabilité* aux équipes de Skype pour conversation entreprise-client
* *fédérés* pour une conversation fédérée entre les clients.

Les paramètres qui déterminent la méthode de routage de thread sont les suivants :
* Le mode TeamsUpgrade du destinataire
* Le client utilisé par l’expéditeur
* Si la conversation est nouveau, ou une partie d’un thread existant
* Si la conversation est fédérés ou de client
* Si la conversation est possible
    * Interopérabilité de client et la fédération des équipes requiert que le client de l’expéditeur est soit pur en ligne ou Skype pour un environnement hybride Business. Locataires purement locaux ne peut pas avoir de client interopérabilité ou équipes de la fédération.
    * Si le Skype pour un compte professionnel de l’expéditeur est hébergée sur site, que l’utilisateur ne peut pas utiliser le client d’équipes pour l’interopérabilité in client et pour la fédération. Que l’utilisateur doit utiliser le Skype pour client d’entreprise au lieu de cela pour l’interopérabilité et la fédération.
    * Aux équipes de communication équipes est toujours possible de client.

# <a name="chat-and-call-routing"></a>Conversation et le routage des appels

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage des appels ou conversations nouveau client 

Le tableau suivant illustre la pratique actuelle pour le client de conversation et le routage des appels. Ce tableau est valide pour les nouveaux appels ou des conversations qui ne sont pas démarrées à partir d’un thread existant préexistant. Il décrit client auquel un nouvel appel (ou chat) est acheminé, si à l’origine par un utilisateur sur la gauche, à un utilisateur de client cible sur la droite.

Messages envoyés aux utilisateurs TeamsOnly seront toujours atteindre dans les équipes. Messages envoyés aux utilisateurs SfB * seront toujours atteindre dans Skype pour les entreprises, si la conversation n’est possible, comme indiqué ci-dessus. Messages envoyés aux utilisateurs (îles) seront toujours atteindre dans le client à partir de laquelle ils ont été à l’origine.

**Tableau 1 : routage d’appel ou de nouvelle conversation dans le client**

| <br/> Mode   | À partir de&nbsp;expéditeur <br/> Client | <br/> SfB&nbsp;hébergés | | <br/> (Îles)  | Pour&nbsp;cible <br/> SfB\*   | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |--- |
| (Îles) <br/>(Îles) <br/>(Îles) <br/>(Îles)<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Teams<br/>SfB <br/>Teams <br/>SfB <br/>SfB <br/>SfB <br/>Teams|En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/> Online<br/> Sur prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>|Teams <br/> SfB <br/> Teams <br/> SfB <br/>  SfB <br/> SfB <br/> Teams | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>*SfB* <br/>  | Teams <br/>*Teams* <br/>Teams <br/>*Teams* <br/> *Teams*  <br/>*Teams* <br/>Teams <br/> |
|  | | | | | | |

Dans le tableau, SfB * représente les modes suivants : *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Texte en italique* dans le tableau indique une conversation d’interopérabilité de base.

**Mise en gras** dans la table représente une situation dans laquelle la conversation ou un appel n’est pas possible. C’est parce que l’infrastructure d’interopérabilité est uniquement disponible en ligne et requiert la Skype pour le compte professionnel associé au compte d’équipes à un compte en ligne. L’expéditeur doit utiliser Skype pour les entreprises à la place dans ces cas. Il s’agit une des raisons pour lesquelles des conseils normatifs de Microsoft pour les clients hybride/le prem à utiliser un autre mode qu’îles (généralement *SfBWithTeamsCollab*) comme point de départ de leur parcours aux équipes de mise à niveau.

## <a name="federated-routing-for-new-chats-or-calls"></a>Fédérés de routage des appels ou conversations nouveau
  
Le tableau ci-dessous capture en cours pratiques appel (et de conversation) routage fédérés. Ce tableau est valide pour les nouveaux appels ou des conversations. Il décrit client auquel un nouvel appel (ou chat) est acheminé, si à l’origine par un utilisateur sur la gauche, à un utilisateur fédéré cible sur la droite.

En résumé, si la conversation n’est possible, comme indiqué ci-dessus, les messages envoyés aux utilisateurs TeamsOnly seront toujours atteindre dans les équipes ; messages envoyés aux utilisateurs SfB * seront toujours atteindre dans Skype pour les entreprises ; messages envoyés aux utilisateurs (îles) seront toujours atteindre dans Skype pour les entreprises, quel que soit le client à partir de laquelle ils ont été à l’origine. Routage pour fédérés des conversations et appels diffère in client routage dans la mesure où les utilisateurs (îles) reçoit toujours une communication fédérée dans Skype pour les entreprises.

La cause de ce dernier point est que nous ne pouvons partons du principe qu’un Skype des partenaires fédéré utilise déjà équipes s’ils sont en mode (îles). (Îles) est le mode par défaut, mais nous ne pouvons supposent que tous les utilisateurs (îles) exécutent équipes. Par le routage Skype pour les entreprises, nous vous assurer qu’aucune communication à un utilisateur (îles) n’échoue. Si nous acheminés vers les équipes, que la communication peut manquer si la cible n’utilisez pas les équipes. Routage à Skype pour les entreprises garantit que le message sera toujours reçu.  

> [!NOTE]
> Implémentation en cours de fédération équipes repose sur Skype pour la fédération de l’entreprise, par conséquent, il s’appuie sur l’infrastructure d’interopérabilité (qui requiert le client de l’expéditeur s’agir pur en ligne ou SfB hybride) et fournit un ensemble de réduction fonctionnalités par rapport à un thread natif. Nous prévoyons de fournir des équipes natives équipes fédération à l’avenir, à partir de laquelle le thread sera native et fournissent des fonctions complètes.

**Tableau 2 : nouvelle conversation fédérée ou le routage des appels**

| <br/>Mode   | À partir de l’expéditeur<br/> Client| <br/>SfB hébergés| | <br/> (Îles) | Ciblage<br/> SfB\* | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |---|
| (Îles) <br/>(Îles) <br/>(Îles) <br/>(Îles)<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Teams<br/>SfB <br/>Teams <br/>SfB <br/>SfB <br/>SfB <br/>Teams|En ligne<br/> En ligne<br/> Sur prem<br/> Sur prem<br/> Online<br/> Sur prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/> | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/>  | Teams <br/>Teams <br/>**NA** <br/>*Les équipes <br/>équipes <br/>équipes* <br/>Teams <br/> |
|  | | | | | |

Dans le tableau, SfB * représente les modes suivants : *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Texte italique* met en évidence une conversation d’interopérabilité de base.

**Mise en gras** représente une situation dans laquelle la conversation ou un appel n’est pas possible. L’expéditeur doit utiliser Skype pour les entreprises à la place dans ces cas. Il s’agit une des raisons pour lesquelles des conseils normatifs de Microsoft pour les clients hybride/le prem à utiliser un autre mode qu’îles (généralement SfBWithTeamsCollab) comme point de départ de leur parcours aux équipes de mise à niveau.

## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et les appels de threads existants

### <a name="from-teams"></a>Des équipes

Les appels ou conversations lancé depuis un préexistant thread persistant dans les équipes est routé de la même manière que ce thread, si cette option de routage est toujours disponible. 

Si le thread permanent existant dans les équipes a un thread natif (c'est-à-dire acheminé vers les équipes), les appels à partir de ce thread et les messages de conversation supplémentaires seront dirigés vers les équipes. S’il s’agissait d’un thread d’interopérabilité de base (c'est-à-dire acheminé vers Skype pour les entreprises), les appels et les messages de conversation supplémentaires seront dirigés vers Skype pour les entreprises (à nouveau en supposant que les options de routage sont disponibles).

> [!NOTE]
> Threads existants dans les équipes peuvent ne plus être routables. Par exemple, cela peut arriver si le thread a un thread d’interopérabilité de base à un utilisateur qui est maintenant mise à niveau pour les équipes. Puisqu’il s’agit d’un thread d’interopérabilité de base, le thread de route pour Skype pour les entreprises mais que l’utilisateur n’est plus peut utiliser Skype pour les entreprises de conversation et d’appel. Dans ce cas, le thread sera désactivé et ne pas permettre les communications.

### <a name="from-skype-for-business"></a>À partir de Skype pour les entreprises

Skype pour les entreprises ne dispose pas de persistance de thread au-delà du délai d’expiration de session SIP (10 minutes). Seront acheminés dans la même manière que le thread de conversations et les appels à partir d’un thread existant dans Skype pour les entreprises avant l’expiration de la session SIP. Les appels et les conversations d’un thread existant dans Skype pour les entreprises au-delà de l’expiration de la session SIP sont acheminées vers Skype de tiers pour les entreprises, quel que soit le client que le thread d’origine provenance située à l’autre partie.

## <a name="availability"></a>Disponibilité

Le comportement de client décrit ci-dessus est disponible en production aujourd'hui.

Le comportement fédéré décrit ci-dessus est principalement disponible en production aujourd'hui. Les éléments suivants en cours de déploiement et sont uniquement disponibles pour les clients sur les premiers : 
* Fédération avec un client local avec la visibilité de présence
* Affichage des contacts fédérés dans la liste des contacts client équipes migrés
* Possibilité d’utiliser l’URI SIP ou une adresse SMTP pour découvrir un contact fédéré.

Déploiement pour ces a commencé et générale de la disponibilité est attendue avant la fin de novembre 2018.

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

|Observateur <br/>Client| |<br/>(Îles) |Publisher <br/>SfB\* |<br/>Équipes uniquement|
|--- |--- |--- |--- |---|
|SfB <br/> Teams|&boxv;<br/>&boxv;<br/> |SfB <br/>Teams | SfB <br/>SfB | Teams  <br/> Teams |
| | | | |

## <a name="federated-presence"></a>Présence fédéré

Présence fédéré est basé sur l’accessibilité fédérée indiquée dans le tableau 2.

Le tableau ci-dessous décrit la présence de l’éditeur qui peuvent être vus par un observateur, selon le mode de l’éditeur et le client de l’Observateur (pour un nouveau thread). Dans la pratique le client de l’Observateur ne fait aucune différence de fédération à ce stade.

**Tableau 4 : fédéré présence (nouveau thread)**

|Observateur <br/> Client | |<br/> (Îles)  |Publisher <br/> SfB\* |<br/> Équipes uniquement  |
|--- |--- |--- |--- |---|
|SfB <br/> Teams|&boxv;<br/>&boxv; |SfB <br/> SfB | SfB <br/> SfB | Teams <br/> Teams |
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Présence dans les threads existants

Pour aligner la présence et l’accessibilité dans les threads existants, la présence de la cible exposé dans cette thread a besoin d’être aligné avec le routage du thread, en supposant que le routage est possible.

En particulier, si un destinataire précédemment un thread de conversation interopérabilité permanente avec est par la suite mis à niveau vers des équipes que thread ne reflète plus précis présence et ne pourra plus être routable. Vous devez démarrer un nouveau thread.
