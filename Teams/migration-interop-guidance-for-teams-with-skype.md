---
title: Migration et interopérabilité - Skype Entreprise
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Comprendre les concepts fondamentaux de la gestion de la transition de votre organisation vers Teams à partir de Skype Entreprise.
ms.localizationpriority: medium
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
ms.openlocfilehash: b6c8e96c1aeb8fabcbe42ba403c51b4a8d6f4836
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657264"
---
# <a name="coexistence-modes---reference"></a>Modes de coexistence - Référence

> [!Important] 
> - Après la mise hors service de Skype Entreprise Online le 31 juillet 2021, il n’est plus possible d’attribuer un mode de coexistence autre que TeamsOnly à un utilisateur hébergé dans le cloud. Comme c’était le cas avant la mise hors service, les utilisateurs hébergés dans Skype Entreprise Server local peuvent se voir attribuer n’importe quel mode *autre que* TeamsOnly. 

Les modes de coexistence offrent une expérience simple et prévisible pour les utilisateurs finaux lorsque les organisations passent de Skype Entreprise à Teams. Pour une organisation qui passe à Teams, le mode TeamsOnly est la destination finale pour chaque utilisateur, mais tous les utilisateurs n’ont pas besoin d’être affectés à TeamsOnly (ou n’importe quel mode) en même temps. Avant que les utilisateurs atteignent le mode TeamsOnly, les organisations peuvent utiliser l’un des modes Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour garantir une communication prévisible entre les utilisateurs qui sont TeamsOnly et ceux qui ne le sont pas encore.

Du point de vue technique, le mode d’un utilisateur régit plusieurs aspects de l’expérience de l’utilisateur :

- *Routage entrant* : dans quel client (Teams ou Skype Entreprise) les conversations et les appels entrants arrivent-ils ? 
- *Publication de présence* : la présence de l’utilisateur est-elle affichée pour d’autres utilisateurs en fonction de son activité dans Teams ou Skype Entreprise ? 
- *Planification des réunions* : quel service est utilisé pour planifier de nouvelles réunions et s’assurer que le complément approprié est présent dans Outlook ? TeamsUpgradePolicy ne régit pas la participation à une réunion. Les utilisateurs peuvent toujours *participer à* n’importe quelle réunion, qu’il s’agisse d’une réunion Skype Entreprise ou d’une réunion Teams.
- *Expérience client* : Quelles sont les fonctionnalités disponibles dans Teams et/ou Skype Entreprise client ? Les utilisateurs peuvent-ils lancer des appels et des conversations dans Teams, Skype Entreprise ou les deux ? L’expérience Teams & Channels est-elle disponible ?  

Pour plus d’informations sur le routage et le comportement de présence en fonction du mode, consultez [Coexistence avec Skype Entreprise](./coexistence-chat-calls-presence.md).

Toutefois, du point de vue de l’expérience, le mode peut être décrit comme définissant l’expérience pour :
- *Conversation et appel* : quel client un utilisateur utilise-t-il ?
- *Planification des* réunions : les utilisateurs planifient-ils de nouvelles réunions en tant que réunions Teams ou Skype Entreprise ?
- *Disponibilité des fonctionnalités de collaboration dans le client Teams*. Les fonctionnalités De canaux et fichiers Teams & sont-ils disponibles alors que les utilisateurs ont toujours Skype Entreprise ?

Les modes sont répertoriés ci-dessous. Les utilisateurs du cloud doivent être TeamsOnly et les utilisateurs hébergés localement doivent être n’importe quel mode autre que TeamsOnly. 
</br>
</br>

|Mode|Appel et conversation|Planification des réunions<sup>1</sup>|Canaux de & Teams|Cas d’usage|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Possible uniquement si l’utilisateur n’a pas de compte local dans Skype Entreprise Server*|Équipes|Teams|Oui|État final de la mise à niveau. Valeur par défaut pour les nouveaux locataires, sauf si une configuration hybride est détectée.|
|Île|Soit|Soit|Oui|Configuration par défaut pour les organisations hybrides. Permet à un seul utilisateur d’évaluer les deux clients côte à côte. Les conversations et les appels peuvent arriver dans l’un ou l’autre des clients, de sorte que les utilisateurs doivent toujours exécuter les deux clients. Pour éviter une expérience Skype Entreprise déroutante ou régressée, les communications externes (fédérées), les services vocaux RTC et les applications vocales, l’intégration d’Office et plusieurs autres intégrations continuent d’être gérées par Skype Entreprise.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Entreprise|Teams|Oui|« Réunions d’abord ». Principalement pour que les organisations locales bénéficient des fonctionnalités de réunion Teams, si elles ne sont pas encore prêtes à passer des appels vers le cloud.|
|SfBWithTeamsCollab|Skype Entreprise|Skype Entreprise|Oui|Autre point de départ pour les organisations complexes qui ont besoin d’un contrôle administratif plus strict.|
|SfBOnly|Skype Entreprise|Skype Entreprise|No<sup>3</sup>|Scénario spécialisé pour les organisations qui ont des exigences strictes en matière de contrôle des données. Teams est utilisé uniquement pour participer à des réunions planifiées par d’autres personnes.|
||||||

