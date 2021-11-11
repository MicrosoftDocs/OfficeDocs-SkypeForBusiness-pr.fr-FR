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
description: Comportement de coexistence entre Teams & Skype Entreprise, y compris le routage des paramètres, le routage des & d’appel, les conversations & appels à partir de threads pré-existants, & présence.
ms.openlocfilehash: 1ed59546d871a7ac375061714ceedd67086818d1
ms.sourcegitcommit: 2ce417430b2aac770997daaf5ef5d844aa97fd84
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60911828"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

La coexistence et l’interopérabilité entre Skype Entreprise et Teams clients sont contrôlées par les modes de coexistence. Pour plus d’informations, consultez les conseils sur la migration et l’interopérabilité pour les organisations qui [utilisent Teams avec d Skype Entreprise.](migration-interop-guidance-for-teams-with-skype.md) Après la mise à Skype Entreprise Online le 31 juillet 2021, les utilisateurs qui erront dans le cloud seront toujours des utilisateurs de TeamsOnly. Il n’est plus possible d’attribuer un mode de coexistence autre que TeamsOnly à un utilisateur en ligne. Les modes de coexistence autres que TeamsOnly sont uniquement pertinents pour les organisations ayant des déploiements locaux d’Skype Entreprise Server ou de Lync Server 2013. Dans cet article, toute référence à « Skype Entreprise Server » s’applique également à Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Détermination du mode de coexistence d’un utilisateur
Tous les utilisateurs dans les organisations sans déploiement local de Skype Entreprise Server sont en mode TeamsOnly, et le mode effectif du client est également TeamsOnly. Cela peut être confirmé en regardant la propriété TeamsUpgradeEffectiveMode sur le client ou l’utilisateur à l’aide Teams PowerShell.   Avant l’retrait d’Skype Entreprise Online le 31 juillet 2021, les organisations avaient la possibilité de modifier le mode de coexistence pour l’utilisateur ou le client. Ce n’est plus possible sauf pour les organisations avec un déploiement local de Skype Entreprise Server, qui ne doivent pas avoir un mode TeamsOnly à l’échelle du client. Vous pouvez vérifier que le mode coexistence ne peut plus être modifié si TeamsUpgradePolicyIsReadOnly = « ModeAndNotifications » sur l’utilisateur ou le client.  (TeamsUpgradePolicyIsReadOnly sur un utilisateur aura la même valeur que la valeur du client.)  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

Dans une organisation avec un déploiement local de Skype Entreprise Server, la stratégie globale du client pour TeamsUpgradePolicy peut avoir n’importe quel mode autre que *TeamsOnly.* Les modes autorisés sont *: SfBOnly,* *SfBWithTeamsCollab* et *SfBWithTeamsCollabAndMeetings.* Les utilisateurs peuvent également se voir directement attribuer une instance de TeamsUpgradePolicy, ce qui serait la stratégie globale du client.  Les utilisateurs qui originent dans le cloud doivent être TeamsOnly et les utilisateurs qui originent sur site doivent être n’importe quel mode autre que TeamsOnly.  Si un utilisateur ne reçoit pas d’instance de TeamsUpgradePolicy, il reçoit la valeur de la stratégie globale du client. 

## <a name="routing-parameters"></a>Paramètres de routage

Le mode de coexistence du destinataire détermine le comportement des conversations, des appels et de la présence, à la fois au sein d’un client et parmi des clients fédérés. Si l’expéditeur utilise Teams, la décision de routage est prise lors de la création d’un fil de conversation. Une fois qu’un fil de conversation est créé, son routage ne change pas et conserve la méthode de routage déterminée lors de la création du thread.

Les méthodes de routage de thread sont les autres :

- *native* pour une Teams à Teams conversation dans le client
- *interop* pour un Teams à Skype Entreprise conversation dans le client
- *natif fédéré pour* une conversation fédérée entre clients lorsque les deux utilisateurs ont le mode TeamsOnly. 
- *interop fédéré pour* une conversation fédérée entre des locataires qui utilise l’échange entre les Skype Entreprise et Teams.

