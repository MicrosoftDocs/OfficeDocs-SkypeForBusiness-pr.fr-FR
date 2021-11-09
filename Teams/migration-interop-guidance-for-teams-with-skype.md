---
title: Migration et interopérabilité - Skype Entreprise
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Comprenez les concepts fondamentaux de la gestion de la transition de votre organisation vers Teams’Skype Entreprise.
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
ms.openlocfilehash: 9e7138acede1f6d67d5bd13d1e5edf413389f8b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865462"
---
# <a name="coexistence-modes---reference"></a>Modes de coexistence - Référence

> [!Important] 
> - Après l’retrait de Skype Entreprise Online le 31 juillet 2021, il n’est plus possible d’attribuer un mode de coexistence autre que TeamsOnly à un utilisateur homed in the cloud. Comme c’était le cas avant la retraite, les utilisateurs Skype Entreprise Server domicile sur site peuvent se voir attribuer n’importe quel *mode* autre que TeamsOnly. 

Les modes de coexistence offrent une expérience simple et prévisible aux utilisateurs finaux au cours de la transition des organisations Skype Entreprise vers Teams. Pour une organisation qui passe à Teams, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent pas être affectés à TeamsOnly (ou n’importe quel mode) en même temps. Avant que les utilisateurs n’atteignent le mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode de Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour assurer une communication prévisible entre les utilisateurs qui sont TeamsOnly et ceux qui ne le sont pas encore.

Du point de vue technique, le mode d’un utilisateur régit plusieurs aspects de son expérience :

- *Routage entrant*: dans quel client (Teams ou Skype Entreprise) les conversations et appels entrants arrivent-ils ? 
- *Publication de présence*: La présence de l’utilisateur est-elle affichée à d’autres utilisateurs en fonction de leur activité dans Teams ou Skype Entreprise ? 
- *Planification de réunion*: quel service est utilisé pour planifier de nouvelles réunions et s’assurer que le bon module est présent dans Outlook ? TeamsUpgradePolicy ne régit pas les réunions. Les utilisateurs peuvent *toujours participer* à une réunion, qu’il s’Skype Entreprise réunion ou Teams réunion.
- *Expérience client*: Quelles fonctionnalités sont disponibles dans Teams et/ou Skype Entreprise client ? Les utilisateurs peuvent-ils lancer des appels et des conversations dans Teams, Skype Entreprise, ou les deux ? L’expérience Teams & canaux est-elle disponible ?  

Pour plus d’informations sur le routage et le comportement de présence en fonction du mode, voir [Coexistence avec Skype Entreprise.](./coexistence-chat-calls-presence.md)

Toutefois, dans une perspective d’expérience, le mode peut être décrit comme définissant l’expérience pour :
- *Conversation et appel*: Quel client utilise un utilisateur ?
- *Planification de réunions*: Les utilisateurs peuvent-ils planifier de nouvelles réunions Teams ou Skype Entreprise réunions ?
- *Disponibilité de la fonctionnalité de collaboration dans Teams client.* Est-Teams & fonctionnalité Canaux et fichiers disponible alors que les utilisateurs ont encore des Skype Entreprise ?

Les modes sont répertoriés ci-dessous. Les utilisateurs du cloud doivent être TeamsOnly et les utilisateurs homed sur site doivent être n’importe quel mode autre que TeamsOnly. 
</br>
</br>

|Mode|Appels et conversation|Planification de réunion<sup>1</sup>|Teams & Canaux de distribution|Cas d’utilisation|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*Uniquement possible si l’utilisateur n’a pas de compte local dans Skype Entreprise Server*|Équipes|Teams|Oui|État final de la mise à niveau. Valeur par défaut pour les nouveaux locataires, sauf si une configuration hybride est détectée.|
|Île|L’une ou l|L’une ou l|Oui|Configuration par défaut pour les organisations hybrides. Permet à un utilisateur unique d’évaluer les deux clients côte à côte. Les conversations et les appels peuvent avoir lieu dans l’un ou l’autre client, de sorte que les utilisateurs doivent toujours exécuter les deux clients. Pour éviter une expérience de Skype Entreprise source de confusion ou de régression, les communications externes (fédérées), les services vocaux PSTN et les applications vocales, l’intégration Office et plusieurs autres intégrations continuent d’être gérées par Skype Entreprise.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype Entreprise|Teams|Oui|« Réunions en premier ». Principalement pour les organisations locales qui peuvent tirer parti Teams fonctionnalités de réunion, si elles ne sont pas encore prêtes à passer des appels vers le cloud.|
|SfBWithTeamsCollab|Skype Entreprise|Skype Entreprise|Oui|Vous avez également besoin d’un autre point de départ pour des organisations complexes qui ont besoin d’un contrôle administratif plus étroit.|
|SfBOnly|Skype Entreprise|Skype Entreprise|No<sup>3</sup>|Scénario spécialisé pour les organisations ayant des exigences strictes en matière de contrôle des données. Teams est utilisé uniquement pour participer à des réunions programmées par d’autres personnes.|
||||||

