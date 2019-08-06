---
title: Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Recommandations pour la gestion de la transition vers teams dans Skype entreprise
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6656cab6918cfa0b04da28f0197137a300bbf79
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207191"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise

> [!Tip] 
> Regardez la session suivante pour en savoir plus sur la [coexistence et l’interopérabilité](https://aka.ms/teams-upgrade-coexistence-interop)

Dans le cadre de la prise en main de Skype entreprise, les administrateurs peuvent gérer l’utilisation des utilisateurs au sein de leur organisation en utilisant le concept du mode de coexistence "qui est une propriété de TeamsUpgradePolicy. Le mode de gestion de l’interopérabilité et de la migration permet aux administrateurs de gérer le passage de Skype entreprise à Teams.  Le mode utilisateur détermine dans quel client les discussions entrantes et les appels terrestres, ainsi que dans quel service (teams ou Skype entreprise) de nouvelles réunions sont prévues. Il définit également les fonctionnalités disponibles dans le client Teams. 


## <a name="fundamental-concepts"></a>Concepts de base

1.  *Interopérabilité* : 1 à 1 communication entre un utilisateur Lync/Skype entreprise et un utilisateur de teams.

2.  *Fédération* : communication entre les utilisateurs de différents clients.

3.  Tous les utilisateurs d’teams disposent d’un compte Skype entreprise sous-jacent qui est «hébergé» en ligne ou en local:
    - Les utilisateurs de Skype entreprise Online utilisent leur compte en ligne existant.
    - Les utilisateurs qui utilisent déjà Skype entreprise/Lync local utilisent leur compte local existant.
    - Les utilisateurs pour lesquels nous ne parvenons pas à détecter un compte Skype entreprise existant disposent d’un compte Skype entreprise Online configuré automatiquement lors de la création de l’utilisateur Teams.

4.  Si vous disposez d’un déploiement local de Skype entreprise ou Lync et que vous voulez que ces utilisateurs soient équipes, vous devez au minimum vous assurer qu’Azure AD Connect est en cours de synchronisation de l’attribut msRTCSIP-DeploymentLocator dans AAD, de sorte que teams/Skype entreprise Online détecte correctement votre environnement local. Par ailleurs, pour déplacer des utilisateurs vers le mode équipes uniquement (c.-à-d. mettre à jour un utilisateur), *vous devez d’abord configurer le mode hybride Skype entreprise*. Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour Skype entreprise et teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect).

5.  L’interopérabilité entre les équipes et les utilisateurs Skype entreprise n’est possible que *si l’utilisateur de teams est connecté en ligne dans Skype entreprise*. L’utilisateur Skype entreprise du destinataire peut être hébergé sur site (et nécessite la configuration de Skype entreprise hybride) ou en ligne. Les utilisateurs qui sont hébergés dans Skype entreprise local peuvent utiliser teams en mode îlot (défini plus loin dans ce document), mais ils ne peuvent pas utiliser teams pour effectuer une interopérabilité ou fédérer avec d’autres utilisateurs de Skype entreprise.  

6.  Le comportement de mise à niveau et d’interopérabilité est déterminé en fonction du mode de coexistence d’un utilisateur, décrit plus bas. Le mode est géré par TeamsUpgradePolicy. 

