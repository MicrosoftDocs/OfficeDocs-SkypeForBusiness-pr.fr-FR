---
title: Coexistence avec Skype Entreprise
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Comportement de coexistence entre les & Skype Entreprise Teams, notamment les paramètres de routage, les conversations & le routage des appels, les conversations & les appels à partir de threads préexistants, & la présence.
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562393"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistence avec Skype Entreprise

La coexistence et l’interopérabilité entre les clients Skype Entreprise et Teams sont contrôlées par les modes de coexistence. Pour plus d’informations, consultez [les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md). Après la mise hors service de Skype Entreprise Online le 31 juillet 2021, les utilisateurs hébergés dans le cloud sont toujours des utilisateurs TeamsOnly. Il n’est plus possible d’attribuer un mode de coexistence autre que TeamsOnly à un utilisateur en ligne. Les modes de coexistence autres que TeamsOnly sont uniquement pertinents pour les organisations avec des déploiements locaux de Skype Entreprise Server ou Lync Server 2013. Dans cet article, toute référence à « Skype Entreprise Server » s’applique également à Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Détermination du mode de coexistence d’un utilisateur
Tous les utilisateurs d’organisations sans déploiement local de Skype Entreprise Server sont en mode TeamsOnly, et le mode effectif du locataire est également TeamsOnly. Cela peut être confirmé en examinant la propriété TeamsUpgradeEffectiveMode sur le locataire ou l’utilisateur à l’aide de Teams PowerShell.   Avant la mise hors service de Skype Entreprise Online le 31 juillet 2021, les organisations avaient la possibilité de modifier le mode de coexistence pour l’utilisateur ou le locataire. Cela n’est plus possible, à l’exception des organisations avec un déploiement local de Skype Entreprise Server, qui ne doivent pas avoir le mode à l’échelle du locataire de TeamsOnly. Vous pouvez confirmer que le mode de coexistence ne peut plus être modifié si TeamsUpgradePolicyIsReadOnly = « ModeAndNotifications » sur l’utilisateur ou le locataire.  (TeamsUpgradePolicyIsReadOnly sur n’importe quel utilisateur aura la même valeur que la valeur du locataire.)  


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

Dans une organisation avec un déploiement local de Skype Entreprise Server, la stratégie globale du locataire pour TeamsUpgradePolicy peut avoir n’importe quel mode *autre que TeamsOnly*. Les modes autorisés sont : *SfBOnly*, *SfBWithTeamsCollab* et *SfBWithTeamsCollabAndMeetings*. Les utilisateurs peuvent également se voir attribuer directement une instance de TeamsUpgradePolicy, ce qui remplacerait la stratégie globale du locataire.  Les utilisateurs hébergés dans le cloud doivent être TeamsOnly et les utilisateurs hébergés localement doivent être n’importe quel mode autre que TeamsOnly.  Si aucune instance de TeamsUpgradePolicy n’est attribuée à un utilisateur, il reçoit la valeur de la stratégie globale du locataire. 

## <a name="routing-parameters"></a>Paramètres de routage

Le mode de coexistence du destinataire détermine le comportement des conversations, des appels et de la présence, à la fois au sein d’un locataire et entre les locataires fédérés. Si l’expéditeur utilise Teams, la décision de routage est prise lors de la création d’un thread de conversation. Une fois qu’un thread de conversation est créé, son routage ne change pas et conserve la méthode de routage déterminée lors de la création du thread.

Les méthodes de routage de thread sont les suivantes :

- *natif* pour une conversation Teams vers Teams dans le locataire
- *interopérabilité* pour qu’une équipe Skype Entreprise conversation dans le locataire
- *natif fédéré* pour une conversation fédérée entre les locataires lorsque les deux utilisateurs ont le mode TeamsOnly. 
- *interopérabilité fédérée* pour une conversation fédérée entre les locataires qui repose sur l’interopérabilité entre Skype Entreprise et Teams.

> [!NOTE]
> - Les conversations natives, que ce soit dans le même locataire ou dans des scénarios fédérés, se produisent lorsque le récepteur et l’expéditeur ont le mode TeamsOnly. La conversation sera une expérience de conversation native, qui inclut toutes les fonctionnalités de messagerie et d’appel enrichies. Pour en savoir plus, lisez [l’expérience de conversation native pour les utilisateurs externes (fédérés) dans Teams](native-chat-for-external-users.md). 
> - Si l’un des participants à la conversation n’a PAS le mode TeamsOnly, la conversation est une expérience d’interopérabilité avec des messages texte uniquement.
> - Les communications fédérées entre les utilisateurs TeamsOnly dans les clouds multilocataires et les environnements cloud spéciaux (par exemple, les clouds gouvernementaux) apparaissent sous forme de conversations fédérées d’interopérabilité.


