---
title: Présentation de l’enregistrement basé sur des stratégies Teams pour l’appel de réunions &
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
ms.localizationpriority: medium
search.appverid: MET150
description: En savoir plus sur l’enregistrement basé sur des stratégies Teams pour l’appel de réunions &
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- purview-compliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e07da669e489a53dfabd2ee7c1fee2079497857
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392164"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Présentation de l’enregistrement basé sur des stratégies Teams pour les appels & réunions

L’enregistrement basé sur des stratégies permet aux organisations qui adoptent Microsoft Teams pour les appels et les réunions de stipuler, à l’aide d’une stratégie administrative, quand les appels et les réunions en ligne doivent être automatiquement enregistrés et capturés pour le traitement et la conservation ultérieurs, comme l’exige la stratégie d’entreprise ou réglementaire appropriée.

Teams a été amélioré pour prendre en charge l’intégration de solutions d’enregistrement tierces, notamment les fonctionnalités de plateforme, les expériences utilisateur et les interfaces administratives nécessaires pour fournir une solution de bout en bout pour la configuration, la gestion, l’enregistrement, le stockage et l’analyse des communications Teams. Les améliorations incluent les API et les événements de plateforme de communication pour l’enregistrement, qui fournissent :

- Capture multimédia transparente et de haute qualité sur les appareils et tous les points de terminaison pris en charge pour l’audio, la vidéo, le partage d’écran et la conversation.

- Prise en charge de la capture d’interaction entre les utilisateurs Teams et les points de terminaison d’appel pris en charge (Teams, Teams Mobile, Skype Entreprise, RTC)

- Nouvelles stratégies d’administration pour l’enregistrement de conformité, y compris l’intégration aux stratégies et aux outils d’appel et de réunion d’administration Teams existants

L’enregistrement de conformité peut être activé sur Microsoft 365 A3/A5/E3/E5/Business Premium, Office 365 A3/A5/E3/E5, salles Teams licence ou Microsoft licence Appareils partagés Teams.

> [!NOTE]
> L’enregistrement de conformité n’est actuellement pas pris en charge pour les services d’appel d’urgence E911.