7.  La mise à niveau d’un utilisateur vers le mode TeamsOnly vous permet de vous assurer que toutes les conversations et tous les appels entrants s’afficheront toujours dans le client teams de l’utilisateur, quel que soit le client dont il provient. Ces utilisateurs configureront également toutes les nouvelles réunions dans Teams. Pour être en mode TeamsOnly, l’utilisateur doit être hébergé en ligne dans Skype entreprise. Cela est nécessaire pour garantir l’interopérabilité, la Fédération et l’administration complète de l’utilisateur Teams. Pour mettre à niveau un utilisateur vers TeamsOnly:
    - Si l’utilisateur est hébergé dans Skype entreprise Online (ou s’il n’en possède jamais un), accordez-lui TeamsUpgradePolicy avec le mode = TeamsOnly à l’aide de l’instance «UpgradeToTeams» à l’aide de PowerShell, ou utilisez le centre d’administration teams pour sélectionner le mode TeamsOnly.
    - Si l’utilisateur est résident sur site, utilisez `Move-CsUser` l’un des outils d’administration locaux pour le déplacer vers Skype entreprise online.  Si vous avez Skype entreprise Server 2019 ou CU8 pour Skype entreprise Server 2015, vous pouvez spécifier le `-MoveToTeams` commutateur `Move-CsUser` pour déplacer l’utilisateur directement vers équipes dans le cadre de la migration en ligne. Cette option permet également de migrer les réunions des utilisateurs vers Teams. Si `-MoveToTeams` n’est pas spécifié ou n’est pas disponible `Move-CsUser` , une fois que vous avez terminé, attribuez le mode TeamsOnly à cet utilisateur à l’aide de PowerShell ou du centre d’administration Teams. Pour plus d’informations, voir [déplacer des utilisateurs entre le Cloud local et le Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).  Pour plus d’informations sur la migration de réunion, voir [utilisation du service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

8.  Pour utiliser le système Microsoft Phone avec Teams, les utilisateurs doivent être en mode TeamsOnly (c’est-à-dire hébergés dans Skype entreprise Online et mis à niveau vers Teams), et ils doivent être configurés pour le [routage direct](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) du système Microsoft Phone (qui vous permet d’utiliser le système téléphonique avec vos propres lignes SIP et SBC) ou avoir un plan d’appels d’Office 365. Le routage direct du système Microsoft Phone n’est pas pris en charge en mode îlot.    

9.  La planification de réunions d’équipes avec l’audioconférence (appel entrant ou sortant par RTC) est disponible, que l’utilisateur soit ou non à domicile dans Skype entreprise Online ou Skype entreprise sur site. 


## <a name="coexistence-modes"></a>Modes de coexistence

L’interopérabilité et la migration sont gérées en fonction du «mode coexistence» à l’aide de TeamsUpgradePolicy. Les modes de coexistence fournissent aux utilisateurs finaux une connaissance simple et prévisible de la transition de Skype entreprise à Teams. Dans le cas d’une organisation migrant vers Teams, le mode TeamsOnly est la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas être assignés TeamsOnly (ou n’importe quel mode) en même temps. Dans le cas où les utilisateurs accèdent au mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour garantir une communication prévisible entre les utilisateurs TeamsOnly et ceux qui ne le sont pas encore.


D’un point de vue technique, le mode d’un utilisateur gouverne plusieurs aspects de l’utilisation de l’utilisateur:

- *Routage entrant*: le client (teams ou Skype entreprise) effectue-t-il des conversations et des appels entrants? 
- *Publication de présence*: est-ce que la présence de l’utilisateur est visible par les autres utilisateurs en fonction de leur activité dans teams ou Skype entreprise? 
- *Planification de réunion*: quel service est utilisé pour planifier de nouvelles réunions et vérifier que le complément approprié est présent dans Outlook? Notez que TeamsUpgradePolicy ne gouverne pas la participation à une réunion. Les utilisateurs peuvent toujours *participer* à une réunion, qu’il s’agisse d’une réunion Skype entreprise ou d’une réunion Teams.
- *Interface utilisateur*: quelles fonctionnalités sont disponibles dans équipes et/ou client Skype entreprise? Les utilisateurs peuvent-ils lancer des appels et des conversations dans Teams, Skype entreprise ou les deux? Les équipes & canaux sont-elles disponibles?  

Pour plus d’informations sur le comportement de routage et de présence en fonction du mode, voir [coexistence avec Skype entreprise](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

Néanmoins, du point de vue de l’utilisateur, le mode de vision peut être plus simplement décrit en définissant l’interface pour:
- *Discussions et appels*: quel client utilise-t-il?
- *Planification des réunions*: les utilisateurs peuvent-ils planifier de nouvelles réunions en équipe ou en réunion Skype entreprise?
- *Disponibilité des fonctionnalités de collaboration dans le client teams*. Les équipes & canaux et fichiers sont-elles disponibles lorsque les utilisateurs disposent toujours de Skype entreprise?

Les modes sont indiqués ci-dessous.
</br>
</br>

|Veille|Appels et discussions|Planification des réunions<sup>1</sup>|Équipes & canaux|Cas d’utilisation|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Nécessite la maison dans Skype entreprise Online*|Teams|Teams|Oui|État final de la mise à niveau. Il s’agit également de la valeur par défaut pour les nouveaux clients avec <500 de sièges.|
|Archipels|Ou|Ou|Oui|Configuration par défaut. Autorise un utilisateur unique à évaluer les deux clients côte à côte. Les conversations et les appels peuvent débarquer dans les deux clients, de sorte que les utilisateurs doivent toujours exécuter les deux clients. Pour éviter toute confusion ou régression de Skype entreprise, les communications externes, les services vocaux RTC et les applications vocales, l’intégration d’Office et plusieurs autres intégrations continuent d’être gérées par Skype entreprise.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Entreprise|Équipes|Oui|«Réunions en premier». Principalement pour les organisations locales à tirer parti des fonctionnalités de réunion d’équipes, si elles ne sont pas encore prêtes à migrer les appels vers le Cloud.|
|SfBWithTeamsCollab|Skype Entreprise|Skype Entreprise|Oui|Point de départ alternatif pour les organisations complexes nécessitant un contrôle administratif plus étroit.|
|SfBOnly|Skype Entreprise|Skype Entreprise|No<sup>3</sup>|Scénario spécialisé pour les organisations présentant des exigences strictes en matière de contrôle des données. Teams permet uniquement de participer à des réunions planifiées par d’autres personnes.|
||||||

</br>
</br>

**Notes**

<sup>1</sup> la possibilité de rejoindre une réunion existante (programmée dans teams ou dans Skype entreprise) n’est pas régie par le mode. Par défaut, les utilisateurs peuvent toujours rejoindre une réunion à laquelle ils ont été invités.

<sup>2</sup> par défaut, lors de l’attribution de TeamsOnly ou SfbWithTeamsCollabAndMeetings à un utilisateur individuel, toutes les réunions Skype entreprise existantes planifiées par l’utilisateur pour l’avenir sont converties en réunions Teams. Si vous le souhaitez, vous pouvez conserver ces réunions en tant que réunions Skype entreprise `-MigrateMeetingsToTeams $false` en spécifiant lors de l’attribution de TeamsUpgradePolicy ou en désélectionnant la case à cocher dans le portail d’administration Teams.   Notez que la possibilité de convertir des réunions à partir de Skype entreprise en équipes n’est pas avaialble lorsque vous accordez TeamsUpgradePolicy en fonction du client. 

<sup>3</sup> actuellement, teams n’a pas la possibilité de désactiver les fonctionnalités d’équipes et de canaux de manière à ce que cette option reste activée pour le moment.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: gestion de la migration et de la coexistence

TeamsUpgradePolicy expose deux propriétés principales: mode et NotifySfbUsers. 
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(par défaut en italique)|Description|
|---|---|---|---|
|Veille|Énumération|*Archipels*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indique le mode dans lequel le client doit s’exécuter.|
|NotifySfbUsers|Bool|*Faux* ou vrai|Indique s’il faut afficher une bannière dans le client Skype entreprise informant l’utilisateur que teams va bientôt remplacer Skype entreprise. Cela ne peut pas être vrai si le mode = TeamsOnly.|
|||||

Teams fournit toutes les instances pertinentes d’TeamsUpgradePolicy par le biais de stratégies intégrées et en lecture seule. Par conséquent, seules les cmdlets Get et Grant sont disponibles. Les instances intégrées sont répertoriées ci-dessous.
</br>
</br>

|Identity |Veille|NotifySfbUsers|
|---|---|---|
|Archipels|Archipels|False|
|IslandsWithNotify|Archipels|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Globale</br>*Par défaut*|Archipels|False|
||||

Ces instances de stratégie peuvent être accordées à des utilisateurs individuels ou en fonction du client. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) en équipes, autorisez l’instance «UpgradeToTeams»:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau le client entier, omettez le paramètre Identity de la commande Grant:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>Considérations relatives aux fédérations

La Fédération entre teams et un autre utilisateur de Skype entreprise nécessite que l’utilisateur de teams soit à domicile en ligne dans Skype entreprise. Pour le moment, les utilisateurs d’équipes travaillant dans Skype entreprise sur site pourront se fédérer avec les utilisateurs de teams uniquement.

TeamsUpgradePolicy gère le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les mêmes scénarios de client, *sauf dans le mode îlot*.  Lorsque les destinataires sont en mode îlot: 
- Discussions et appels lancés à partir de teams dans marketing si le destinataire est dans un *client fédéré*.
- Les conversations et les appels passés à partir de teams dans teams si le destinataire est dans le *même client*.
- Les conversations et les appels lancés à partir de marketing sont toujours terrains dans Skype entreprise.

Pour plus d’informations, reportez-vous à la section [coexistence avec Skype entreprise](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence).

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>Interface utilisateur du client teams lors de l’utilisation des modes marketing
Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), toutes les discussions et les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur. Pour éviter toute confusion à l’utilisateur final et garantir le routage, les appels et les discussions appropriés dans le client teams sont automatiquement désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise. De même, la planification de réunions dans teams est automatiquement désactivée lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés automatiquement lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings. Pour plus d’informations, reportez-vous à la section [découverte et conformité des modes de coexistence](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Avant la mise à disposition automatique des équipes et des canaux, les modes SfbOnly et SfBWithTeamsCollab se comportent de la même façon.


## <a name="detailed-mode-descriptions"></a>Descriptions du mode détaillé
</br>
</br>

|Veille|Explication|
|---|---|
|**Archipels**</br>définie|Un utilisateur exécute Skype entreprise et teams côte à côte. Cet utilisateur:</br><ul><li>Peut lancer des conversations et des appels VoIP dans un client Skype entreprise ou Teams. Remarque: les utilisateurs dotés de Skype entreprise sur site ne peuvent pas lancer de teams pour atteindre un autre utilisateur Skype entreprise, quel que soit le mode du destinataire.<li>Reçoit des discussions & appels VoIP lancés dans Skype entreprise par un autre utilisateur dans le client Skype entreprise.<li>Reçoit des conversations & appels VoIP lancés par un autre utilisateur dans le client d’équipes s’il se trouve dans le *même*client.<li>Reçoit des discussions & appels VoIP lancés par un autre utilisateur dans le client Skype entreprise s’il se trouve dans un client *fédéré*. <li>Est doté de la fonctionnalité RTC comme indiqué ci-dessous:<ul><li>Lorsque l’utilisateur travaille dans Skype entreprise sur site et qu’il dispose d’une voix entreprise, les appels RTC sont toujours lancés et reçus dans Skype entreprise.<li>Lorsque l’utilisateur dispose de Skype entreprise Online et dispose du système Microsoft Phone, il passe toujours et reçoit les appels RTC dans Skype entreprise:<ul><li>C’est le cas, que l’utilisateur dispose d’un forfait d’appel Microsoft ou qu’il se connecte au réseau PSTN via Skype entreprise version Cloud Connector ou un déploiement local de Skype entreprise Server (voix hybride).<li>**Remarque: le routage direct du système Microsoft teams n’est pas pris en charge en mode îlot.**</ul></ul><li>Reçoit des files d’attente d’appels Microsoft et des appels de standard automatique dans Skype entreprise.<li>Peut planifier des réunions dans teams ou Skype entreprise (et afficher les deux plug-ins par défaut).<li>Permet de participer à une réunion Skype entreprise ou Teams. la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**|Un utilisateur n’exécute que Skype entreprise. Cet utilisateur:</br><ul><li>Peut lancer des conversations et des appels à partir de Skype entreprise uniquement.<li>Reçoit une conversation ou un appel dans le client Skype entreprise, quelle que soit l’origine, sauf si l’initiateur est un utilisateur de teams avec Skype entreprise sur site. *Peut planifier uniquement des réunions Skype entreprise, mais peut participer à des réunions Skype entreprise ou Teams. <li> </br> *L’utilisation du mode îlot avec des utilisateurs locaux n’est pas recommandée en association avec d’autres utilisateurs en mode SfBOnly. S’il s’agit d’un utilisateur de teams dans lequel Skype entreprise est hébergé sur site, un appel ou une conversation à un utilisateur de SfBOnly, l’utilisateur SfBOnly n’est pas joignable et reçoit une notification d’appel manqué.|
|**SfBWithTeamsCollab**|Un utilisateur exécute Skype entreprise et teams côte à côte. Cet utilisateur:</br><ul><li>Est doté de la fonctionnalité d’un utilisateur en mode SfBOnly.<li>Équipes est activée uniquement pour la collaboration de groupe (canaux); les discussions/appels/planification des réunions sont désactivées.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|Un utilisateur exécute Skype entreprise et teams côte à côte. Cet utilisateur:<ul><li>Est doté de la fonctionnalité de conversation et d’appel de l’utilisateur en mode SfBOnly.<li>Teams est activé pour la collaboration de groupe (canaux-y compris les conversations de canal); les discussions et les appels sont désactivés.<li>Ne peut planifier que les réunions d’équipe, mais peut participer à des réunions Skype entreprise ou Teams.</ul>|
|**TeamsOnly**</br>(nécessite marketing online Home)|Un utilisateur ne exécute que Teams. Cet utilisateur:<ul><li>Reçoit les discussions et les appels dans leur client Teams, quel que soit l’endroit de l’initiation.<li>Peut lancer des conversations et des appels à partir d’équipes uniquement.<li>Peut planifier des réunions uniquement dans Teams, mais peut participer à des réunions Skype entreprise ou Teams.<li>Peut continuer à utiliser des téléphones IP Skype entreprise.<br><br>*L’utilisation du mode TeamsOnly en association avec d’autres utilisateurs en mode îlot n’est pas recommandée tant que le mode d’adoption des équipes n’est pas saturé, c’est-à-dire que le mode d’utilisation des équipes et des clients Skype entreprise est actif. Si un utilisateur de TeamsOnly entame un appel ou une conversation à un utilisateur de l’archipel, cet appel ou la conversation sera effectué sur le client teams de l’utilisateur de l’îlot; Si l’utilisateur de l’îlot n’utilise pas ou ne surveille aucune équipe, il apparaît hors ligne et ne peut pas être joint par l’utilisateur TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Voir aussi

[Coexistence avec Skype Entreprise](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Expérience client Teams et conformité aux modes coexistence](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