</br>
</br>

**Notes:**

<sup>1</sup> La possibilité de participer à une réunion existante (planifiée dans Teams ou dans Skype Entreprise) n’est pas régie par le mode. Par défaut, les utilisateurs peuvent toujours participer à n’importe quelle réunion à laquelle ils ont été invités.

<sup>2</sup> Par défaut, lors de l’affectation de TeamsOnly ou de SfbWithTeamsCollabAndMeetings à un utilisateur individuel, toutes les réunions Skype Entreprise existantes planifiées par cet utilisateur pour l’avenir sont converties en réunions Teams. Si vous le souhaitez, vous pouvez laisser ces réunions comme Skype Entreprise réunions en spécifiant `-MigrateMeetingsToTeams $false` lors de l’octroi de TeamsUpgradePolicy ou en désélectionnant la case à cocher dans le portail Teams Administration. La possibilité de convertir des réunions de Skype Entreprise en Teams n’est pas disponible lors de l’octroi de TeamsUpgradePolicy à l’échelle du client. 

<sup>3</sup> Actuellement, Teams n’a pas la possibilité de désactiver les fonctionnalités Teams et Canaux. Cela reste donc activé pour l’instant.


## <a name="using-teamsupgradepolicy"></a>Utilisation de TeamsUpgradePolicy

TeamsUpgradePolicy expose deux propriétés clés : Mode et NotifySfbUsers. 
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(par défaut en italique)|Description|
|---|---|---|---|
|Mode|Enum|*Île*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indique le mode dans lequel le client doit s’exécuter.|
|NotifySfbUsers|Bool|*False* ou true|Indique s’il faut afficher une bannière dans le client Skype Entreprise informant l’utilisateur que Teams remplacera bientôt Skype Entreprise. Cela ne peut pas être vrai si Mode=TeamsOnly.|
|||||

Teams fournit toutes les instances pertinentes de TeamsUpgradePolicy via des stratégies intégrées en lecture seule. Par conséquent, seules les applets de commande Get et Grant sont disponibles. Les instances intégrées sont répertoriées ci-dessous.
</br>
</br>

|Identity |Mode|NotifySfbUsers|
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
|Global</br>*Par défaut*|Île|False|
||||

Ces instances de stratégie peuvent être accordées à des utilisateurs individuels ou à l’échelle du locataire. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) vers Teams, accordez l’instance « UpgradeToTeams » :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau l’intégralité du locataire, omettez le paramètre d’identité à partir de la commande grant :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Expérience utilisateur du client Teams lors de l’utilisation des modes Skype Entreprise

Lorsqu’un utilisateur se trouve dans l’un des modes Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), toutes les conversations et appels entrants sont acheminés vers le client Skype Entreprise de l’utilisateur. Pour éviter toute confusion de l’utilisateur final et garantir un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont automatiquement désactivées lorsqu’un utilisateur se trouve dans l’un des modes de Skype Entreprise. De même, la planification des réunions dans Teams est automatiquement désactivée quand les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab, et automatiquement activée lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings. Pour plus d’informations, consultez [l’expérience client teams et la conformité aux modes de coexistence](./teams-client-experience-and-conformance-to-coexistence-modes.md).

> [!Note] 
> - Avant la remise de l’application automatique des modes Teams et Channels, les modes SfbOnly et SfBWithTeamsCollab se comportent de la même façon.


## <a name="detailed-mode-descriptions"></a>Descriptions détaillées du mode
</br>
</br>

