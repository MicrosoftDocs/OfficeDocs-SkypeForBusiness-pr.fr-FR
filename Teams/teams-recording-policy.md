---
title: Présentation des enregistrements basés sur les stratégies d’équipes pour les appels & des réunions
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Apprenez-en davantage sur l’enregistrement basé sur les stratégies d’équipe pour appeler & réunions
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48cc430ea864614a306725958b56dda934e00eef
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121644"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Présentation des enregistrements basés sur les stratégies d’équipe pour les appels & des réunions

L’enregistrement basé sur une stratégie permet aux organisations adoptant Microsoft teams d’appeler et de réunions de stipuler, à l’aide d’une stratégie d’administration, si les appels et les réunions en ligne doivent être enregistrés automatiquement et capturés en cas de traitement et de rétention ultérieurs requis par une politique d’entreprise ou de réglementation appropriée.

Teams a été amélioré pour prendre en charge l’intégration de solutions d’enregistrement tiers, notamment les fonctionnalités de plateforme, les expériences utilisateur et les interfaces d’administration nécessaires pour fournir une solution de bout en bout pour la configuration, la gestion, l’enregistrement, le stockage et l’analyse des communications entre les équipes. Cela inclut les API et événements de la plateforme de communication pour l’enregistrement, qui fournit les éléments suivants :

- Capture multimédia transparente et de grande qualité sur les appareils et tous les points de terminaison pris en charge pour l’audio, la vidéo, le partage d’écran et la discussion.

- Prise en charge de la capture d’interactions entre les utilisateurs de teams et les points de terminaison d’appel pris en charge (Teams, équipes mobiles, Skype entreprise, RTC)

- Nouvelles politiques d’administration pour l’enregistrement de la conformité, y compris l’intégration aux équipes existantes d’appels administratifs et aux politiques et aux outils de réunion

- Activé pour les utilisateurs de teams disposant d’une licence distincte

Les fonctionnalités d’intégration de la solution enregistrement de la conformité ont également été examinées lors de l’enflamme 2019 de la [<span class="underline">session enregistrement de la conformité et Microsoft teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).

## <a name="teams-interaction-recording-overview"></a>Présentation de l’enregistrement d’interactions dans teams