> [! NOTES]
> - Les conversations natives, que ce soit dans le même client ou dans des scénarios fédérés, se produisent lorsque le récepteur et l’expéditeur ont le mode TeamsOnly. La conversation sera une expérience de conversation native, qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez l’expérience de conversation native des [utilisateurs externes (fédérés) dans Teams.](native-chat-for-external-users.md) 
> - Si l’un des participants à la conversation n’a PAS de mode TeamsOnly, la conversation est une expérience d’échange avec les messages texte uniquement.
> - Les communications fédérées entre les utilisateurs de TeamsOnly dans des nuages multi-clients et des environnements nuageux spéciaux (par exemple, les nuages du gouvernement) s’afficheront sous forme de conversations fédérées interopées.


Lors de la création d’une conversation, les facteurs déterminant la façon dont le thread est acheminé sont les suivants :

- Mode de coexistence du destinataire
- Client utilisé par l’expéditeur
- Si la conversation est en client ou fédérée
- Si la conversation est possible. Si un utilisateur dispose d’un Skype Entreprise local, il ne peut pas utiliser le client Teams pour l’interopérabilité au sein du client ou pour la fédération. Cet utilisateur peut uniquement utiliser le client Skype Entreprise’interopérabilité et de fédération. Notez que Teams à Teams communication au client est toujours possible.

## <a name="chat-and-call-routing"></a>Routage des appels et des discussions
Les tableaux ci-dessous indiquent quel client dans un mode donné recevra un appel de la part de l’origine (trois colonnes les plus à gauche). Le pointeur qui reçoit l’appel dépend du mode de l’appelant, du client choisi et de l’endroit où le compte Skype Entreprise est home (local ou en ligne).

Dans les tables qui suivent :

- **Skype Entreprise** _ représente l’un des modes suivants : _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings.*
- *Le texte en italique* met en évidence une conversation interop.
- **Impossible de** représenter une situation dans laquelle la conversation ou l’appel n’est pas possible. Dans ce cas, l’Skype Entreprise doit utiliser une Skype Entreprise' C’est l’une des raisons pour lesquelles les instructions en exposant Microsoft aux clients locaux et hybrides de Microsoft sont d’utiliser un mode autre que Islands (généralement SfBWithTeamsCollab) comme point de départ de leur parcours de mise à niveau vers Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage dans le client pour les nouvelles conversations ou appels

Les tableaux ci-dessous capturent le routage des appels et des conversations dans le client, et sont valides pour les nouveaux appels ou conversations qui ne sont pas démarrés à partir d’un fil de discussion existant. Il décrit le client qui recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur de gauche, à un utilisateur destinataire dans le client de droite.  Les messages envoyés aux utilisateurs de TeamsOnly seront toujours acheminés vers Teams. Les messages envoyés Skype Entreprise aux utilisateurs seront toujours acheminés vers Skype Entreprise. Les messages envoyés aux utilisateurs des îles seront toujours acheminés vers le même client à partir duquel ils ont été envoyés.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tableau 1a : nouvelle conversation ou routage d’appel dans le client vers un destinataire en mode TeamsOnly

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>&nbsp;Skype Entreprise origine|<br><br>Route-->|Destinataire TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;|Équipes <br> *Teams*|
|Skype Entreprise | Skype Entreprise | Sur site|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tableau 1b : nouvelle conversation dans le client ou routage d’appel vers un destinataire en mode Îles

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>&nbsp;Skype Entreprise origine|<br><br>Route-->|Destinataire d’îles|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
|Île| Équipes <br> Skype Entreprise|Sur site<br>Sur site|&boxv;<br>&boxv;| Équipes <br> Skype Entreprise|
|Skype Entreprise |Skype Entreprise | Sur site|&boxv;| Skype Entreprise|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tableau 1c : nouvelle conversation dans le client ou routage d’appel vers un destinataire dans Skype Entreprise mode d’accès

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>&nbsp;Skype Entreprise origine|<br><br>Route-->|Skype Entreprise Destinataire|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;| **Impossible** <br> Skype Entreprise|
|Skype Entreprise | Skype Entreprise| Sur site|&boxv;| Skype Entreprise|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Routage fédéré pour les nouvelles conversations ou appels

Les tableaux ci-dessous capturent le routage des appels et conversations fédérés, et sont valides pour les nouveaux appels ou les nouvelles conversations. Ils décrivent le client qui recevra un nouvel appel ou une nouvelle conversation, s’il provient d’un utilisateur sur la gauche, à un utilisateur cible fédéré sur la droite. En résumé, si la conversation est possible comme décrit ci-dessus, les messages envoyés aux utilisateurs de TeamsOnly seront toujours Teams ; les messages envoyés aux Skype Entreprise en mode utilisateur sont toujours reçus Skype Entreprise ; Les messages envoyés aux utilisateurs des îles sont toujours reçus Skype Entreprise quel que soit le client à partir duquel ils ont été envoyés. 

