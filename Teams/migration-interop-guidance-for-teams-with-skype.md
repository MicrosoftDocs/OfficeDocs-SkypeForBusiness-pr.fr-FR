---
title: Migration et interopérabilité-Skype entreprise
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Familiarisez-vous avec les concepts de base de la gestion de la transition de votre organisation vers teams depuis Skype entreprise.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c30877a9563a5f97cbe2b4a7d5b8b136d5ec9ebd
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940554"
---
# <a name="coexistence-modes---reference"></a>Modes de coexistence-référence

Les modes de coexistence fournissent aux utilisateurs finaux une connaissance simple et prévisible de la transition de Skype entreprise à Teams. Dans le cas d’une organisation migrant vers Teams, le mode TeamsOnly est la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas être assignés TeamsOnly (ou n’importe quel mode) en même temps. Dans le cas où les utilisateurs accèdent au mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour garantir une communication prévisible entre les utilisateurs TeamsOnly et ceux qui ne le sont pas encore.

D’un point de vue technique, le mode d’un utilisateur gouverne plusieurs aspects de l’utilisation de l’utilisateur :

- *Routage entrant*: le client (teams ou Skype entreprise) effectue-t-il des conversations et des appels entrants ? 
- *Publication de présence*: est-ce que la présence de l’utilisateur est visible par les autres utilisateurs en fonction de leur activité dans teams ou Skype entreprise ? 
- *Planification de réunion*: quel service est utilisé pour planifier de nouvelles réunions et vérifier que le complément approprié est présent dans Outlook ? Notez que TeamsUpgradePolicy ne gouverne pas la participation à une réunion. Les utilisateurs peuvent toujours *participer* à une réunion, qu’il s’agisse d’une réunion Skype entreprise ou d’une réunion Teams.
- *Interface utilisateur*: quelles fonctionnalités sont disponibles dans équipes et/ou client Skype entreprise ? Les utilisateurs peuvent-ils lancer des appels et des conversations dans Teams, Skype entreprise ou les deux ? Les équipes & canaux sont-elles disponibles ?  

Pour plus d’informations sur le comportement de routage et de présence en fonction du mode, voir [coexistence avec Skype entreprise](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence).

Néanmoins, du point de vue de l’utilisateur, le mode de vision peut être plus simplement décrit en définissant l’interface pour :
- *Discussions et appels*: quel client utilise-t-il ?
- *Planification des réunions*: les utilisateurs peuvent-ils planifier de nouvelles réunions en équipe ou en réunion Skype entreprise ?
- *Disponibilité des fonctionnalités de collaboration dans le client teams*. Les équipes & canaux et fichiers sont-elles disponibles lorsque les utilisateurs disposent toujours de Skype entreprise ?

Les modes sont indiqués ci-dessous.
</br>
</br>

|Veille|Appels et discussions|Planification des réunions<sup>1</sup>|Équipes & canaux|Cas d’utilisation|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Nécessite la maison dans Skype entreprise Online*|Teams|Teams|Oui|État final de la mise à niveau. Également la valeur par défaut des nouveaux clients.|
|Île|Ou|Ou|Oui|Configuration par défaut. Autorise un utilisateur unique à évaluer les deux clients côte à côte. Les conversations et les appels peuvent débarquer dans les deux clients, de sorte que les utilisateurs doivent toujours exécuter les deux clients. Pour éviter toute confusion ou régression de Skype entreprise, les communications externes, les services vocaux RTC et les applications vocales, l’intégration d’Office et plusieurs autres intégrations continuent d’être gérées par Skype entreprise.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Entreprise|Teams|Oui|« Réunions en premier ». Principalement pour les organisations locales à tirer parti des fonctionnalités de réunion d’équipes, si elles ne sont pas encore prêtes à migrer les appels vers le Cloud.|
|SfBWithTeamsCollab|Skype Entreprise|Skype Entreprise|Oui|Point de départ alternatif pour les organisations complexes nécessitant un contrôle administratif plus étroit.|
|SfBOnly|Skype Entreprise|Skype Entreprise|No<sup>3</sup>|Scénario spécialisé pour les organisations présentant des exigences strictes en matière de contrôle des données. Teams permet uniquement de participer à des réunions planifiées par d’autres personnes.|
||||||

</br>
</br>

