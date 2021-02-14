---
title: Migration et interopérabilité - Skype Entreprise
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Comprenez les concepts fondamentaux de la gestion de la transition de votre organisation vers Teams à partir de Skype Entreprise.
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
ms.openlocfilehash: 7b03a31865504507db1c1b0da0fb9c30eb3e1444
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955921"
---
# <a name="coexistence-modes---reference"></a>Modes de coexistence - Référence

Les modes de coexistence offrent aux utilisateurs finaux une expérience simple et prévisible en vue de la transition entre Skype Entreprise et Teams au sein des organisations. Pour une organisation qui passe à Teams, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous ne doivent pas être affectés à TeamsOnly (ou n’importe quel mode) en même temps. Avant que les utilisateurs n’atteignent le mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour assurer une communication prévisible entre les utilisateurs qui sont TeamsOnly et ceux qui ne le sont pas encore.

Du point de vue technique, le mode d’un utilisateur régit plusieurs aspects de son expérience :

- *Routage entrant*: dans quel client (Teams ou Skype Entreprise) les conversations et appels entrants arrivent-ils ? 
- *Publication de présence*: La présence de l’utilisateur est-elle affichée à d’autres utilisateurs en fonction de leur activité dans Teams ou Skype Entreprise ? 
- *Planification de réunion*: Quel service est utilisé pour planifier de nouvelles réunions et s’assurer que le bon module est présent dans Outlook ? TeamsUpgradePolicy ne régit pas les réunions. Les utilisateurs *peuvent toujours participer* à une réunion, qu’il s’agit d’une réunion Skype Entreprise ou d’une réunion Teams.
- *Expérience client*: Quelles fonctionnalités sont disponibles dans Teams et/ou le client Skype Entreprise ? Les utilisateurs peuvent-ils lancer des appels et des conversations dans Teams, Skype Entreprise ou les deux ? L’expérience Teams & canaux est-elle disponible ?  

Pour plus d’informations sur le routage et le comportement de présence en fonction du mode, voir [Coexistence avec Skype Entreprise.](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)

Toutefois, dans une perspective d’expérience, le mode peut être décrit comme définissant l’expérience pour :
- *Conversation et appel*: Quel client utilise un utilisateur ?
- *Planification de réunions*: Les utilisateurs peuvent-ils planifier de nouvelles réunions en tant que réunions Teams ou Skype Entreprise ?
- *Disponibilité de la fonctionnalité de collaboration dans le client Teams.* La fonctionnalité Canaux & Fichiers de Teams est-elle disponible alors que les utilisateurs ont toujours Skype Entreprise ?

Les modes sont répertoriés ci-dessous.
</br>
</br>

|Mode|Appels et conversation|Planification de réunion<sup>1</sup>|Teams & Channels|Cas d’utilisation|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Nécessite un accueil dans Skype Entreprise Online*|Teams|Teams|Oui|État final de la mise à niveau. Également la valeur par défaut pour les nouveaux locataires.|
|Île|L’une ou l|L’une ou l|Oui|Configuration par défaut. Permet à un utilisateur unique d’évaluer les deux clients côte à côte. Les conversations et les appels peuvent avoir lieu dans l’un ou l’autre des clients, de sorte que les utilisateurs doivent toujours exécuter les deux clients. Pour éviter toute confusion ou une régression de l’expérience Skype Entreprise, les communications externes (fédérées), les services vocaux RSTN et les applications vocales, l’intégration d’Office et plusieurs autres intégrations restent gérées par Skype Entreprise.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Entreprise|Teams|Oui|« Réunions en premier ». Principalement pour les organisations locales qui peuvent tirer parti des fonctionnalités de réunion Teams, si elles ne sont pas encore prêtes à passer des appels dans le cloud.|
|SfBWithTeamsCollab|Skype Entreprise|Skype Entreprise|Oui|Vous avez également besoin d’un autre point de départ pour les organisations complexes qui ont besoin d’un contrôle administratif plus étroit.|
|SfBOnly|Skype Entreprise|Skype Entreprise|No<sup>3</sup>|Scénario spécialisé pour les organisations ayant des exigences strictes en matière de contrôle des données. Teams est utilisé uniquement pour participer à des réunions programmées par d’autres personnes.|
||||||

</br>
</br>

**Remarques :**