Le routage pour les conversations et appels fédérés diffère du routage dans le client, car les utilisateurs des îles recevront toujours une communication fédérée dans Skype Entreprise. Cela est dû au fait que le partenaire fédéré n’utilise peut-être pas encore Teams. Un routage vers Skype Entreprise’un mode d’îles garantit que les messages seront toujours reçus.  Un routage vers Teams peut entraîner une communication manquée si le destinataire prévu n’utilise pas Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tableau 2a : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode TeamsOnly

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Skype Entreprise d’origine|<br><br>Route-->|Destinataire TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
|Île|Équipes <br> Skype Entreprise|Sur site <br> Sur site|&boxv;<br>&boxv;|**Impossible** <br> *Teams*|
|Skype Entreprise |Skype Entreprise|Sur site|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tableau 2b : nouvelle conversation fédérée ou routage d’appel vers un destinataire d’îles

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Skype Entreprise d’origine|<br><br>Route-->|Destinataire d’îles|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;| **Impossible** <br> Skype Entreprise|
|Skype Entreprise |Skype Entreprise| Sur site|&boxv;| Skype Entreprise|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tableau 2c : nouvelle conversation fédérée ou nouveau routage d’appel vers un destinataire en mode Skype Entreprise instantanée

<br>

|<br><br>Mode|Originator<br><br>Client|<br><br>Skype Entreprise d’origine|<br><br>Route-->|Skype Entreprise Destinataire|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;|**Impossible** <br> Skype Entreprise|
|Skype Entreprise |Skype Entreprise|Sur site|&boxv;<br>&boxv;|Skype Entreprise|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et appels de threads pré-existants

### <a name="from-teams"></a>À partir de Teams

Les appels ou conversations démarrés à partir d’un fil de conversation Teams sont acheminés de la même façon que ce thread. Si le fil de discussion existant dans Teams était un thread natif (c’est-à-dire, acheminé vers Teams), les messages et appels de conversation supplémentaires de ce thread seront Teams. S’il s’agit d’un thread interop (c’est-à-dire, acheminé vers Skype Entreprise), d’autres messages et appels de conversation sont acheminés vers le Skype Entreprise (en supposant que des options de routage sont disponibles).

> [!NOTE]
> Il est possible pour les threads pré-existants dans Teams de ne plus être routables, par exemple, lorsque le thread était un thread interop vers un utilisateur qui a été mis à niveau vers Teams. Étant donné qu’il a été créé en tant que thread interop, le thread est acheminé jusqu’à Skype Entreprise, mais cet utilisateur ne peut plus utiliser les Skype Entreprise pour la conversation et les appels. Dans ce cas, le fil de discussion est désactivé et ne permet pas d’autres communications.

### <a name="from-skype-for-business"></a>À partir de Skype Entreprise

Skype Entreprise threads ne sont pas persistantes au-delà du délai d’délai de session SIP de 10 minutes. Les conversations et appels d’un thread existant dans Skype Entreprise avant l’expiration de la session SIP sont acheminés de la même manière que le thread. Les appels et conversations d’un fil de discussion existant dans Skype Entreprise au-delà du délai d’délai de la session SIP sont acheminés vers la Skype Entreprise distante, quel que soit le client d’origine issu du thread de l’autre partie.

## <a name="presence"></a>Présence

Dans les situations où certains utilisateurs utilisent le client Teams et d’autres utilisent le client Skype Entreprise, il est possible que certains d’entre eux utilisent les deux clients. Il est important de comprendre que la présence est publiée en fonction du mode de coexistence d’un utilisateur. Par exemple, si la conversation ou l’appel d’un créateur doit se trouver sur le client Skype Entreprise de la cible, c’est la présence du client Skype Entreprise qui doit être affichée à l’origine. Si elle doit se poser sur le client Teams cible, c’est la présence du client Teams qui doit être affichée.

La présence est partagée en fonction du mode de coexistence d’un utilisateur, comme décrit ci-dessous :