</br>
</br>

**Remarques :**

<sup>1</sup> La possibilité de participer à une réunion existante (qu’elle soit programmée dans Teams ou dans Skype Entreprise) n’est pas régie par le mode. Par défaut, les utilisateurs peuvent toujours participer à n’importe quelle réunion à qui ils ont été invités.

<sup>2</sup> Par défaut, lors de l’attribution de TeamsOnly ou SfbWithTeamsCollabAndMeetings à un utilisateur individuel, les réunions Skype Entreprise existantes prévues par cet utilisateur pour l’avenir sont converties en réunions Teams. Si vous le souhaitez, vous pouvez quitter ces réunions en Skype Entreprise en spécifiant lors de l’octroi de TeamsUpgradePolicy ou en désélectionner la case à cocher dans le portail d’administration `-MigrateMeetingsToTeams $false` Teams. La possibilité de convertir des réunions à partir Skype Entreprise en Teams n’est pas disponible lorsque vous accordez TeamsUpgradePolicy au niveau du client. 

<sup>3</sup> Actuellement, Teams ne peut pas désactiver les fonctionnalités de Teams et de canaux, ce qui reste activé pour le moment.


## <a name="using-teamsupgradepolicy"></a>Utilisation de TeamsUpgradePolicy

TeamsUpgradePolicy expose deux propriétés clés : Mode et NotifySfbUsers. 
</br>
</br>

|Paramètre|Type|Valeurs autorisées</br>(par défaut en italique)|Description|
|---|---|---|---|
|Mode|Enum|*Île*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|Indique le mode dans qui le client doit s’exécuter.|
|NotifySfbUsers|Bool|*Faux* ou vrai|Indique si vous allez afficher une bannière dans le client Skype Entreprise’informer l’utilisateur que Teams sera bientôt Skype Entreprise. Cela ne peut pas être vrai si Mode=TeamsOnly.|
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

Ces instances de stratégie peuvent être octroyées à des utilisateurs individuels ou à l’échelle du client. Par exemple :
- Pour mettre à niveau un utilisateur ($SipAddress) vers Teams, accordez l’instance « UpgradeToTeams » :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- Pour mettre à niveau l’ensemble du client, omettez le paramètre d’identité de la commande d’octroi :</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Expérience utilisateur Teams client lors de l’utilisation des modes Skype Entreprise client

Lorsqu’un utilisateur est dans l’un des modes Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings), toutes les conversations et appels entrants sont acheminés vers le client Skype Entreprise de l’utilisateur. Pour éviter la confusion des utilisateurs finaux et garantir un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont automatiquement désactivées lorsqu’un utilisateur est dans l’un des modes Skype Entreprise. De même, la planification de réunions dans Teams est automatiquement désactivée lorsque les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab et automatiquement activés quand un utilisateur est en mode SfBWithTeamsCollabAndMeetings. Pour plus d’informations, voir Teams expérience client et la conformité aux [modes de coexistence.](./teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!Note] 
> - Avant la livraison de l’application automatique de Teams et canaux, les modes SfbOnly et SfBWithTeamsCollab se comportent à l’identique.


## <a name="detailed-mode-descriptions"></a>Description détaillée du mode
</br>
</br>