Lors de la création d’une conversation, les facteurs qui déterminent la façon dont le thread est routée sont les suivants :

- Mode de coexistence du destinataire
- Client utilisé par l’expéditeur
- Indique si la conversation est in-tenant ou fédérée
- Indique si la conversation est possible. Si un utilisateur dispose d’un compte Skype Entreprise hébergé localement, il ne peut pas utiliser le client Teams pour l’interopérabilité in-tenant ou pour la fédération. Cet utilisateur peut uniquement utiliser le client Skype Entreprise pour l’interopérabilité et la fédération. Notez que la communication Teams vers Teams est toujours possible dans le locataire.

## <a name="chat-and-call-routing"></a>Routage des conversations et des appels
Les tableaux ci-dessous indiquent quel client dans un mode donné recevra un appel de l’expéditeur (trois colonnes à gauche). Le cient qui reçoit l’appel dépend du mode de l’expéditeur, du client choisi et de l’emplacement d’accueil du compte Skype Entreprise (local ou en ligne).

Dans les tableaux suivants :

- **Skype Entreprise** _ représente l’un des modes suivants : _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *Le texte italique* met en évidence une conversation d’interopérabilité.
- **Impossible** représente une situation dans laquelle la conversation ou l’appel n’est pas possible. L’initiateur doit utiliser Skype Entreprise à la place dans ces cas. C’est l’une des raisons pour lesquelles les conseils normatifs de Microsoft pour les clients locaux et hybrides sont d’utiliser un mode autre que Islands (généralement SfBWithTeamsCollab) comme point de départ pour leur parcours de mise à niveau vers Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Routage in-tenant pour les nouvelles conversations ou appels

Les tableaux ci-dessous capturent le routage des conversations et des appels dans le locataire, et sont valides pour les nouveaux appels ou conversations qui ne sont pas démarrés à partir d’un thread préexistant. Il décrit le client qui recevra un nouvel appel ou conversation, s’il provient d’un utilisateur à gauche, à un utilisateur destinataire dans le locataire à droite.  Les messages envoyés aux utilisateurs TeamsOnly sont toujours acheminés vers Teams. Les messages envoyés aux utilisateurs Skype Entreprise sont toujours acheminés vers Skype Entreprise. Les messages envoyés aux utilisateurs islands sont toujours acheminés vers le même client à partir duquel ils ont été envoyés.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tableau 1a : Nouvelle conversation dans le locataire ou routage des appels vers un destinataire en mode TeamsOnly

<br>

|<br><br>Mode|Auteur<br><br>Client|<br><br>&nbsp;Skype Entreprise homed|<br><br>Route-->|Destinataire TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;|Équipes <br> *Teams*|
|Skype Entreprise | Skype Entreprise | Sur site|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tableau 1b : Nouvelle conversation ou routage d’appel in-tenant vers un destinataire en mode îles

<br>

|<br><br>Mode|Auteur<br><br>Client|<br><br>&nbsp;Skype Entreprise homed|<br><br>Route-->|Destinataire des îles|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
|Île| Équipes <br> Skype Entreprise|Sur site<br>Sur site|&boxv;<br>&boxv;| Équipes <br> Skype Entreprise|
|Skype Entreprise |Skype Entreprise | Sur site|&boxv;| Skype Entreprise|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tableau 1c : Nouvelle conversation dans le locataire ou routage des appels vers un destinataire en mode Skype Entreprise

<br>

|<br><br>Mode|Auteur<br><br>Client|<br><br>&nbsp;Skype Entreprise homed|<br><br>Route-->|destinataire Skype Entreprise|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;| **Impossible** <br> Skype Entreprise|
|Skype Entreprise | Skype Entreprise| Sur site|&boxv;| Skype Entreprise|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Routage fédéré pour les nouveaux conversations ou appels

Les tableaux ci-dessous capturent le routage des appels fédérés et des conversations, et sont valides pour les nouveaux appels ou conversations. Ils décrivent le client qui recevra un nouvel appel ou conversation, s’il provient d’un utilisateur de gauche, à un utilisateur cible fédéré à droite. En résumé, si la conversation est possible comme décrit ci-dessus, les messages envoyés aux utilisateurs TeamsOnly arrivent toujours dans Teams; les messages envoyés aux utilisateurs en mode Skype Entreprise arrivent toujours dans Skype Entreprise ; les messages envoyés aux utilisateurs des îles arrivent toujours dans Skype Entreprise quel que soit le client à partir duquel ils ont été envoyés. 