**Notes**

<sup>1</sup> la possibilité de rejoindre une réunion existante (programmée dans teams ou dans Skype entreprise) n’est pas régie par le mode. Par défaut, les utilisateurs peuvent toujours rejoindre une réunion à laquelle ils ont été invités.

<sup>2</sup> par défaut, lors de l’attribution de TeamsOnly ou SfbWithTeamsCollabAndMeetings à un utilisateur individuel, toutes les réunions Skype entreprise existantes planifiées par l’utilisateur pour l’avenir sont converties en réunions Teams. Si vous le souhaitez, vous pouvez conserver ces réunions en tant que réunions Skype entreprise en spécifiant  `-MigrateMeetingsToTeams $false` lors de l’attribution de TeamsUpgradePolicy ou en désélectionnant la case à cocher dans le portail d’administration Teams.   Notez que la possibilité de convertir des réunions à partir de Skype entreprise en équipes n’est pas disponible lorsque vous accordez TeamsUpgradePolicy sur un client. 

<sup>3</sup> actuellement, teams n’a pas la possibilité de désactiver les fonctionnalités d’équipes et de canaux de manière à ce que cette option reste activée pour le moment.


## <a name="using-teamsupgradepolicy"></a>Utiliser TeamsUpgradePolicy

TeamsUpgradePolicy expose deux propriétés principales : mode et NotifySfbUsers. 
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(par défaut en italique)|Description|
|---|---|---|---|
|Veille|Énumération|*Île*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indique le mode dans lequel le client doit s’exécuter.|
|NotifySfbUsers|Bool|*Faux* ou vrai|Indique s’il faut afficher une bannière dans le client Skype entreprise informant l’utilisateur que teams va bientôt remplacer Skype entreprise. Cela ne peut pas être vrai si le mode = TeamsOnly.|
|||||

Teams fournit toutes les instances pertinentes d’TeamsUpgradePolicy par le biais de stratégies intégrées et en lecture seule. Par conséquent, seules les cmdlets Get et Grant sont disponibles. Les instances intégrées sont répertoriées ci-dessous.
</br>
</br>

|Identity |Veille|NotifySfbUsers|
|---|---|---|
|Île|Île|False|
|IslandsWithNotify|Île|Vrai|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|Vrai|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|Vrai|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|Vrai|
|UpgradeToTeams|TeamsOnly|False|
|Globale</br>*Par défaut*|Île|False|
||||

Ces instances de stratégie peuvent être accordées à des utilisateurs individuels ou en fonction du client. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) en équipes, autorisez l’instance « UpgradeToTeams » :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau le client entier, omettez le paramètre Identity de la commande Grant :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Interface utilisateur du client teams lors de l’utilisation du mode Skype entreprise

Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), toutes les discussions et les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur. Pour éviter toute confusion à l’utilisateur final et garantir le routage, les appels et les discussions appropriés dans le client teams sont automatiquement désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise. De même, la planification de réunions dans teams est automatiquement désactivée lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés automatiquement lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings. Pour plus d’informations, reportez-vous à la section [découverte et conformité des modes de coexistence](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes).

> [!Note] 
> - Avant la mise à disposition automatique des équipes et des canaux, les modes SfbOnly et SfBWithTeamsCollab se comportent de la même façon.


## <a name="detailed-mode-descriptions"></a>Descriptions du mode détaillé
</br>
</br>