<sup>1</sup> La possibilité de participer à une réunion existante (qu’elle soit programmée dans Teams ou dans Skype Entreprise) n’est pas régie par le mode. Par défaut, les utilisateurs peuvent toujours participer à n’importe quelle réunion à qui ils ont été invités.

<sup>2</sup> Par défaut, lors de l’attribution de TeamsOnly ou SfbWithTeamsCollabAndMeetings à un utilisateur individuel, les réunions Skype Entreprise existantes prévues par cet utilisateur pour l’avenir sont converties en réunions Teams. Si vous le souhaitez, vous pouvez quitter ces réunions en tant que réunions Skype Entreprise soit en spécifiant lors de l’octroi de TeamsUpgradePolicy, soit en désélectionner la case à cocher dans le portail d’administration  `-MigrateMeetingsToTeams $false` Teams. La possibilité de convertir des réunions de Skype Entreprise en Équipes n’est pas disponible lorsque vous accordez TeamsUpgradePolicy au niveau du client. 

<sup>3</sup> Actuellement, Teams ne peut pas désactiver la fonctionnalité Équipes et canaux et reste ainsi activée pour le moment.


## <a name="using-teamsupgradepolicy"></a>Utilisation de TeamsUpgradePolicy

TeamsUpgradePolicy expose deux propriétés clés : Mode et NotifySfbUsers. 
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(par défaut en italique)|Description|
|---|---|---|---|
|Mode|Enum|*Île*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indique le mode dans qui le client doit s’exécuter.|
|NotifySfbUsers|Bool|*Faux* ou vrai|Indique si vous allez afficher une bannière dans le client Skype Entreprise pour informer l’utilisateur que Teams remplacera bientôt Skype Entreprise. Cela ne peut pas être vrai si Mode=TeamsOnly.|
|||||

Teams fournit toutes les instances pertinentes de TeamsUpgradePolicy via des stratégies intégrées en lecture seule. Par conséquent, seules les cmdlets Obtenir et Accorder sont disponibles. Les instances intégrées sont répertoriées ci-dessous.
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

Ces instances de stratégie peuvent être octroyées à des utilisateurs individuels ou à l’échelle du client. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) vers Teams, accordez l’instance « UpgradeToTeams » :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau l’ensemble du client, omettez le paramètre d’identité de la commande d’octroi :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Expérience utilisateur du client Teams lors de l’utilisation des modes Skype Entreprise

Lorsqu’un utilisateur est dans l’un des modes Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), toutes les conversations et appels entrants sont acheminés vers le client Skype Entreprise de l’utilisateur. Pour éviter la confusion des utilisateurs finaux et garantir un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont automatiquement désactivées lorsqu’un utilisateur est dans l’un des modes Skype Entreprise. De même, la planification de réunions dans Teams est automatiquement désactivée lorsque les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab et automatiquement activés quand un utilisateur est en mode SfBWithTeamsCollabAndMeetings. Pour plus d’informations, [consultez l’expérience du client Teams](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)et la conformité aux modes de coexistence.

> [!Note] 
> - Avant la distribution de l’application automatique des équipes et des canaux, les modes SfbOnly et SfBWithTeamsCollab se comportent à l’identique.


## <a name="detailed-mode-descriptions"></a>Descriptions détaillées du mode
</br>
</br>