Les cas d’utilisation de l’enregistrement d’interactions peuvent être divisées en quatre catégories principales de fonctionnalité d’enregistrement (commodité, fonctionnelle, d’organisation et d’interception licite, comme illustré dans l’image :

![Capture d’écran montrant les interactions enregistrement et pourquoi.](media/recording-taxonomy.png "L’image montre les catégories d’enregistrements.")

Chacune des catégories implique différentes exigences relatives à la manière dont les enregistrements sont initiés, les enregistrements enregistrés, les enregistrements stockés, les personnes qui contrôlent l’accès et la manière dont la rétention est gérée.

|                        | Avantage        | Fonction         | Org-général      | Réglementé par l’Organisation | Interception licite   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| Initiateur              | Utilisateur               | Application/solution       | Administrateur système     | Administrateur système  | LEA                |
| Cible                 | Par appel/réunion | Par appel/réunion | Par appel/réunion | Par utilisateur        | Par point de terminaison/DID |
| Propriétaire de stockage          | Utilisateur               | Appli                | Administrateur              | Conformément      | LEA                |
| Notification requise ? | Oui                 | Oui                 | Oui                 | Oui             | Non                 |
| Propriétaire de l’accès           | Utilisateur               | Appli                | Administrateur              | Conformément      | LEA                |
| Stratégie de rétention      | Facultatif           | Oui                 | Oui                 | Oui              | Oui                |

Teams fournit différentes fonctionnalités pour un enregistrement [<span class="underline">pratique</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) et opérationnel pour les réunions et les événements en direct. L’enregistrement d’organisation implique la possibilité pour les organisations d’adopter des équipes aux fins d’appel et de réunions pour stipuler, par le biais d’une politique d’administration, l’enregistrement et la conservation automatiques des appels et des réunions en ligne conformément aux exigences d’entreprise ou de réglementation pertinentes. Les utilisateurs qui se trouvent dans le cadre de cette stratégie seront avertis que leurs interactions numériques avec Teams, mais ne seront pas en mesure de désactiver l’enregistrement et ne pourront pas accéder à l’enregistrement une fois que l’interaction se termine. L’enregistrement fait partie de l’archive d’organisation disponible pour la conformité et le personnel légal pour la découverte électronique, la conservation légale et les autres usages de rétention de l’entreprise.

## <a name="example-user-needs"></a>Exemple d’utilisation requise

<table>
<thead>
<tr class="header">
<th><strong>Personnage</strong></th>
<th><strong>Nécessit</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilisateurs enregistrés</td>
<td><ul>
<li><p>Recevoir une notification lorsque l’enregistrement est en cours.</p></li>
<li><p>Soyez informé en cas d’erreur de stratégie et/ou d’enregistreur entraînant des modifications du comportement d’appel.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administration des communications</td>
<td><ul>
<li><p>Comprenez pourquoi et comment appliquer/mettre en œuvre des stratégies d’enregistrement aux utilisateurs/points de terminaison Teams.</p></li>
<li><p>Configurer et tenir à jour des stratégies d’enregistrement d’équipes pour l’organisation.</p></li>
<li><p>Surveiller et résoudre les problèmes liés à l’enregistrement liés aux conférences et aux appels aux équipes.</p></li>
<li><p>Prise en charge de l’officier de conformité interne avec les analyses opérationnelles concernant l’utilisation, la qualité et la fiabilité.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Officier de conformité</td>
<td><ul>
<li><p>Rassemblez toutes les communications de l’équipe conformément aux exigences en matière de conformité aux frontières locales appropriées.</p></li>
<li><p>Recherchez des interactions basées sur les métadonnées ou le contenu d’interaction liés aux communications. Voici quelques exemples courants :</p>
<ul>
<li><p><strong>Metadata</strong> - Participants, heure, direction, numéro composé, numéro d’origine, données métiers personnalisées</p></li>
<li><p><strong>Contenu</strong> – transcription, sentiment, phonétique, interactions associées</p></li>
</ul></li>
<li><p>Analysez et interagissez avec les communications collectées, y compris la possibilité de surveiller les interactions lors de leur collecte.</p></li>
<li><p>Assurez la sécurité des communications collectées et empêchez les étapes de falsification.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Vue d’ensemble de l’architecture de solution

Les solutions d’enregistrement de la conformité sont intégrées aux équipes, comme indiqué dans le schéma suivant :

![Capture d’écran montrant le paramètre de l’application personnalisée d’équipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Les images montrent le flux d’envoi et de réception d’une réunion ou d’un appel Teams.")

## <a name="recorder"></a>Magnétoscope

Le composant principal de la solution d’enregistrement de la conformité est l’enregistreur.
Les enregistreurs sont basés sur des services basés sur la fonction Azure (robots) qui [<span class="underline">tirent parti de la plateforme de communication de Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) et sont enregistrés en tant qu’applications avec Microsoft Graph. L’enregistreur d’enregistrements fournit une interaction directe avec les API d’appel et de réunion de la [<span class="underline">plateforme de communication</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) et fournit le point de terminaison d’acquisition multimédia.

Un [<span class="underline">exemple d’application d’enregistrement de conformité est disponible</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , qui montre comment configurer le bot, créer l’instance d’application et affecter les stratégies de conformité. Cet exemple inclut également des exemples d’utilisation d’API pour l’enregistrement d’interactions spécifiques telles que le traitement de l’acheminement des [<span class="underline">appels entrants</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , le [<span class="underline">changement d’état d’enregistrement</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)et [<span class="underline">la suppression de l’utilisateur enregistré</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
La documentation Graph sur les API spécifiques est disponible ici pour [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) et [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).

L’implémentation exacte du service d’enregistreur d’enregistrements varie en fonction du partenaire, mais doit être conçue pour prendre en charge plusieurs enregistreurs afin de garantir une disponibilité élevée et une distribution géographique du déploiement afin de réduire la latence entre teams et l’enregistreur. De plus, il est probable que les enregistreurs eux-mêmes soient conçus en fonction de la résilience et de la redondance à l’esprit.

Les partenaires doivent confirmer la version minimale requise des API et SDK Microsoft Graph avec Microsoft avant de soumettre leur solution de certification pour s’assurer que toutes les exigences en matière d’intégration de l’enregistrement de la conformité sont prises en charge.

Deux exigences spécifiques qui sont fondamentales pour le scénario d’enregistrement de la conformité sont les suivantes :

- Le robot de magnétoscope doit être déployé dans Azure

- Le robot de magnétoscope doit s’exécuter sur un ordinateur virtuel Windows dans Azure

La configuration requise pour Azure et Windows VM s’applique uniquement au composant bot Teams, ce qui signifie qu’un partenaire peut mettre en œuvre le reste de la plate-forme de son choix pour répondre aux exigences de performances et de fonctionnement pertinentes pour l’enregistrement de la conformité.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Attribution de stratégie d’enregistrement de la conformité et approvisionnement

Les administrateurs informatiques peuvent déterminer quels utilisateurs seront enregistrés et quel enregistreur sera utilisé pour chaque utilisateur, en créant et en assignant des stratégies d’enregistrement de la conformité. Les enregistreurs sont automatiquement invités à participer à des conversations en fonction de la configuration de celles-ci lorsqu’une interaction de communication a lieu. Les stratégies d’enregistrement de la conformité sont gérées à l’aide de [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) et peuvent être appliquées au niveau du client, de la sécurité et du groupe de sécurité pour chaque organisation. Vous trouverez des informations supplémentaires sur les stratégies de [<span class="underline">réunion</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), les stratégies d' [<span class="underline">appel</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) et les stratégies de [<span class="underline">groupe</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)dans Microsoft documents.

1. Créez une instance d’application dans votre client.

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. Créer une stratégie d’enregistrement de conformité.

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Affectez la stratégie d’enregistrement de conformité à un utilisateur.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Expérience utilisateur

La prise en charge des notifications est activée à l’aide de l’expérience client d’équipes. Les expériences peuvent être visuelles ou audio.

**Clients teams-avis visuel**
- Bureau et Web
- Mobile (iOS/Android)
- Téléphones teams
- Salles d’équipe

**Autres points de terminaison-avis audio**
- Téléphones SIP
- Skype Entreprise
- Audioconférence
- Appelants PSTN

## <a name="compliance-recording-for-teams-certification-programs"></a>Enregistrement de la conformité pour les programmes de certification d’équipes

Outre la publication d’API disponibles à des fins publiques permettant aux partenaires de développer et d’intégrer des solutions CCaaSes avec Teams, nous avons mis en garde l’enregistrement de la conformité pour le programme de certification de Microsoft Teams, afin de fournir aux clients l’assurance que les solutions de chaque partenaire participant ont été testées et vérifiées pour fournir la qualité, la compatibilité et la fiabilité de leurs solutions  

Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams.  

|Partenaire|Site Web de solution |
|:--|:--|
|Technologies ASC |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|BELLE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Zone rouge |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

Cette liste sera mise à jour sous la forme d’autres partenaires et répondez aux critères de certification.

## <a name="next-steps"></a>Étapes suivantes

Si vous êtes un fournisseur qui cherche à rejoindre le programme de certification, envoyez-le à <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.
