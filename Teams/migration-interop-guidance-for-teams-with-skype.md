---
title: Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Conseils pour la gestion de la transition aux équipes de Skype pour les entreprises
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20516c3045fecf14757866bf076b4bf8d16adaf4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902740"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise

> [!Tip] 
> Regarder la session suivante pour en savoir plus sur [l’interopérabilité et Coexistence](https://aka.ms/teams-upgrade-coexistence-interop)

Une organisation avec Skype pour les entreprises au démarrage d’adopter les équipes, les administrateurs peuvent gérer l’expérience utilisateur dans leur organisation en utilisant le concept de coexistence « mode », qui est une propriété de TeamsUpgradePolicy. L’utilisation du mode, administrateurs de gérer les interopérabilité et la migration qui gèrent la transition à partir de Skype pour les entreprises aux équipes.  Mode d’un utilisateur détermine dans laquelle les conversations entrantes et terrestre d’appels ainsi que dans les réunions du nouveau service (équipes ou Skype pour les entreprises) sont planifiés. À l’avenir, le mode sera également être utilisé pour définir le comportement du client équipes en termes de fonctionnalité sera disponible. 


## <a name="fundamental-concepts"></a>Concepts fondamentaux

1.  *Interopérabilité* : communication 1 à 1 entre un Lync/Skype pour l’utilisateur d’entreprise et un utilisateur d’équipes.

2.  *Fédération* : Communication entre les utilisateurs à partir de différents clients.

3.  Toutes les équipes, les utilisateurs ont un Skype sous-jacente pour le compte d’entreprise qui est « hébergé » soit en ligne ou locale :
    - Les utilisateurs utilisent déjà Skype pour Business Online utilisent leur compte en ligne existant.
    - Les utilisateurs déjà à l’aide de Skype pour Business/Lync local utilisent leur compte local existant.
    - Les utilisateurs pour lesquels nous ne pouvons pas détecter un Skype existant pour le compte professionnel aura une Skype pour Business Online compte configuré automatiquement lors de la création de l’utilisateur d’équipes.

4.  Si vous disposez d’un déploiement local de soit Skype pour Lync ou de l’entreprise et que vous souhaitez que ces utilisateurs à des utilisateurs des équipes, vous devez au minimum vous assurer que Azure AD Connect est en cours de synchronisation du msRTCSIP-DeploymentLocator attribut dans DAS, ainsi que les équipes/Skype pour les entreprises Online correctement détecte votre environnement local. En outre, pour déplacer des utilisateurs vers les équipes seule (autrement dit, mettre à niveau un utilisateur), *vous devez d’abord configurer Skype pour le mode hybride Business*. Pour plus d’informations, voir [configurer les Azure AD Connect pour Skype pour professionnels et les équipes](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  Interopérabilité entre équipes et Skype pour les utilisateurs professionnels n’est possible que *Si l’utilisateur équipes est hébergé en ligne dans Skype pour les entreprises*. Le destinataire Skype pour l’utilisateur d’entreprise peut être hébergé soit localement (et nécessite la configuration Skype pour un environnement hybride Business) ou en ligne. Permettent aux utilisateurs qui sont hébergés dans Skype pour Business local équipes en mode îles (défini plus loin dans ce document), mais ils ne peuvent pas permet aux équipes interop ou fédérer avec d’autres utilisateurs qui utilisent Skype pour les entreprises.  

6.  Le comportement de mise à niveau et d’interopérabilité de base sont déterminés basée sur le mode de la Coexistence d’un utilisateur, décrit ci-dessous. Mode est géré par TeamsUpgradePolicy. TeamsInteropPolicy n’est plus pris en compte et accorder le mode = hérité n’est plus autorisée. 

7.  Mise à niveau d’un utilisateur vers le mode TeamsOnly garantit que tous les appels et les conversations entrantes seront toujours atteindre dans le client de l’utilisateur équipes, quel que soit le client provient de. Ces utilisateurs seront également planifier toutes les réunions dans les équipes. Pour être en mode TeamsOnly, un utilisateur doit être hébergé en ligne dans Skype pour les entreprises. Cette opération est obligatoire pour garantir l’interopérabilité, la fédération et l’administration complète de l’utilisateur d’équipes. Mise à niveau un utilisateur vers TeamsOnly :
    - Si l’utilisateur est hébergé dans Skype pour les entreprises en ligne (ou jamais eu de n’importe quel compte Skype), leur accorder TeamsUpgradePolicy avec Mode = TeamsOnly à l’aide de l’instance de « UpgradeToTeams » à l’aide de PowerShell, ou utiliser le centre d’administration équipes pour sélectionner le mode TeamsOnly.
    - Si l’utilisateur est hébergés localement, utilisez `Move-CsUser` à partir de l’environnement local administrateur des outils pour déplacer vers le premier l’utilisateur de Skype pour Business Online.  Si vous avez Skype pour Business Server 2019 ou CU8 pour Skype pour Business Server 2015, vous pouvez spécifier le `-MoveToTeams` basculer dans `Move-CsUser` pour déplacer l’utilisateur directement aux équipes dans le cadre du déplacement en ligne. Cette option sera également migrer des réunions de l’utilisateur aux équipes. Si `-MoveToTeams` n’est pas spécifié ou n’est disponible, puis après `Move-CsUser` se termine, affectez TeamsOnly mode à cet utilisateur à l’aide de PowerShell ou le centre d’administration équipes. Pour plus d’informations, voir [déplacer des utilisateurs entre locaux et en nuage](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Pour plus d’informations sur la migration de la réunion, reportez-vous [à l’aide de la réunion Migration MMS (Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Pour utiliser les fonctionnalités de système téléphonique d’équipes avec les équipes, les utilisateurs doivent être en mode TeamsOnly (autrement dit, hébergés dans Skype pour Business Online et mis à niveau vers les équipes), et ils doivent être configurés pour le système téléphonique de Microsoft [Routage Direct](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (qui vous permet d’utiliser le système téléphonique avec vos propres jonctions SIP et SBC) ou possèdent un Office 365 appelant Plan de.   

9.  Planification de réunions d’équipes à une conférence Audio (entrant ou appel sortant via PSTN) est désormais disponible, si l’utilisateur est hébergé dans Skype pour Business Online ou Skype pour l’entreprise locale. 


## <a name="coexistence-modes"></a>Modes de coexistence

Interopérabilité et la migration sont gérés en fonction de « mode de coexistence » à l’aide de TeamsUpgradePolicy. Modes de coexistence fournissent une expérience prévisible simple pour les utilisateurs finaux en tant que la transition des organisations de Skype pour les entreprises aux équipes. Pour une organisation déplacement aux équipes, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent être attribués TeamsOnly (ou n’importe quel mode) en même temps. Avant d’atteindre le mode TeamsOnly des utilisateurs, organisations peuvent utiliser de la Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour assurer la communication entre les utilisateurs qui sont TeamsOnly et ceux qui ne sont pas encore prévisible.


À partir d’un point de vue technique, le mode d’un utilisateur régit plusieurs aspects de l’expérience de l’utilisateur :

- *Routage des télécopies entrantes*: dans quels ne client (équipes ou Skype pour les entreprises) entrant conversations et appelle terrain ? 
- *Publication de présence*: présence de l’utilisateur qui est affiché pour les autres utilisateurs en fonction de leur activité dans des équipes ou Skype pour les entreprises ? 
- *Planification de la réunion*: le service qui est utilisé pour la planification de réunions et en vous assurant que le complément approprié est présent dans Outlook ? Notez que TeamsUpgradePolicy ne gère pas participer à une réunion. Les utilisateurs peuvent toujours *participer à* une réunion, qu’il s’agisse d’un Skype pour conférence Business ou équipes.
- *L’expérience client*: quelles sont les fonctionnalités sont disponible dans les équipes et/ou Skype pour client d’entreprise ? Les utilisateurs peuvent initier des appels et les conversations d’équipes, Skype pour les entreprises ou les deux ? Est qu'expérience des équipes & canaux disponibles ?  

Pour plus d’informations sur le comportement de routage et de présence basée sur le mode, consultez [Coexistence avec Skype pour les entreprises](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

Toutefois, du point de vue de l’expérience, mode permettre plus simplement décrits comme définissant l’expérience pour :
- *Conversation et l’appel*: le client utilise-t-il un utilisateur ?
- *Planification de la réunion*: font utilisateurs planifient des réunions nouvelles équipes ou Skype pour les réunions d’entreprise ?
- *Disponibilité des fonctionnalités de collaboration dans le client d’équipes*. Fonctionnalité équipes & canaux et les fichiers n’est disponible pendant que les utilisateurs ont toujours Skype pour les entreprises ?

Les modes sont répertoriés ci-dessous.
</br>
</br>

|Mode|Appel et conversation|Planification de réunion<sup>1</sup>|Les équipes & canaux|Cas d’utilisation|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Nécessite d’accueil dans Skype pour Business en ligne*|Teams|Teams|Oui|L’état final de la mise à niveau. Également la valeur par défaut pour les nouveaux clients avec <500 sièges.|
|(Îles)|Soit|Soit|Oui|Configuration par défaut. Permet à un utilisateur unique à évaluer les deux clients côte à côte. Conversations et les appels peuvent atteindre dans un client, afin que les utilisateurs doivent toujours exécuter les deux clients.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Entreprise|Équipes|Oui|« Réunions premier ». Principalement pour des organisations locales afin de bénéficier de fonctionnalités de réunion équipes, s’ils ne sont pas encore prêts à passer l’appel vers le nuage.|
|SfBWithTeamsCollab|Skype Entreprise|Skype Entreprise|Oui|Autre point de départ pour les organisations complexes nécessitant une plus forte du contrôle administratif.|
|SfBOnly|Skype Entreprise|Skype Entreprise|Aucun<sup>3</sup>|Spécialisés scénario pour les organisations ayant de strictes exigences de contrôle de données. Les équipes est utilisée uniquement pour participer à des réunions planifiées par d’autres personnes.|
||||||

</br>
</br>

**Notes :**

<sup>1</sup> la possibilité de participer à une réunion existante (si planifiées dans des équipes ou Skype pour les entreprises) n’est pas régie par le mode. Par défaut, les utilisateurs peuvent toujours participer à des réunions qu’ils ont été invités.

<sup>2</sup> par défaut, lorsque vous affectez TeamsOnly ou SfbWithTeamsCollabAndMeetings à un utilisateur individuel, n’importe quel Skype existant pour les réunions Business prévues par l’utilisateur dans le futur sont convertis en réunions d’équipes. Si vous le souhaitez, vous pouvez laisser quitter ces réunions en tant que Skype pour les réunions d’entreprise soit en spécifiant `-MigrateMeetingsToTeams $false` lorsque vous accordez TeamsUpgradePolicy ou en désélectionnant la case à cocher dans le portail d’administration des équipes.   Notez que la possibilité de convertir réunions Skype pour les entreprises d’équipes n’est pas disque lors de l’octroi de TeamsUpgradePolicy sur un client à l’échelle. 

<sup>3</sup> actuellement, les équipes ne dispose pas la possibilité de désactiver la fonctionnalité équipes et canaux afin que cela reste activé pour l’instant.



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

Fédération des équipes à un autre utilisateur à l’aide de Skype entreprise requiert l’utilisateur équipes hébergés en ligne dans Skype pour les entreprises. Finalement, équipes, les utilisateurs hébergés dans Skype pour Business locale sera en mesure d’établir une fédération avec des équipes uniquement les utilisateurs.

TeamsUpgradePolicy gère le routage des appels et des conversations fédérées entrantes. Le comportement du routage fédéré est la même que pour les scénarios de même client, *sauf en mode (îles)*.  Lorsque les destinataires sont en mode (îles) : 
- Conversations et les appels démarrés à partir des équipes atteindre dans SfB si le destinataire se trouve dans un *client fédéré*.
- Conversations et les appels démarrés à partir des équipes atteindre dans les équipes si le destinataire se trouve dans le *même client*.
- Conversations et les appels démarrés à partir de SfB toujours atteindre dans Skype pour les entreprises.

Pour plus d’informations, consultez [Coexistence avec Skype pour les entreprises](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>Expérience de l’utilisateur du client équipes lors de l’utilisation de modes SfB
Lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), toutes les conversations entrantes et les appels sont routés vers Skype l’utilisateur pour client d’entreprise. Pour éviter toute confusion d’utilisateur final et garantir un routage correct, les fonctionnalités d’appel et de conversation dans le client d’équipes sont désactivée lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise. De même, planifier des réunions dans les équipes est désactivé lorsque vous êtes dans les modes SfBOnly ou SfBWithTeamsCollab et explicitement activée lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings. Pour désactiver automatiquement la fonctionnalité de conversation et appel des fonctionnalités, ainsi que d’activer/désactiver basée sur le mode de planification de la réunion est désormais disponible. Pour plus d’informations sur les nouvelles fonctionnalités, voir [l’expérience client équipes et conformité aux modes de coexistence](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Avant la remise de l’exécution automatique d’équipes et les canaux, les modes SfbOnly et SfBWithTeamsCollab ont le même comportement.



## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>TeamsInteropPolicy et Mode hérité a été retirée. 

TeamsInteropPolicy a été remplacée par TeamsUpgradePolicy. Tous les composants précédemment réglé TeamsInteropPolicy ont été mis à jour pour honorer TeamsUpgradePolicy au lieu de cela. Microsoft a été précédemment introduit le mode « Hérité » dans TeamsUpgradePolicy afin de faciliter la transition entre TeamsInteropPolicy et TeamsUpgradePolicy. En mode hérité, les composants de routage qui compris TeamsUpgradePolicy seraient revenir au TeamsInteropPolicy. Routage maintenant prend totalement en charge TeamsUpgradePolicy. Mode hérité n’est plus pris en charge et il n’est plus possible d’accorder le mode hérité.


## <a name="detailed-mode-descriptions"></a>Descriptions du mode détaillé
</br>
</br>

|Mode|Explication|
|---|---|
|**(Îles)**</br>(valeur par défaut)|Un utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :</br><ul><li>Peuvent lancer des conversations et VoIP appelle de soit Skype pour client équipes ou de l’entreprise. Remarque : Avec Skype pour les entreprises, les utilisateurs hébergés sur site ne peut pas démarrer à partir d’équipes pour atteindre une autre Skype pour les utilisateurs professionnels, quel que soit le mode du destinataire.<li>Reçoit & conversations que des appels VoIP initiées dans Skype pour les entreprises par un autre utilisateur dans leur Skype pour client d’entreprise.<li>Reçoit les conversations & VoIP appelle initiées dans les équipes par un autre utilisateur dans le client de leurs équipes s’ils sont dans le *même client*.<li>Reçoit les conversations & VoIP appelle initiées dans les équipes par un autre utilisateur dans leur Skype pour client Business s’ils sont dans un *client fédéré*. <li>Présente la fonctionnalité PSTN comme indiqué ci-dessous :<ul><li>Si l’utilisateur est hébergé dans Skype pour Business locaux, appels PSTN sont émis et reçus dans Skype pour les entreprises.<li>Si l’utilisateur est hébergé en ligne, l’utilisateur a système téléphonique, auquel cas l’utilisateur :<ul><li>Initialisation et reçoit des appels PSTN dans les équipes si l’utilisateur est configuré pour le routage Direct<li>Initialisation et reçoit des appels PSTN dans Skype pour les entreprises si l’utilisateur a un Plan d’appel MS ou se connecte au réseau RTC via un Skype pour édition dans le nuage connecteur ou un déploiement local de Skype pour Business Server (voix hybride)</ul></ul><li>Permet de planifier des réunions dans des équipes ou Skype pour les entreprises (et s’affiche les deux plug-ins par défaut).<li>Peuvent participer à n’importe quel Skype de réunion équipes ou de l’entreprise ; la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**|Un utilisateur exécute uniquement Skype pour les entreprises. Cet utilisateur :</br><ul><li>Peuvent lancer des conversations et appels Skype pour les entreprises uniquement.<li>Reçoit toute conversation/appel dans leur Skype pour client d’entreprise, quel que soit où initialisé, sauf si l’initiateur est un utilisateur d’équipes avec Skype pour les entreprises hébergés localement. * <li>Permet de planifier uniquement Skype pour les réunions d’entreprise, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise. </br> *Mode (îles) à l’aide avec des utilisateurs locaux n’est pas recommandé en combinaison avec d’autres utilisateurs en mode SfBOnly. Si un utilisateur d’équipes avec Skype pour les entreprises hébergés localement lance un appel ou une conversation à un utilisateur SfBOnly, l’utilisateur SfBOnly n’est pas accessible et reçoit un email.* conversation/appel manqué|
|**SfBWithTeamsCollab**|Un utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :</br><ul><li>Comporte des fonctionnalités d’un utilisateur en mode SfBOnly.<li>Les équipes a activé uniquement pour la collaboration de groupe (chaînes) ; planification de la conversation/appel/réunion sont désactivées.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un utilisateur exécute les deux Skype pour les professionnels et les équipes côte à côte. Cet utilisateur :<ul><li>A la conversation et les fonctions d’appel de l’utilisateur en mode SfBOnly.<li>Les équipes activé pour la collaboration de groupe (canaux - inclut les conversations du canal) ; conversation et appel sont désactivées.<li>Permet de planifier des réunions d’équipes uniquement, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise.</ul>|
|**TeamsOnly**</br>(requiert SfB Online accueil)|Un utilisateur exécute uniquement les équipes. Cet utilisateur :<ul><li>Reçoit les conversations et appelle dans leur client équipes, quel que soit où initié.<li>Peuvent lancer des conversations et les appels des équipes uniquement.<li>Permet de planifier des réunions dans les équipes uniquement, mais peuvent participer à Skype pour les réunions des équipes ou de l’entreprise.<li>Peut continuer à utiliser Skype pour les téléphones IP de l’entreprise.</ul> |
|||




## <a name="related-topics"></a>Voir aussi

[Coexistence avec Skype Entreprise](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Expérience client Teams et conformité aux modes coexistence](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Utilisation du Service de Migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
