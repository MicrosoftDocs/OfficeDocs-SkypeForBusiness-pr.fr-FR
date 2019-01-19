---
title: Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Conseils pour la gestion de la transition aux équipes de Skype pour les entreprises
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3c273868a07099ce0aaed60cb16e698adbdd13f
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349520"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise

> [!Tip] 
> Regarder la session suivante pour en savoir plus sur [l’interopérabilité et Coexistence](https://aka.ms/teams-upgrade-coexistence-interop)

Une organisation avec Skype pour les entreprises au démarrage d’adopter les équipes, les administrateurs peuvent gérer l’expérience utilisateur dans leur organisation en utilisant le concept de coexistence « mode », qui est une propriété de TeamsUpgradePolicy. L’utilisation du mode, administrateurs de gérer les interopérabilité et la migration qui gèrent la transition à partir de Skype pour les entreprises aux équipes.  Mode d’un utilisateur détermine dans laquelle les conversations entrantes et terrestre d’appels ainsi que dans les réunions du nouveau service (équipes ou Skype pour les entreprises) sont prévues. À l’avenir, le mode sera également être utilisé pour définir le comportement du client équipes en termes de fonctionnalité sera disponible. 


## <a name="fundamental-concepts"></a>Concepts fondamentaux

1.  *Interopérabilité* : communication 1 à 1 entre un Lync/Skype pour l’utilisateur d’entreprise et un utilisateur d’équipes.

2.  *Fédération* : Communication entre les utilisateurs à partir de différents clients.

3.  Toutes les équipes, les utilisateurs ont un Skype sous-jacente pour le compte d’entreprise qui est « hébergé » soit en ligne ou locale :
    - Les utilisateurs utilisent déjà Skype pour Business Online utilisent leur compte en ligne existant.
    - Les utilisateurs déjà à l’aide de Skype pour Business/Lync local utilisent leur compte local existant.
    - Les utilisateurs pour lesquels nous ne pouvons pas détecter un Skype existant pour le compte professionnel aura une Skype pour Business Online compte configuré automatiquement lors de la création de l’utilisateur d’équipes. Aucun Skype pour la licence entreprise n’est requis.

4.  Si vous disposez d’un déploiement local de soit Skype pour Lync ou de l’entreprise et que vous souhaitez que ces utilisateurs à des utilisateurs des équipes, vous devez au minimum vous assurer que Azure AD Connect est en cours de synchronisation du msRTCSIP-DeploymentLocator attribut dans DAS, ainsi que les équipes/Skype pour les entreprises Online correctement détecte votre environnement local. En outre, pour déplacer des utilisateurs vers les équipes seule (autrement dit, mettre à niveau un utilisateur), *vous devez d’abord configurer Skype pour le mode hybride Business*. Pour plus d’informations, voir [configurer les Azure AD Connect pour Skype pour professionnels et les équipes](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interopérabilité entre équipes et Skype pour les utilisateurs professionnels n’est possible que *Si l’utilisateur équipes est hébergé en ligne dans Skype pour les entreprises*. Le destinataire Skype pour l’utilisateur d’entreprise peut être hébergé soit localement (et nécessite la configuration Skype pour un environnement hybride Business) ou en ligne. Permettent aux utilisateurs qui sont hébergés dans Skype pour Business local équipes en mode îles (défini plus loin dans ce document), mais ils ne peuvent pas permet aux équipes interop ou fédérer avec d’autres utilisateurs qui utilisent Skype pour les entreprises.  

6.  Le comportement de mise à niveau et d’interopérabilité de base sont déterminés en fonction d’un utilisateur, qui est gérée par TeamsUpgradePolicy de cohabitation. TeamsInteropPolicy n’est plus pris en compte et accorder le mode = hérité n’est plus autorisée. 

7.  Mise à niveau d’un utilisateur vers le mode TeamsOnly garantit que tous les appels et les conversations entrantes seront toujours atteindre dans le client de l’utilisateur équipes, quel que soit le client il orignated à partir de. Ces utilisateurs seront également planifier toutes les réunions dans les équipes. Pour être en mode TeamsOnly, un utilisateur doit être hébergé en ligne dans Skype pour les entreprises. Cette opération est obligatoire pour garantir l’interopérabilité, la fédération et l’administration complète de l’utilisateur d’équipes. Mise à niveau un utilisateur vers TeamsOnly :
    - Si l’utilisateur est hébergé dans Skype pour les entreprises en ligne (ou jamais eu de n’importe quel compte Skype), leur accorder TeamsUpgradePolicy avec Mode = TeamsOnly à l’aide de l’instance de « UpgradeToTeams » à l’aide de PowerShell, ou utiliser le centre d’administration équipes pour sélectionner le mode TeamsOnly.
    - Si l’utilisateur est hébergés localement, utilisez `Move-CsUser` à partir de l’environnement local administrateur des outils pour déplacer vers le premier l’utilisateur de Skype pour Business Online. Il existe 2 options lorsque vous déplacez des utilisateurs sur site :  
     - Si vous avez Skype pour Business Server 2019 ou CU8 pour Skype pour Business Server 2015, vous pouvez spécifier le `-MoveToTeams` basculer dans `Move-CsUser` pour déplacer l’utilisateur directement aux équipes. Cette option sera également migrer des réunions de l’utilisateur aux équipes (bien que pour l’instant, migration de réunion ne fonctionne uniquement pour les clients TAP). 
      - Dans le cas contraire, après `Move-CsUser` se termine, affectez TeamsOnly mode à cet utilisateur à l’aide de PowerShell ou le centre d’administration équipes.  
     Pour plus d’informations, voir [déplacer des utilisateurs entre locaux et en nuage](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Pour plus d’informations sur la migration de la réunion, reportez-vous [à l’aide de la réunion Migration MMS (Service)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


8.  Pour utiliser les fonctionnalités de système téléphonique d’équipes avec les équipes, les utilisateurs doivent être en mode TeamsOnly (autrement dit, hébergés dans Skype pour Business Online et mis à niveau vers les équipes), et ils doivent être configurés pour le système téléphonique de Microsoft [Routage Direct](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (qui vous permet d’utiliser le système téléphonique avec vos propres jonctions SIP et SBC) ou possèdent un Office 365 appelant Plan de.   

9.  Planification de réunions d’équipes à une conférence Audio (entrant ou appel sortant via PSTN) est actuellement disponible uniquement pour les utilisateurs qui sont hébergés dans Skype pour Business Online. Appuyez sur est prise en charge pour les utilisateurs d’équipes avec un Skype locale pour le compte de l’entreprise.


## <a name="coexistence-modes"></a>Modes de coexistence

Interopérabilité et la migration sont gérés en fonction de « mode de coexistence » à l’aide de TeamsUpgradePolicy. Mode d’un utilisateur détermine :

- *Routage des télécopies entrantes*: dans quels ne client (équipes ou Skype pour les entreprises) entrant conversations et appelle terrain ? 
- *Planification de la réunion*: le service qui est utilisé pour la planification de réunions et en vous assurant que le complément approprié est présent dans Outlook. Notez que TeamsUpgradePolicy ne gère pas participer à une réunion. Les utilisateurs peuvent toujours *participer à* une réunion, qu’il s’agisse d’un Skype pour conférence Business ou équipes.
- *L’expérience client*: quelles sont les fonctionnalités sont disponible dans les équipes et/ou Skype pour client d’entreprise ? Ceci est implémenté pour le mode TeamsOnly. Prise en charge pour les autres modes est prévue pour l’avenir. 

Les modes sont répertoriés ci-dessous. SfBWithTeamsCollab et SfBWithTeamsCollabAndMeetings autorisera mixte d’utilisation de ces deux clients, mais aucune fonctionnalité qui se chevauchent. Mode (îles) permet l’utilisation de ces deux clients, mais avec chevauchement des fonctionnalités. Par exemple, en mode (îles), un utilisateur peut lancer une conversation dans soit Skype pour les équipes ou de l’entreprise, mais dans SfBWithTeamsCollab, ils peuvent uniquement converser dans Skype pour les entreprises (bien qu’ils peuvent participer à des conversations de canal équipes). Notez que le Client expeirence pour les modes SfB n’est pas encore entièrement fonctionnelle.  
</br>
</br>

|Mode|Comportement de routage|Planification de la réunion|Expérience du client|
|---|---|---|---|
|(Îles)|VOIP entrant appelle et conversations terrestre dans le même client en tant qu’expéditeur, sauf si le destinataire est fédéré et en mode (îles), auquel cas ils atterrissent SfB.<sup>1</sup>|Les deux|Les utilisateurs finaux peuvent lancer des appels et les salles de conversation à partir d’un client et permet de planifier des réunions à partir d’un client.|
|SfBOnly|Conversations et les appels entrants sont routées vers Skype pour les entreprises|Skype pour les entreprises uniquement|Les utilisateurs finaux peuvent lancer des appels et des conversations de Skype pour les entreprises et planifier uniquement Skype pour les réunions d’entreprise. (PAS ENCORE APPLIQUÉE)|
|SfBWithTeamsCollab<sup>2</sup>|Conversations et les appels entrants sont routées vers Skype pour les entreprises|Skype pour les entreprises uniquement|Les utilisateurs finaux peuvent lancer des appels et des conversations de Skype pour les entreprises et planifier uniquement Skype pour les réunions d’entreprise. Ils peuvent également utiliser des canaux dans les équipes. (PAS ENCORE APPLIQUÉE)|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Conversations et les appels entrants sont routées vers Skype pour les entreprises|Équipes uniquement|Les utilisateurs finaux peuvent passer des appels et conversations Skype pour les entreprises uniquement et uniquement à partir de planifient des réunions d’équipes. Ils peuvent participer aux conversations du canal équipes. (PAS ENCORE APPLIQUÉE)|
|TeamsOnly|Conversations et les appels entrants sont acheminées vers les équipes|Équipes uniquement|Les utilisateurs finaux peuvent lancer des appels et des conversations des équipes. Skype pour les entreprises est uniquement disponible pour participer à des réunions.|
|||||

**Notes :**

<sup>1</sup> pour plus d’informations sur PSTN d’appel, voir tableau à la fin de ce document.

<sup>2</sup> SfBWithTeamsCollab et SfBWithTeamsCollabAndMeetings ne sont pas encore exposées dans l’expérience utilisateur d’administration car ils actuellement se comportent pas différemment mode SfBOnly, à l’exception de contrôle des compléments Outlook. Une fois que l’expérience du client est remis, ces modes seront disponibles dans le portail d’administration. 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy : gestion de la migration et coexistence

TeamsUpgradePolicy expose deux propriétés principales : Mode et NotifySfbUsers. 
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(valeur par défaut en italique)|Description|
|---|---|---|---|
|Mode|Enum|*(Îles)*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indique le mode, dans que le client doit s’exécuter.|
|NotifySfbUsers|Bool|*False* ou true|Indique s’il faut afficher une bannière dans le Skype pour client Business informant l’utilisateur que les équipes remplacera bientôt Skype pour les entreprises. Il ne peut pas être la valeur true si le Mode = TeamsOnly.|
|||||

Les équipes fournit toutes les instances appropriées de TeamsUpgradePolicy par le biais des stratégies intégrées, en lecture seule. Par conséquent, obtenir uniquement et applets de commande Grant sont disponibles. Les instances intégrés sont répertoriés ci-dessous.
</br>
</br>

|Identity |Mode|NotifySfbUsers|
|---|---|---|
|(Îles)|(Îles)|False|
|IslandsWithNotify|(Îles)|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Globale</br>*Par défaut*|(Îles)|False|
||||

Ces instances de stratégie peuvent être accordées à des utilisateurs individuels ou sur un client à l’échelle. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) aux équipes, accordez l’instance « UpgradeToTeams » :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau le client entière, omettez le paramètre identity de la commande grant :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Considérations relatives à la fédération

Fédération des équipes à un autre utilisateur à l’aide de Skype entreprise requiert l’utilisateur équipes hébergés en ligne dans Skype pour les entreprises. Finalement, équipes, les utilisateurs hébergés dans Skype pour Business locale sera vous fédérer avec d’autres utilisateurs d’équipes.

TeamsUpgradePolicy gère le routage des appels et des conversations fédérées entrantes. Le comportement du routage fédéré est la même que pour les scénarios de même client, *sauf en mode (îles)*.  Lorsque les destinataires sont en mode (îles) : 
- Conversations et les appels démarrés à partir des équipes atteindre dans SfB si le destinataire se trouve dans un *client fédéré*.
- Conversations et les appels démarrés à partir des équipes atteindre dans les équipes si le destinataire se trouve dans le *même client*.
- Conversations et les appels démarrés à partir de SfB toujours atteindre dans SfB.


## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>L’utilisateur concerné client l’expérience dans les équipes lors de l’utilisation de modes SfB

Lorsque les utilisateurs dans le Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), les *fonctionnalités d’appel et de conversation dans l’application des équipes sont destinée à être désactivée*, mais actuellement il n’est pas encore désactivé. De même, lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, *planifier des réunions dans les équipes est destiné à être désactivée*, mais il n’est pas actuellement. Une solution pour fournir automatiquement cette expérience est planifiée.

Jusqu'à ce que cette solution est remise, les administrateurs peuvent appliquer l’expérience du client concerné du mode TeamsUpgradePolicy en configurant manuellement les valeurs de TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy. En outre, lorsque vous utilisez `Grant-CsTeamsUpgradePolicy` dans PowerShell, l’applet de commande vérifie automatiquement la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy à determmine si ces paramètres sont compatibles avec le mode spécifié. Si les ne sont pas configurés correctement, l’octroi réussira, mais est fourni un avertissement indiquant les paramètres ne sont pas configurés correctement. L’administrateur doit mettre à jour ultérieurement les stratégies indiqués afin d’offrir une expérience utilisateur final compatible dans les équipes. Si l’administrateur décide de vous n’avez rien à la suite de l’avertissement, les utilisateurs peuvent toujours accéder à la conversation, appel et/ou des fonctions de planification dans les équipes en fonction des valeurs de TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy, de la réunion qui peut entraîner une expérience utilisateur final confus.


`PS C:\Users\janedoe> Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab
WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.
PS C:\Users\janedoe>`


Avant la remise de l’exécution automatique du comportement du client décrite ci-dessus, chacun des modes SfB ont essentiellement les mêmes. Les modes SfBOnly, SfBWithTeamsCollab et SfBWithTeamsCollabAndMeetings sont toutes identiques dans la façon dont ils sont positionnés les conversations et les appels entrants. La seule différence pour l’instant, est dans les compléments Outlook pour les équipes et Skype pour les entreprises sont activé ou non. Jusqu'à ce que le client différenciés documenter est remis, 1 uniquement sur les modes SfB est activé dans le portail d’administration. Mais tous les modes sont disponibles dans PowerShell.


### <a name="powershell-warning-matrix"></a>Matrice d’avertissement de PowerShell

Ce tableau présente les paramètres de stratégie qui sont en cours lorsque TeamsUpgradeMode est accordé. À l’avenir, l’objectif étant pour le mode SfBOnly également désactiver canaux dans les équipes ; Toutefois, il n’existe actuellement aucun paramètre qui permet à la fonctionnalité de canaux dans les équipes à désactiver.


|**Modalité (application)**|**Policy.Setting**|
|---|---|
|Conversation|TeamsMessagingPolicy.AllowUserChat|
|Appels|TeamsCallingPolicy.AllowPrivateCalling|
|Planification de la réunion|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


Un avertissement s’affiche à l’administrateur s’il existe une déconnexion entre l’activation de la charge de travail et le mode de votre choix. Temporairement, l’administrateur doit activer/désactiver la charge de travail par le biais de la stratégie de charges de travail principal.  Une fois l’application automatique en fonction de TeamsUpgradePolicy implémentée, les avertissements PowerShell seront mis à jour pour informer l’administrateur qui applique automatiquement l’expérience du client. Dans ce cas, les valeurs de TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy restent inchangées – mais TeamsUpgradePolicy en fonction de l’expérience du client concerné est appliquée.



## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy et Mode hérité est obsolète 

TeamsInteropPolicy a été remplacée par TeamsUpgradePolicy. Tous les composants précédemment réglé TeamsInteropPolicy ont été mis à jour pour honorer TeamsUpgradePolicy au lieu de cela.  Microsoft a été précédemment introduit le mode « Hérité » dans TeamsUpgradePolicy afin de faciliter la transition entre TeamsInteropPolicy et TeamsUpgradePolicy. En mode hérité, les composants de routage qui compris TeamsUpgradePolicy seraient revenir au TeamsInteropPolicy. Routage prend maintenant entièrement en charge TeamsUpgradePolicy et mode hérité n’est plus pris en charge. *Les clients qui utilisent le mode hérité doivent mettre à jour leur configuration de TeamsUpgradePolicy d’utiliser une des autres modes.* 


### <a name="action-required-for-organizations-that-are-using-modelegacy-andor-teamsinteroppolicy"></a>Action requise pour les organisations qui utilisent le Mode = hérité et/ou TeamsInteropPolicy
Les clients qui utilisent le mode = Legacy dans TeamsUpgradePolicy (instance de stratégie = instance NoUpgrade ou stratégie = NotifyForTeams) doit mettre à jour leur configuration pour utiliser une stratégie avec un mode autre que hérité.  En outre, les clients qui utilisent TeamsInteropPolicy doivent supprimer toutes les affectations de cette stratégie dans la mesure où il n’est plus utilisé par le système.  Notez qu’il est n’est plus possible d’accorder le mode hérité. 

Actions requises :
 - Les clients qui utilisent TeamsInteropPolicy avec des utilisateurs qui se trouvent *pas* dans le mode hérité : la stratégie n’a aucun effet et recommandé de supprimer n’importe quel utilisateur affectations d’audit et d’utiliser uniquement la stratégie globale avec les valeurs par défaut.
 - Les clients qui utilisent le mode hérité avec TeamsInteropPolicy routage vers SfB (DisallowOverrideCallingSfbChatSfb) : ces organisations devraient opter pour utiliser un des modes SfB (SfBOnly, SfBWithTeamsCollab, SfbWithTeamsCollabAndMeetings) dans TeamsUpgradePolicy. À partir d’un point de vue de routage, un de ces modes se comporte comme l’utilisation du mode hérité avec TeamsInteropPolicy routage vers SfB.
  - Les clients qui utilisent le mode hérité avec TeamsInteropPolicy routage aux équipes (DisallowOverrideCallingTeamsChatTeams) : ces organisations doivent basculer en mode TeamsOnly.  Routage du point de vue que sera ont le même. Toutefois, une différence est que les utilisateurs en mode équipes uniquement ne sera plus en mesure de démarrer des conversations et les appels ni planifier des réunions dans Skype pour les entreprises. Toutefois ils peuvent tout de même rejoindre tout Skype pour une réunion d’affaires.


 **Microsoft demande que les clients suppriment toute utilisation du mode hérité par le 15 novembre 2018.** Un certain temps après, Microsoft sera suppression instances de TeamsUpgradePolicy avec mode = hérité.</br> 


## <a name="detailed-mode-descriptions"></a>Descriptions du mode détaillé
</br>
</br>

|Mode|Explication (includeding planifiée expérience du client)|
|---|---|
|**(Îles)**</br>(valeur par défaut)|Un utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :</br><ul><li>Peuvent lancer des conversations et VOIP appelle de soit Skype pour client équipes ou de l’entreprise. Remarque : Avec Skype pour les entreprises, les utilisateurs hébergés sur site ne peut pas démarrer à partir d’équipes pour atteindre une autre Skype pour l’utilisateur d’entreprise.<li>Reçoit les conversations & VOIP appelle initiées dans Skype pour les entreprises par un autre utilisateur dans leur Skype pour client d’entreprise.<li>Reçoit les conversations & VOIP appelle initiées dans les équipes par un autre utilisateur dans le client de leurs équipes s’ils sont dans le *même client*.<li>Reçoit les conversations & VOIP appelle initiées dans les équipes par un autre utilisateur dans leur Skype pour client Business s’ils sont dans un *client fédéré*. <li>Présente la fonctionnalité PSTN comme indiqué ci-dessous :<ul><li>Si l’utilisateur est hébergé dans Skype pour Business locaux, appels PSTN sont émis et reçus dans Skype pour les entreprises.<li>Si l’utilisateur est hébergé en ligne, l’utilisateur a système téléphonique, auquel cas l’utilisateur :<ul><li>Initialisation et reçoit des appels PSTN dans les équipes si l’utilisateur est configuré pour le routage Direct<li>Initialisation et reçoit des appels PSTN dans Skype pour les entreprises si l’utilisateur a un Plan d’appel MS ou se connecte au réseau RTC via un Skype pour édition dans le nuage connecteur ou un déploiement local de Skype pour Business Server (voix hybride)</ul></ul><li>Permet de planifier des réunions dans des équipes ou Skype pour les entreprises (et s’affiche les deux plug-ins par défaut).<li>Peuvent participer à n’importe quel Skype de réunion équipes ou de l’entreprise ; la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**|Un utilisateur exécute uniquement Skype pour les entreprises. Cet utilisateur :</br><ul><li>Peuvent lancer des conversations et appels Skype pour les entreprises uniquement.<li>Reçoit toute conversation/appel dans leur Skype pour client d’entreprise, quel que soit où initialisé, sauf si l’initiateur est un utilisateur d’équipes avec Skype pour les entreprises hébergés localement. * <li>Permet de planifier uniquement Skype pour les réunions d’entreprise, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise. </br> *Mode (îles) à l’aide avec des utilisateurs locaux n’est pas recommandé en combinaison avec d’autres utilisateurs en mode SfBOnly. Si un utilisateur d’équipes avec Skype pour les entreprises hébergés localement lance un appel ou une conversation à un utilisateur SfBOnly, l’utilisateur SfBOnly n’est pas accessible et reçoit un email.* conversation/appel manqué|
|**SfBWithTeamsCollab**|Un utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :</br><ul><li>Comporte des fonctionnalités d’un utilisateur en mode SfBOnly.<li>Les équipes a activé uniquement pour la collaboration de groupe (chaînes) ; planification de la conversation/appel/réunion sont désactivées.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :<ul><li>A la conversation et les fonctions d’appel de l’utilisateur en mode SfBOnly.<li>Les équipes activé pour la collaboration de groupe (canaux - inclut les conversations du canal) ; conversation et appel sont désactivées.<li>Permet de planifier des réunions d’équipes uniquement, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise.</ul>|
|**TeamsOnly**</br>(requiert SfB Online accueil)|Un utilisateur exécute uniquement les équipes. Cet utilisateur :<ul><li>Reçoit les conversations et appelle dans leur client équipes, quel que soit où initié.<li>Peuvent lancer des conversations et les appels des équipes uniquement.<li>Permet de planifier des réunions dans les équipes uniquement, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise.<li>Peut continuer à utiliser Skype pour les téléphones IP de l’entreprise.</ul> |
|||




## <a name="related-topics"></a>Rubriques connexes

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Nouvelle CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