|Veille|Explication|
|---|---|
|**Île**</br>définie|Un utilisateur exécute Skype entreprise et teams côte à côte. Cet utilisateur :</br><ul><li>Peut lancer des conversations et des appels VoIP dans un client Skype entreprise ou Teams. Remarque : les utilisateurs dotés de Skype entreprise sur site ne peuvent pas lancer de teams pour atteindre un autre utilisateur Skype entreprise, quel que soit le mode du destinataire.<li>Reçoit des discussions & appels VoIP lancés dans Skype entreprise par un autre utilisateur dans le client Skype entreprise.<li>Reçoit des conversations & appels VoIP lancés par un autre utilisateur dans le client d’équipes s’il se trouve dans le *même*client.<li>Reçoit des discussions & appels VoIP lancés par un autre utilisateur dans le client Skype entreprise s’il se trouve dans un client  *fédéré*. <li>Est doté de la fonctionnalité RTC comme indiqué ci-dessous :<ul><li>Lorsque l’utilisateur travaille dans Skype entreprise sur site et qu’il dispose d’une voix entreprise, les appels RTC sont toujours lancés et reçus dans Skype entreprise.<li>Lorsque l’utilisateur dispose de Skype entreprise Online et dispose du système Microsoft Phone, il passe toujours et reçoit les appels RTC dans Skype entreprise :<ul><li>C’est le cas, que l’utilisateur dispose d’un forfait d’appel Microsoft ou qu’il se connecte au réseau PSTN via Skype entreprise version Cloud Connector ou un déploiement local de Skype entreprise Server (voix hybride).<li>**Remarque : le routage direct du système Microsoft teams n’est pas pris en charge en mode îlot.**</ul></ul><li>Reçoit les files d’attente d’appels Microsoft et les appels de standard automatique dans Skype entreprise :<ul><li>Les numéros de téléphone affectés aux files d’attente d’appels et aux standards automatiques **ne peuvent pas** être des numéros de routage directs du système téléphonique Microsoft teams en mode îlot.</ul></ul><li>Peut planifier des réunions dans teams ou Skype entreprise (et afficher les deux plug-ins par défaut).<li>Permet de participer à une réunion Skype entreprise ou Teams. la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**|Un utilisateur n’exécute que Skype entreprise. Cet utilisateur :</br><ul><li>Peut lancer des conversations et des appels à partir de Skype entreprise uniquement.<li>Reçoit une conversation ou un appel dans le client Skype entreprise, quelle que soit l’origine, sauf si l’initiateur est un utilisateur de teams avec Skype entreprise sur site. * <li> Peut planifier uniquement des réunions Skype entreprise, mais peut participer à des réunions Skype entreprise ou Teams. </br> \* * L’utilisation du mode îlot avec des utilisateurs locaux n’est pas recommandée en association avec d’autres utilisateurs en mode SfBOnly. S’il s’agit d’un utilisateur de teams dans lequel Skype entreprise est hébergé sur site, un appel ou une conversation à un utilisateur de SfBOnly, l’utilisateur SfBOnly n’est pas joignable et reçoit une notification d’appel manqué.|
|**SfBWithTeamsCollab**|Un utilisateur exécute Skype entreprise et teams côte à côte. Cet utilisateur :</br><ul><li>Est doté de la fonctionnalité d’un utilisateur en mode SfBOnly.<li>Équipes est activée uniquement pour la collaboration de groupe (canaux); les discussions/appels/planification des réunions sont désactivées.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Un utilisateur exécute Skype entreprise et teams côte à côte. Cet utilisateur :<ul><li>Est doté de la fonctionnalité de conversation et d’appel de l’utilisateur en mode SfBOnly.<li>Teams est activé pour la collaboration de groupe (canaux-y compris les conversations de canal); les discussions et les appels sont désactivés.<li>Ne peut planifier que les réunions d’équipe, mais peut participer à des réunions Skype entreprise ou Teams.</ul>|
|**TeamsOnly**</br>(nécessite marketing online Home)|Un utilisateur ne exécute que Teams. Cet utilisateur :<ul><li>Reçoit les discussions et les appels dans leur client Teams, quel que soit l’endroit de l’initiation.<li>Peut lancer des conversations et des appels à partir d’équipes uniquement.<li>Peut planifier des réunions uniquement dans Teams, mais peut participer à des réunions Skype entreprise ou Teams.<li>Peut continuer à utiliser des téléphones IP Skype entreprise.<br><br>*L’utilisation du mode TeamsOnly en association avec d’autres utilisateurs en mode îlot n’est pas recommandée tant que le mode d’adoption des équipes n’est pas saturé, c’est-à-dire que le mode d’utilisation des équipes et des clients Skype entreprise est actif. Si un utilisateur de TeamsOnly entame un appel ou une conversation à un utilisateur de l’archipel, cet appel ou la conversation sera effectué sur le client teams de l’utilisateur de l’îlot ; Si l’utilisateur de l’îlot n’utilise pas ou ne surveille aucune équipe, il apparaît hors ligne et ne peut pas être joint par l’utilisateur TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Sujets associés

[Coexistence avec Skype Entreprise](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Expérience client Teams et conformité aux modes coexistence](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