Le routage pour les conversations et les appels fédérés diffère du routage in-tenant, car les utilisateurs islands recevront toujours une communication fédérée dans Skype Entreprise. Cela est dû au fait que le partenaire fédéré n’utilise peut-être pas encore Teams. Le routage vers Skype Entreprise pour n’importe quel mode îles recipeint garantit que les messages seront toujours reçus.  Le routage vers Teams peut entraîner une communication manquée si le destinataire prévu n’utilise pas Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tableau 2a : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode TeamsOnly

<br>

|<br><br>Mode|Auteur<br><br>Client|<br><br>Skype Entreprise hébergé|<br><br>Route-->|Destinataire TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|Équipes|
|Île|Équipes <br> Skype Entreprise|Sur site <br> Sur site|&boxv;<br>&boxv;|**Impossible** <br> *Teams*|
|Skype Entreprise |Skype Entreprise|Sur site|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tableau 2b : nouvelle conversation fédérée ou routage d’appel vers un destinataire Islands

<br>

|<br><br>Mode|Auteur<br><br>Client|<br><br>Skype Entreprise hébergé|<br><br>Route-->|Destinataire des îles|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;| **Impossible** <br> Skype Entreprise|
|Skype Entreprise |Skype Entreprise| Sur site|&boxv;| Skype Entreprise|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tableau 2c : nouvelle conversation fédérée ou routage d’appel vers un destinataire en mode Skype Entreprise

<br>

|<br><br>Mode|Auteur<br><br>Client|<br><br>Skype Entreprise hébergé|<br><br>Route-->|destinataire Skype Entreprise|
|---|---|---|:---:|---|
|TeamsOnly|Équipes|Online|&boxv;|*Skype Entreprise*|
|Île|Équipes <br> Skype Entreprise| Sur site <br> Sur site|&boxv;<br>&boxv;|**Impossible** <br> Skype Entreprise|
|Skype Entreprise |Skype Entreprise|Sur site|&boxv;<br>&boxv;|Skype Entreprise|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Conversations et appels à partir de threads préexistants

### <a name="from-teams"></a>À partir de Teams

Les appels ou conversations démarrés à partir d’un thread de conversation préexistant dans Teams sont routées de la même manière que ce thread. Si le thread existant dans Teams était un thread natif (c’est-à-dire routée vers Teams), les messages de conversation et les appels supplémentaires de ce thread seront envoyés à Teams. S’il s’agissait d’un thread d’interopérabilité (c’est-à-dire routée vers Skype Entreprise), des messages de conversation et des appels supplémentaires sont envoyés à Skype Entreprise (en supposant que les options de routage sont disponibles).

> [!NOTE]
> Il est possible que les threads préexistants dans Teams ne soient plus routables, par exemple quand le thread était un thread d’interopérabilité vers un utilisateur qui a depuis été mis à niveau vers Teams. Étant donné qu’il a été créé en tant que thread d’interopérabilité, le thread achemine vers Skype Entreprise, mais cet utilisateur ne peut plus utiliser Skype Entreprise pour la conversation et l’appel. Dans ce cas, le thread est désactivé et n’autorise pas d’autres communications.

### <a name="from-skype-for-business"></a>À partir de Skype Entreprise

Skype Entreprise threads ne persistent pas au-delà du délai d’expiration de session SIP de 10 minutes. Les conversations et appels à partir d’un thread existant dans Skype Entreprise avant l’expiration de la session SIP seront routées de la même manière que le thread. Les appels et conversations à partir d’un thread existant dans Skype Entreprise au-delà du délai d’expiration de session SIP sont acheminés vers le Skype Entreprise de la partie distante, quel que soit le client d’origine du thread de l’autre partie.

## <a name="presence"></a>Présence

Dans les situations où certains utilisateurs utilisent le client Teams et d’autres utilisent le client Skype Entreprise, il est possible que certains de ces utilisateurs utilisent les deux clients. Il est important de comprendre que Presence est publié en fonction du mode de coexistence d’un utilisateur. Par exemple, si la conversation ou l’appel d’un expéditeur doit se poser sur le client Skype Entreprise de la cible, c’est la présence du client Skype Entreprise qui doit être affichée à l’expéditeur. S’il doit se poser sur le client Teams de la cible, c’est la présence du client Teams qui doit être affichée.

La présence est partagée en fonction du mode de coexistence d’un utilisateur, comme décrit ci-dessous :