|Mode|Explication|
|---|---|
|**Île**</br>(par défaut)|Un utilisateur exécute Skype Entreprise et Teams côte à côte. Cet utilisateur :</br><ul><li>Peut démarrer des conversations et des appels VoIP dans Skype Entreprise ou le client Teams. Remarque : les utilisateurs viennent de Skype Entreprise et ne peuvent pas démarrer une conversation depuis Teams pour atteindre un autre utilisateur Skype Entreprise, quel que soit le mode du destinataire.<li>Reçoit des conversations & appels VoIP initiés dans Skype Entreprise par un autre utilisateur de son client Skype Entreprise.<li>Reçoit des conversations & appels VoIP initiés dans Teams par un autre utilisateur de son client Teams s’il se passe dans *le même client.*<li>Reçoit des conversations & appels VoIP initiés dans Teams par un autre utilisateur de son client Skype Entreprise s’il se passe dans un *client fédéré.* <li>Insère des fonctionnalités PSTN comme indiqué ci-dessous :<ul><li>Lorsque l’utilisateur est re domicile dans Skype Entreprise sur site et a Voix Entreprise, les appels PSTN sont toujours initiés et reçus dans Skype Entreprise.<li>Lorsque l’utilisateur est homed on Skype Entreprise Online et dispose de Microsoft Phone System, l’utilisateur passe et reçoit toujours des appels PSTN dans Skype Entreprise :<ul><li>Cela se produit que l’utilisateur dispose d’un plan d’appel Microsoft ou se connecte au réseau PSTN via Skype Entreprise Édition Cloud Connector ou un déploiement local de Skype Entreprise Server (voix hybride).<li>**Remarque : le routage direct du système téléphonique n’est pas pris en charge en mode Îles.**</ul></ul><li>Reçoit des files d’attente et des appels de attendant automatique Microsoft dans Skype Entreprise :<ul><li>Les numéros de téléphone affectés aux files d’attente et aux **attendants** automatiques ne peuvent pas être des numéros de routage directs du système téléphonique en mode Îles.</ul></ul><li>Peut planifier des réunions dans Teams ou Skype Entreprise (et les deux plug-ins seront ajoutés par défaut).<li>Peut participer à n’importe quelle réunion Skype Entreprise ou Teams ; la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**|Un utilisateur exécute uniquement Skype Entreprise. Cet utilisateur :</br><ul><li>Ne peut démarrer que des conversations et des appels à partir de Skype Entreprise.<li>Reçoit une conversation ou un appel dans son client Skype Entreprise, quelle que soit l’endroit où elle est lancée, sauf si le initiateur est un utilisateur de Teams qui a Skype Entreprise domicile sur site. *<li> Ne peut planifier que des réunions Skype Entreprise, </br> \** mais peut participer à des réunions Skype Entreprise ou Teams. L’utilisation du mode Îles avec des utilisateurs locaux n’est pas recommandée en combinaison avec d’autres utilisateurs en mode SfBOnly. Si un utilisateur de Teams douzième dans Skype Entreprise entame un appel ou une conversation avec un utilisateur SfBOnly, l’utilisateur SfBOnly n’est pas accessible et reçoit une conversation ou un e-mail d’appel manqué.*|
|**SfBWithTeamsCollab**|Un utilisateur exécute Skype Entreprise et Teams côte à côte. Cet utilisateur :</br><ul><li>Possède les fonctionnalités d’un utilisateur en mode SfBOnly.<li>Teams est activé uniquement pour la collaboration de groupe (canaux) ; les appels et la planification de réunions sont désactivés.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|Un utilisateur exécute Skype Entreprise et Teams côte à côte. Cet utilisateur :<ul><li>Initie les fonctionnalités de conversation et d’appel de l’utilisateur en mode SfBOnly.<li>Teams est-il activé pour la collaboration de groupe (canaux - inclut les conversations de canal) ; les appels sont désactivés.<li>Ne peut planifier que des réunions Teams, mais peut participer à des réunions Skype Entreprise ou Teams.</ul>|
|**TeamsOnly**</br>(nécessite la page d’accueil SfB Online)|Un utilisateur exécute uniquement Teams. Cet utilisateur :<ul><li>Reçoit toutes les conversations et appels dans son client Teams, quel que soit l’endroit où elle est lancée.<li>Peut démarrer des conversations et des appels à partir de Teams uniquement.<li>Vous ne pouvez planifier des réunions que dans Teams, mais vous pouvez participer à des réunions Skype Entreprise ou Teams.<li>Peut continuer à utiliser les téléphones IP Skype Entreprise.<br><br>*Il n’est pas recommandé d’utiliser le mode TeamsOnly en combinaison avec d’autres utilisateurs en mode Îles tant que l’adoption de Teams n’est pas saturée . autrement dit, tous les utilisateurs du mode Îles utilisent et surveillent activement les clients Teams et Skype Entreprise. Si un utilisateur de TeamsOnly entame un appel ou une conversation avec un utilisateur des îles, cet appel ou cette conversation sera reçu dans le client Teams de l’utilisateur des îles ; si l’utilisateur des îles n’utilise pas ou ne surveille pas Teams, il apparaît hors connexion et n’est pas accessible par l’utilisateur TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Sujets associés

[Coexistence avec Skype Entreprise](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Expérience client Teams et conformité aux modes coexistence](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