|Mode|Explication|
|---|---|
|**Île**</br>(sur site uniquement)|Un utilisateur exécute les Skype Entreprise et Teams côte à côte. Cet utilisateur :</br><ul><li>Peut démarrer des conversations et des appels VoIP Skype Entreprise ou Teams client. Remarque : les utilisateurs Skype Entreprise domicile sur site ne peuvent pas démarrer d’une Teams pour atteindre un autre utilisateur Skype Entreprise, quel que soit le mode du destinataire.<li>Reçoit les conversations & appels VoIP initiés dans Skype Entreprise par un autre utilisateur de son client Skype Entreprise messagerie.<li>Reçoit des conversations & appels VoIP initiés dans Teams par un autre utilisateur de son client Teams s’il se passe dans *le même client.*<li>Reçoit des conversations & appels VoIP initiés dans Teams par un autre utilisateur de son client Skype Entreprise s’il se passe dans un *client fédéré.* <li>Insère des fonctionnalités PSTN comme indiqué ci-dessous :<ul><li>Lorsque l’utilisateur est re domicile Skype Entreprise sur site et a des Voix Entreprise, les appels PSTN sont toujours initiés et reçus dans Skype Entreprise.<li>Lorsque l’utilisateur est homed on Skype Entreprise Online et dispose d’Téléphone Microsoft System, l’utilisateur passe et reçoit toujours des appels PSTN dans Skype Entreprise :<ul><li>Cela se produit si l’utilisateur dispose d’un plan d’appel Microsoft ou se connecte au réseau PSTN via Skype Entreprise Cloud Connector Edition ou un déploiement local de Skype Entreprise Server (voix hybride).<li>**Remarque : le Système téléphonique routage direct n’est pas pris en charge en mode Îles.**</ul></ul><li>Reçoit des files d’attente et des appels de attendant automatique Microsoft dans Skype Entreprise :<ul><li>Téléphone numéros affectés aux files d’attente et aux **attendants** automatiques ne peuvent pas être Système téléphonique des numéros de routage direct en mode Îles.</ul></ul><li>Peut planifier des réunions dans Teams ou Skype Entreprise (et voient les deux plug-ins par défaut).<li>Peut participer à n’importe quelle Skype Entreprise ou Teams réunion ; la réunion s’ouvre dans le client respectif.</ul>|
|**SfBOnly**</br>(sur site uniquement)|Un utilisateur exécute uniquement Skype Entreprise. Cet utilisateur :</br><ul><li>Peut démarrer des conversations et des appels à partir Skype Entreprise uniquement.<li>Reçoit une conversation ou un appel dans son client Skype Entreprise, quelle que soit l’endroit où elle a été lancée, sauf si le initié est un utilisateur Teams qui Skype Entreprise domicile sur site. *<li> Ne peut planifier Skype Entreprise que d’autres réunions, </br> \** mais peut Skype Entreprise ou Teams réunions. L’utilisation du mode Îles avec des utilisateurs locaux n’est pas recommandée en combinaison avec d’autres utilisateurs en mode SfBOnly. Si un utilisateur Teams Skype Entreprise douzième sur site passe un appel ou une conversation avec un utilisateur SfBOnly, l’utilisateur SfBOnly n’est pas accessible et reçoit une conversation ou un e-mail d’appel manqué.*|
|**SfBWithTeamsCollab**</br>(sur site uniquement)|Un utilisateur exécute les Skype Entreprise et Teams côte à côte. Cet utilisateur :</br><ul><li>Possède les fonctionnalités d’un utilisateur en mode SfBOnly.<li>Est Teams uniquement pour la collaboration de groupe (canaux) ; les appels et la planification de réunions sont désactivés.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**</br>(sur site uniquement)|Un utilisateur exécute les Skype Entreprise et Teams côte à côte. Cet utilisateur :<ul><li>Initie les fonctionnalités de conversation et d’appel de l’utilisateur en mode SfBOnly.<li>A Teams pour la collaboration de groupe (canaux - inclut les conversations de canal) ; les appels sont désactivés.<li>Ne peut planifier Teams que d’autres réunions, mais peut Skype Entreprise ou Teams réunions.</ul>|
|**TeamsOnly**</br>(utilisateurs cloud uniquement)|Un utilisateur exécute uniquement des Teams. Cet utilisateur :<ul><li>Reçoit toutes les conversations et appels dans leur client Teams, quel que soit l’endroit où ils ont été initiés.<li>Peut démarrer des conversations et des appels à partir Teams uniquement.<li>Ne peut planifier des réunions que Teams, mais peut participer Skype Entreprise ou Teams réunions.<li>Peut continuer à utiliser Skype Entreprise téléphones IP.<br><br>*L’utilisation du mode TeamsOnly en combinaison avec d’autres utilisateurs en mode Îles n’est pas recommandée tant que l’adoption Teams est saturée ; autrement dit, tous les utilisateurs du mode Îles utilisent et surveillent activement Teams et Skype Entreprise clients. Si un utilisateur de TeamsOnly entame un appel ou une conversation avec un utilisateur des îles, cet appel ou cette conversation se place dans le client de messagerie Teams de l’utilisateur des îles. si l’utilisateur des îles n’utilise pas ou ne surveille pas Teams, il apparaît hors connexion et n’est pas accessible par l’utilisateur TeamsOnly.*</ul> |
|||




## <a name="related-topics"></a>Voir aussi

[Coexistence avec Skype Entreprise](./coexistence-chat-calls-presence.md)

[Expérience client Teams et conformité aux modes coexistence](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