|Mode|Explication|
|---|---|
|**Île**</br>(local uniquement)|Un utilisateur exécute à la fois Skype Entreprise et Teams côte à côte. Cet utilisateur :</br><ul><li>Peut lancer des conversations et des appels VoIP dans Skype Entreprise ou le client Teams. Remarque : les utilisateurs avec Skype Entreprise hébergés localement ne peuvent pas lancer à partir de Teams pour atteindre un autre utilisateur Skype Entreprise, quel que soit le mode du destinataire.<li>Reçoit les conversations & les appels VoIP lancés dans Skype Entreprise par un autre utilisateur de leur client Skype Entreprise.<li>Reçoit des conversations & appels VoIP lancés dans Teams par un autre utilisateur de son client Teams s’ils se trouvent dans le *même locataire*.<li>Reçoit des conversations & appels VoIP lancés dans Teams par un autre utilisateur de son client Skype Entreprise s’il se trouve dans un *locataire fédéré*. <li>Dispose de fonctionnalités RTC comme indiqué ci-dessous :<ul><li>Lorsque l’utilisateur est hébergé dans Skype Entreprise local et qu’il a Téléphonie –  Grandes entreprises, les appels RTC sont toujours lancés et reçus dans Skype Entreprise.<li>Lorsque l’utilisateur est hébergé sur Skype Entreprise Online et dispose du système téléphonique Microsoft, il lance et reçoit toujours des appels RTC dans Skype Entreprise :<ul><li>Cela se produit si l’utilisateur dispose d’un plan d’appel Microsoft ou se connecte au réseau RTC via Skype Entreprise Cloud Connector Edition ou un déploiement local de Skype Entreprise Server (voix hybride).<li>**Remarque : Le routage direct du système téléphonique n’est pas pris en charge en mode Îles.**</ul></ul><li>Reçoit des files d’attente d’appels Microsoft et des appels de standard automatique dans Skype Entreprise :<ul><li>Les numéros de téléphone affectés aux files d’attente d’appels et aux standards automatiques **ne peuvent pas** être des numéros de routage direct du système téléphonique en mode Îles.</ul></ul><li>Peut planifier des réunions dans Teams ou Skype Entreprise (et affichera les deux plug-ins par défaut).<li>Peut participer à n’importe quelle réunion Skype Entreprise ou Teams ; la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**</br>(local uniquement)|Un utilisateur exécute uniquement Skype Entreprise. Cet utilisateur :</br><ul><li>Peut lancer des conversations et des appels à partir de Skype Entreprise uniquement.<li>Reçoit toute conversation/appel dans son client Skype Entreprise, quel que soit l’endroit où il a été lancé, sauf si l’initiateur est un utilisateur Teams avec Skype Entreprise hébergé localement.*<li> Peut planifier uniquement Skype Entreprise réunions, mais peut participer à des réunions Skype Entreprise ou Teams.</br>\** L’utilisation du mode Islands avec des utilisateurs locaux n’est pas recommandée en combinaison avec d’autres utilisateurs en mode SfBOnly. Si un utilisateur Teams avec Skype Entreprise hébergé en local lance un appel ou une conversation à un utilisateur SfBOnly, l’utilisateur SfBOnly n’est pas accessible et reçoit un e-mail de conversation ou d’appel manqué.*|
|**SfBWithTeamsCollab**</br>(local uniquement)|Un utilisateur exécute à la fois Skype Entreprise et Teams côte à côte. Cet utilisateur :</br><ul><li>Dispose des fonctionnalités d’un utilisateur en mode SfBOnly.<li>Est-ce que Teams est activé uniquement pour la collaboration de groupe (canaux) ; La planification des conversations/appels/réunions est désactivée.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(local uniquement)|Un utilisateur exécute à la fois Skype Entreprise et Teams côte à côte. Cet utilisateur :<ul><li>Dispose de la fonctionnalité de conversation et d’appel de l’utilisateur en mode SfBOnly.<li>A activé Teams pour la collaboration de groupe (canaux - inclut les conversations de canal) ; la conversation et l’appel sont désactivés.<li>Peut planifier uniquement des réunions Teams, mais peut participer à des réunions Skype Entreprise ou Teams.</ul>|
|**TeamsOnly**</br>(utilisateurs cloud uniquement)|Un utilisateur exécute uniquement Teams. Cet utilisateur :<ul><li>Reçoit toutes les conversations et appels dans leur client Teams, quel que soit l’endroit où il a été lancé.<li>Peut lancer des conversations et des appels à partir de Teams uniquement.<li>Peut planifier des réunions dans Teams uniquement, mais peut participer à des réunions Skype Entreprise ou Teams.<li>Peut continuer à utiliser Skype Entreprise téléphones IP.<br><br>*L’utilisation du mode TeamsOnly en combinaison avec d’autres utilisateurs en mode Îles n’est pas recommandée tant que l’adoption de Teams n’est pas saturée ; Autrement dit, tous les utilisateurs en mode Îles utilisent et surveillent activement les clients Teams et Skype Entreprise. Si un utilisateur TeamsOnly lance un appel ou une conversation avec un utilisateur Islands, cet appel ou cette conversation atterrit dans le client Teams de l’utilisateur Islands; si l’utilisateur Islands n’utilise pas ou ne surveille pas Teams, cet utilisateur apparaît hors connexion et n’est pas accessible par l’utilisateur TeamsOnly.* <li>Dans certains cas, les participants en mode TeamsOnly ne peuvent participer qu’à Skype Entreprise réunions à l’aide de Application Web Skype Entreprise ou de l’application Réunions Skype en tant qu’utilisateur anonyme. Finalement, ce cas sera vrai pour tous les utilisateurs en mode TeamsOnly. Pour plus d’informations, consultez [Skype Entreprise mise hors service en ligne](skype-for-business-online-retirement.md#what-to-expect-post-retirement).</ul> |
|||




## <a name="related-topics"></a>Rubriques connexes

[Coexistence avec Skype Entreprise](./coexistence-chat-calls-presence.md)

[Expérience client Teams et conformité aux modes coexistence](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Utilisation du service de migration de réunion (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