- Si un utilisateur est en mode TeamsOnly, tout autre utilisateur (que ce soit en Teams ou en Skype Entreprise) verra la présence de cet utilisateur Teams TeamsOnly
- Si un utilisateur est dans l’un des modes Skype Entreprise (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), tout autre utilisateur (que ce soit dans Teams ou Skype Entreprise) verra la présence Skype Entreprise de l’utilisateur Skype Entreprise
- Si un utilisateur est en mode Îles, la présence dans Teams et la présence dans Skype Entreprise sont indépendantes (les valeurs ne doivent pas correspondre) et les autres utilisateurs voient l’une ou l’autre présence de l’utilisateur des îles, selon qu’il se trouve dans le même client ou dans un client fédéré et quel client il utilise
  - À partir Teams, tout autre utilisateur au sein du même client verra la présence Teams de l’Teams de l’utilisateur. aligné sur la table de routage dans le client ci-dessus
  - À partir Teams, tous les autres utilisateurs d’un client fédéré voient la présence Skype Entreprise utilisateur des îles. aligné sur le tableau de routage fédéré ci-dessus
  - À partir Skype Entreprise, les autres utilisateurs verront la présence Skype Entreprise de l’utilisateur des îles (à la fois au sein du client et fédéré) ; aligné sur les tables de routage ci-dessus

### <a name="in-tenant-presence"></a>Présence dans le client

Les messages envoyés aux utilisateurs de TeamsOnly seront toujours reçus Teams. Les messages envoyés aux Skype Entreprise en mode utilisateur seront toujours reçus dans Skype Entreprise, si la conversation est possible comme décrit ci-dessus. Les messages envoyés aux utilisateurs des îles sont toujours acheminés vers le client d’où ils proviennent.

Le tableau décrit la présence du Publisher visible par un watcher, selon le mode de la Publisher et le client de l’observeur (pour une nouvelle conversation).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tableau 3 : présence dans le client (nouveau thread)

<br>

|Watcher<br><br>Client|<br><br>Route-->|<br><br>Île|Publisher<br><br>Skype Entreprise|<br>Teams Uniquement|
|---|:---:|---|---|---|
|Skype Entreprise|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
|Teams|&boxv;|Teams|Skype Entreprise|Teams|
|||||

### <a name="federated-presence"></a>Présence fédérée

La présence fédérée est basée sur la capacité d’accès fédérée affichée dans le tableau 2.  Le tableau ci-dessous décrit la présence du Publisher visible par un watcher, selon le mode de la Publisher et le client de l’observeur (pour une nouvelle conversation). Dans la pratique, le client de l’Watcher ne fait aucune différence dans la fédération à ce stade.

#### <a name="table-4-federated-presence-new-thread"></a>Tableau 4 : présence fédérée (nouveau thread)

<br>

|Watcher<br><br>Client|<br><br>Route-->|<br><br>Île|Publisher<br><br>Skype Entreprise|<br><br>Teams Uniquement|
|---|:---:|---|---|---|
|Skype Entreprise|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
|Teams|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Présence dans des threads pré-existants

Pour aligner la présence et l’accessibilité dans les threads pré-existants, la présence de la cible exposée dans ce thread doit être alignée sur le routage du thread, en supposant que le routage est possible.  En particulier, si un destinataire avec qui vous avez précédemment eu un thread de conversation permanente interop a été mis à niveau vers Teams, ce thread ne reflète plus la présence précise et ne sera plus routable. Vous devez commencer un nouveau thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Fédération et interoper avec Office 365 géré par 21Vianet

La fédération et l’interopation entre les Office 365 à plusieurs clients et Office 365 gérés par 21Vianet sont pris en charge lorsque les utilisateurs Office 365 clients multiples sont en mode Teams uniquement. Dans ce scénario, les utilisateurs de Skype Entreprise Online dans Office 365 géré par 21Vianet pourront communiquer avec Teams Seuls les utilisateurs des Office 365 à plusieurs clients par le biais de conversations et d’appels. Le tableau suivant indique les scénarios pris en charge dans cette configuration :
 
|Scénario|Origine|Destinataire|Pris en charge ?|
|---|---|---|---|
|Présence|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui<br>Oui|
|Conversation|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui(1:1 uniquement)|
|Appels audio|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui (1:1 uniquement)|
|Appels vidéo|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui (1:1 uniquement)|
|Partage d’écran|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams |Oui (via une réunion Teams promue)<br>Oui (via une réunion Skype Entreprise promue)|
|||||


## <a name="related-links"></a>Liens connexes
[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Vidéo : Gérer la coexistence et l’interopérabilité entre les Skype Entreprise et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