- Si un utilisateur est en mode TeamsOnly, tout autre utilisateur (que ce soit dans Teams ou Skype Entreprise) verra cette présence Teams de l’utilisateur TeamsOnly.
- Si un utilisateur se trouve dans l’un des modes Skype Entreprise (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), tout autre utilisateur (que ce soit dans Teams ou Skype Entreprise) verra que Skype Entreprise présence Skype Entreprise de l’utilisateur
- Si un utilisateur est en mode Îles, la présence dans Teams et la présence dans Skype Entreprise sont indépendantes (les valeurs ne doivent pas correspondre) et d’autres utilisateurs verront une ou l’autre présence de l’utilisateur Islands, selon qu’ils se trouvent dans le même locataire ou dans un locataire fédéré et le client qu’ils utilisent
  - À partir de Teams, tout autre utilisateur au sein du même locataire verra la présence teams de l’utilisateur Islands ; ceci est aligné sur la table de routage dans le locataire ci-dessus
  - À partir de Teams, tout autre utilisateur dans un locataire fédéré verra la présence Skype Entreprise de l’utilisateur Islands ; il est aligné sur la table de routage fédérée ci-dessus.
  - À partir de Skype Entreprise, tout autre utilisateur verra la présence Skype Entreprise de l’utilisateur Islands (à la fois dans le locataire et fédéré) ; ceci est aligné sur les tables de routage ci-dessus

### <a name="in-tenant-presence"></a>Présence dans le locataire

Les messages envoyés aux utilisateurs TeamsOnly arrivent toujours dans Teams. Les messages envoyés aux utilisateurs en mode Skype Entreprise arrivent toujours dans Skype Entreprise, si la conversation est possible comme décrit ci-dessus. Les messages envoyés aux utilisateurs des îles arrivent toujours dans le client d’où ils proviennent.

Le tableau décrit la présence du serveur de publication qui sera visible par un Observateur, en fonction du mode du serveur de publication et du client de l’Observateur (pour un nouveau thread).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tableau 3 : présence in-tenant (nouveau thread)

<br>

|Watcher<br><br>Client|<br><br>Route-->|<br><br>Île|Publisher<br><br>Skype Entreprise|<br>Teams uniquement|
|---|:---:|---|---|---|
|Skype Entreprise|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
|Teams|&boxv;|Teams|Skype Entreprise|Teams|
|||||

### <a name="federated-presence"></a>Présence fédérée

La présence fédérée est basée sur l’accessibilité fédérée indiquée dans le tableau 2.  Le tableau ci-dessous décrit la présence du serveur de publication qui sera visible par un Observateur, en fonction du mode du serveur de publication et du client de l’Observateur (pour un nouveau thread). Dans la pratique, le client de l’Observateur ne fait aucune différence dans la fédération à ce stade.

#### <a name="table-4-federated-presence-new-thread"></a>Tableau 4 : présence fédérée (nouveau thread)

<br>

|Watcher<br><br>Client|<br><br>Route-->|<br><br>Île|Publisher<br><br>Skype Entreprise|<br><br>Teams uniquement|
|---|:---:|---|---|---|
|Skype Entreprise|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
|Teams|&boxv;|Skype Entreprise|Skype Entreprise|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Présence dans les threads préexistants

Pour aligner la présence et l’accessibilité dans les threads préexistants, la présence de la cible exposée dans ce thread doit être alignée sur le routage du thread, en supposant que le routage est possible.  En particulier, si un destinataire avec lequel vous aviez précédemment un thread de conversation d’interopérabilité permanente a été mis à niveau vers Teams, ce thread ne reflète plus la présence précise et ne sera plus routable. Vous devez démarrer un nouveau thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Fédération et interopérabilité avec Office 365 gérées par 21Vianet

La fédération et l’interopérabilité entre les Office 365 multilocataires et les Office 365 gérés par 21Vianet sont prises en charge lorsque les utilisateurs Office 365 multilocataires sont en mode Teams uniquement. Dans ce scénario, Skype Entreprise utilisateurs en ligne dans Office 365 géré par 21Vianet pourront communiquer avec les utilisateurs Teams uniquement dans des Office 365 multilocataires via des conversations et des appels. Le tableau suivant présente les scénarios pris en charge dans cette configuration :
 
|Scénario|Origine|Destinataire|Pris en charge ?|
|---|---|---|---|
|Présence|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui<br>Oui|
|Conversation|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui(1:1 uniquement)|
|Appels audio|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui (1:1 uniquement)|
|Appels vidéo|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams|Oui (1:1 uniquement)<br>Oui (1:1 uniquement)|
|Partage d’écran|Équipes <br> Skype Entreprise <br> | Skype Entreprise <br> Teams |Oui (via une réunion Teams promue)<br>Oui (par le biais d’une réunion de Skype Entreprise promue)|
|||||


## <a name="related-links"></a>Liens connexes
[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)

[Vidéo : Gérer la coexistence et l’interopérabilité entre Skype Entreprise et Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