Les fonctionnalités d’intégration de la solution d’enregistrement de conformité ont également été examinées lors d’Ignite 2019 dans la [session Enregistrement de conformité et Microsoft Teams](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>Vue d’ensemble de l’enregistrement des interactions Teams

Les cas d’usage de l’enregistrement d’interaction peuvent être effectivement séparés en quatre catégories principales de fonctionnalités d’enregistrement : Commodité, Fonctionnelle, Organisation et Interception légale, comme illustré dans l’image :

> [!div class="mx-imgBorder"]
> ![Capture d’écran montrant l’interaction qui enregistre quoi et pourquoi.](media/recording-taxonomy.png "L’image montre les catégories d’enregistrement.")

Chacune des catégories implique des exigences différentes pour la façon dont les enregistrements sont initiés, ce qui est enregistré, où les enregistrements sont stockés, qui est notifié, qui contrôle l’accès et comment la rétention est gérée.

| Type                   | Commodité (enregistrement Teams standard) | Organisation - Réglementé (enregistrement de conformité) |
| ---------------------- | ------------------ | --------------- |
| Initiateur              | Utilisateur               | Administration (système)  |
| Target (Cible)                 | Par appel/réunion | Par utilisateur        |
| Propriétaire du stockage          | Utilisateur               | Conformité      |
| Notification requise ? | Oui                | Oui             |
| Propriétaire de l’accès           | Utilisateur               | Conformité      |
| Stratégie de rétention ?      | Facultatif           | Oui             |

Teams fournit diverses fonctionnalités pour l’enregistrement [pratique](./cloud-recording.md) et fonctionnel des réunions et des événements en direct. L’enregistrement organisationnel permet aux organisations qui adoptent Teams pour les appels et les réunions de stipuler, par le biais d’une stratégie administrative, quand les appels et les réunions en ligne doivent être automatiquement enregistrés et capturés pour le traitement et la conservation ultérieurs, comme l’exige la stratégie d’entreprise ou réglementaire pertinente. Les utilisateurs dans le cadre de cette stratégie seront conscients que leurs interactions numériques avec Teams sont enregistrées, mais ne pourront pas désactiver l’enregistrement et n’auront pas accès à l’enregistrement une fois l’interaction terminée. L’enregistrement fait partie de l’archive organisationnelle disponible pour le personnel de conformité et juridique pour eDiscovery, la conservation légale et d’autres utilisations de rétention de l’entreprise.

## <a name="example-user-needs"></a>Exemples de besoins d’utilisateur

<table>
<thead>
<tr class="header">
<th>Personnage</th>
<th>Besoins</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilisateurs enregistrés</td>
<td><ul>
<li><p>Être averti lorsque l’enregistrement est en cours.</p></li>
<li><p>Soyez informé quand une erreur de stratégie et/ou d’enregistreur provoque des changements de comportement d’appel.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrateur des communications</td>
<td><ul>
<li><p>Comprendre pourquoi et comment appliquer des stratégies d’enregistrement aux utilisateurs/points de terminaison Teams.</p></li>
<li><p>Configurez et gérez les stratégies d’enregistrement Teams pour l’organisation.</p></li>
<li><p>Surveillez et résolvez les problèmes liés à l’enregistrement avec les appels et les réunions Teams.</p></li>
<li><p>Prenez en charge l’agent de conformité interne avec l’analytique opérationnelle sur l’utilisation, la qualité et la fiabilité.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsable de la conformité</td>
<td><ul>
<li><p>Collecter toutes les communications Teams de la manière requise pour respecter les obligations de conformité dans les limites régionales appropriées.</p></li>
<li><p>Recherchez des interactions basées sur des métadonnées ou du contenu d’interaction liés à la communication. Voici quelques exemples courants :</p>
<ul>
<li><p><strong>Métadonnées</strong> - Participants, heure, direction, numéro composé, numéro d’origine, données métier personnalisées</p></li>
<li><p><strong>Contenu</strong> : transcription, sentiment, phonétique, interactions associées</p></li>
</ul></li>
<li><p>Analyser et interagir avec les communications collectées, y compris la possibilité de surveiller les interactions au fur et à mesure qu’elles sont collectées.</p></li>
<li><p>Garantir la sécurité des communications collectées et empêcher la falsification à toutes les étapes.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Vue d’ensemble de l’architecture de solution

Les solutions d’enregistrement de conformité sont intégrées à Teams, comme illustré dans le diagramme suivant :

> [!div class="mx-imgBorder"]
> ![Capture d’écran montrant le paramètre d’application personnalisée de l’équipe.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Les images montrent le flux lorsqu’une réunion ou un appel Teams est envoyé et reçu.")

> [!NOTE]
> Cette solution est conçue spécifiquement pour activer l’enregistrement de conformité basé sur des stratégies avec Teams. Toute autre utilisation de cette solution ne sera pas prise en charge.

## <a name="recorder"></a>Enregistreur

Le composant principal de la solution d’enregistrement de conformité est l’enregistreur.
Les enregistreurs sont créés en tant que bots (services azure) évolutifs qui [utilisent la plateforme de communication de Microsoft et s’inscrivent en tant qu’applications](/graph/cloud-communications-concept-overview) avec Microsoft Graph. L’enregistreur fournit l’interaction directe avec les API de la [plateforme de communication](/graph/api/resources/communications-api-overview) d’appels et de réunions Teams et fournit le point de terminaison pour l’ingestion des médias.

Un [exemple d’application d’enregistreur de conformité est disponible](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) qui montre comment configurer le bot, créer l’instance d’application et attribuer les stratégies de conformité. L’exemple contient également des exemples d’utilisation d’API pour enregistrer des interactions spécifiques, telles que la gestion du routage [des appels entrants](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , la [modification des états d’enregistrement](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) et [la suppression de l’utilisateur qui est enregistré](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
La documentation graph sur les API spécifiques est disponible ici pour [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) et [incomingContext](/graph/api/resources/incomingcontext).

L’implémentation exacte du service d’enregistreur varie selon le partenaire, mais doit être conçue pour prendre en charge plusieurs enregistreurs afin d’obtenir une haute disponibilité et une distribution géographique du déploiement afin de réduire la latence entre Teams et l’enregistreur. En outre, il est prévu que les enregistreurs eux-mêmes soient conçus avec la résilience et la redondance à l’esprit.

Les partenaires doivent confirmer la version minimale requise des API de communication Microsoft Graph et des kits de développement logiciel (SDK) avec Microsoft avant de soumettre leur solution pour certification afin de s’assurer que toutes les exigences d’intégration de l’enregistrement de conformité sont prises en charge.

Deux exigences spécifiques qui sont fondamentales pour le scénario d’enregistrement de conformité sont les suivantes :

- Le bot enregistreur doit être déployé dans Azure

- Le bot enregistreur doit s’exécuter sur une machine virtuelle Windows dans Azure

La configuration requise pour les machines virtuelles Azure et Windows s’applique uniquement au composant Bot Teams, ce qui signifie qu’un partenaire peut implémenter le reste de la plateforme de son choix, à condition qu’il puisse répondre aux exigences fonctionnelles et de performances appropriées pour l’enregistrement de la conformité.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Attribution et approvisionnement de la stratégie d’enregistrement de conformité

Les administrateurs informatiques peuvent déterminer quels utilisateurs doivent être enregistrés et quel enregistreur sera utilisé pour chaque utilisateur, en créant et en affectant des stratégies d’enregistrement de conformité. Les enregistreurs sont automatiquement invités à participer à des conversations en fonction de la configuration de ces stratégies lorsqu’une interaction de communication a lieu. Les stratégies d’enregistrement de conformité sont gérées à [l’aide de Microsoft PowerShell](./teams-powershell-overview.md) et peuvent être appliquées au niveau du locataire, de l’utilisateur et du groupe de sécurité pour chaque organisation. Vous trouverez plus d’informations sur les stratégies Microsoft Learn for [Meeting](./meeting-policies-overview.md), les [stratégies d’appel](./teams-calling-policy.md) et les [stratégies de groupe](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

1. Créez une instance d’application dans votre locataire.

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

2. Créez une stratégie d’enregistrement de conformité.

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

   Consultez [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Affectez la stratégie d’enregistrement de conformité à un utilisateur.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Consultez [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Expériences utilisateur

La prise en charge des notifications est activée à l’aide des expériences client Teams. Les expériences peuvent être visuelles ou audio.

**Clients Teams - notification visuelle**
- Bureau/web
- Mobile (iOS/Android)
- Téléphones Teams
- Salles Teams

**Autres points de terminaison - avis audio**
- Téléphones SIP
- Skype Entreprise
- Audioconférence (notification audio dans la langue par défaut du numéro rendez-vous ou sélectionnée par l’utilisateur)
- Appelants RTC (notification audio dans la langue par défaut de l’utilisateur Teams)

> [!NOTE]
> L’enregistrement de conformité n’est pas pris en charge avec les files d’attente d’appels en mode conférence. Utilisez les files d’attente d’appels en mode transfert.
> L’enregistrement de conformité ne fonctionne pas si les utilisateurs ont rencontré une panne d’Internet et qu’ils effectuent et reçoivent des appels RTC à l’aide d’une SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Enregistrement de conformité pour les programmes de certification Teams

En plus de publier des API disponibles publiquement permettant aux partenaires de développer et d’intégrer des solutions CCaaS avec Teams, nous avons développé l’enregistrement de conformité pour Microsoft programme de certification Teams afin de fournir aux clients l’assurance que la solution de chaque partenaire participant a été testée et vérifiée pour fournir la qualité, la compatibilité et la fiabilité qu’ils attendent de Microsoft solutions.  

Les partenaires suivants ont certifié leur solution pour Microsoft Teams.<br/><br/>

|Partenaire|Site web de la solution |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Technologie perspicace |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|Mida Solutions |[https://www.midasolutions.com/recorder-for-teams/](https://www.midasolutions.com/recorder-for-teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Boîte rouge |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Lac Êtta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams.<br/><br/>

|Partenaire|Site web de la solution |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Redwood Technologies |[https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/](https://www.contentguru.com/en-gb/solutions/needs/compliance-recording-MS-Teams/) |


Cette liste sera mise à jour à mesure que d’autres partenaires rejoignent et répondent aux critères de certification.


## <a name="next-steps"></a>Étapes suivantes

Si vous êtes un fournisseur qui cherche à rejoindre le programme de certification, remplissez [ce formulaire](https://aka.ms/CallingPlatformIntake) à l’étape suivante. Si vous avez besoin de fournir un contexte et des détails supplémentaires, envoyez un e-mail à [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
