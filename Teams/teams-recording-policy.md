---
title: Présentation de Teams’enregistrement basé sur des stratégies pour l’appel de réunions &
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
description: En savoir plus sur Teams enregistrement basé sur des stratégies pour appeler des réunions &
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
ms.openlocfilehash: b6fb06062902ee5bb0b3ab3f41f25a712933dd37
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056924"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Présentation de Teams enregistrement basé sur des stratégies pour les appels & réunions

L’enregistrement basé sur des stratégies permet aux organisations qui adoptent Microsoft Teams pour les appels et les réunions de spécifier, à l’aide d’une stratégie d’administration, quand les appels et les réunions en ligne doivent être automatiquement enregistrés et capturés pour le traitement et la rétention suivants, selon les besoins de la stratégie d’entreprise ou réglementaire pertinente.

Teams a été améliorée pour prendre en charge l’intégration de solutions d’enregistrement tierces, notamment les fonctionnalités de plateforme, les expériences utilisateur et les interfaces administratives nécessaires pour fournir une solution de bout en bout pour la configuration, la gestion, l’enregistrement, le stockage et l’analyse des communications Teams. Les améliorations incluent les API et les événements de la plateforme de communications pour l’enregistrement, qui fournissent :

- Capture multimédia transparente et de haute qualité sur tous les appareils et tous les points de terminaison pris en charge pour l’audio, la vidéo, le partage d’écran et la conversation.

- Prise en charge de la capture d’interaction entre les utilisateurs Teams et les points de terminaison d’appel pris en charge (Teams, Teams Mobile, Skype Entreprise, RTC)

- Nouvelles stratégies d’administration pour l’enregistrement de conformité, notamment l’intégration avec les outils et stratégies d’appel et de réunion d’administration Teams existants

L’enregistrement de conformité peut être activé sur Microsoft 365 A3/A5/E3/E5/Business Premium et Office 365 A3/A5/E3/E5 utilisateurs. 

Les fonctionnalités d’intégration de la solution d’enregistrement de conformité ont également été examinées à Ignite 2019 dans la [session d’enregistrement de conformité et de Microsoft Teams](https://myignite.microsoft.com/archives/IG19-VCE40).

## <a name="teams-interaction-recording-overview"></a>vue d’ensemble de l’enregistrement d’interaction Teams

Les cas d’utilisation de l’enregistrement d’interaction peuvent être effectivement séparés en quatre catégories principales de fonctionnalités d’enregistrement : commodité, fonctionnalité, organisationnelle et interception légale, comme illustré dans l’image :

> [!div class="mx-imgBorder"]
> ![Capture d’écran montrant l’interaction enregistrant quoi et pourquoi.](media/recording-taxonomy.png "L’image montre les catégories d’enregistrement.")

Chacune des catégories implique des exigences différentes pour la façon dont les enregistrements sont lancés, ce qui est enregistré, où les enregistrements sont stockés, qui est averti, qui contrôle l’accès et comment la rétention est gérée.

| Type                   | Commodité (enregistrement régulier Teams) | Org - Réglementé (Enregistrement de conformité) |
| ---------------------- | ------------------ | --------------- |
| Initiateur              | Utilisateur               | Administrateur (système)  |
| Target (Cible)                 | Par appel/réunion | Par utilisateur        |
| propriétaire Stockage          | Utilisateur               | Conformité      |
| Notification requise ? | Oui                | Oui             |
| Propriétaire de l’accès           | Utilisateur               | Conformité      |
| Stratégie de rétention ?      | Facultatif           | Oui             |

Teams offre différentes fonctionnalités pour [l’enregistrement pratique](./cloud-recording.md) et fonctionnel des réunions et des événements en direct. L’enregistrement organisationnel signifie permettre aux organisations qui adoptent des Teams pour les appels et les réunions de spécifier, par le biais d’une stratégie d’administration, quand les appels et les réunions en ligne doivent être enregistrés et capturés automatiquement pour le traitement et la rétention suivants, comme l’exige la politique d’entreprise ou réglementaire pertinente. Les utilisateurs sous cette stratégie seront conscients que leurs interactions numériques avec Teams sont enregistrées, mais ne pourront pas désactiver l’enregistrement et n’auront pas accès à l’enregistrement une fois l’interaction terminée. L’enregistrement fait partie de l’archive organisationnelle disponible pour la conformité et le personnel juridique pour eDiscovery, conservation légale et autres utilisations de rétention d’entreprise.

## <a name="example-user-needs"></a>Exemple de besoins des utilisateurs

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
<li><p>Soyez averti lorsque l’enregistrement est en cours.</p></li>
<li><p>Soyez informé quand une erreur de stratégie et/ou d’enregistreur entraîne des modifications dans le comportement d’appel.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrateur des communications</td>
<td><ul>
<li><p>Comprendre pourquoi et comment appliquer/appliquer des stratégies d’enregistrement à Teams utilisateurs/points de terminaison.</p></li>
<li><p>Configurez et gérez Teams stratégies d’enregistrement pour l’organisation.</p></li>
<li><p>Surveillez et résolvez les problèmes liés à l’enregistrement avec Teams appels et réunions.</p></li>
<li><p>Prenez en charge l’agent de conformité interne avec l’analytique opérationnelle sur l’utilisation, la qualité et la fiabilité.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Agent de conformité</td>
<td><ul>
<li><p>Collectez toutes les communications Teams de la manière requise pour respecter les obligations de conformité dans les limites régionales appropriées.</p></li>
<li><p>Recherchez des interactions basées sur des métadonnées ou du contenu d’interaction liés à la communication. Voici quelques exemples courants :</p>
<ul>
<li><p><strong>Métadonnées</strong> - Participants, heure, direction, numéro composé, numéro d’origine, données métier personnalisées</p></li>
<li><p><strong>Contenu</strong> : transcription, sentiment, phonétique, interactions associées</p></li>
</ul></li>
<li><p>Analysez et interagissez avec les communications collectées, y compris la possibilité de surveiller les interactions à mesure qu’elles sont collectées.</p></li>
<li><p>Garantir la sécurité des communications collectées et empêcher toute falsification à tous les stades.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Vue d’ensemble de l’architecture de solution

Les solutions d’enregistrement de conformité sont intégrées à Teams comme illustré dans le diagramme suivant :

> [!div class="mx-imgBorder"]
> ![Capture d’écran montrant le paramètre d’application personnalisée de l’équipe.](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Les images affichent le flux lorsqu’une réunion ou un appel Teams est envoyé et reçu.")

> [!NOTE]
> Cette solution est conçue spécifiquement pour activer l’enregistrement de conformité basé sur des stratégies avec Teams. Toute autre utilisation de cette solution ne sera pas prise en charge.

## <a name="recorder"></a>Enregistreur

Le composant principal de la solution d’enregistrement de conformité est l’enregistreur.
Les enregistreurs sont créés en tant que services scalables basés sur Azure (bots) qui [utilisent la plateforme de communications de Microsoft et s’inscrivent](/graph/cloud-communications-concept-overview) en tant qu’applications auprès de Microsoft Graph. L’enregistreur fournit l’interaction directe avec les [API de plateforme de communication](/graph/api/resources/communications-api-overview) Teams appels et réunions et fournit le point de terminaison pour l’ingestion du média.

Un [exemple d’application d’enregistreur de conformité est disponible](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) qui montre comment configurer le bot, créer l’instance d’application et attribuer les stratégies de conformité. L’exemple contient également des exemples sur l’utilisation de l’API pour l’enregistrement d’interactions spécifiques, telles que la gestion du routage des [appels entrants](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) , la [modification des états d’enregistrement](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138) et [la suppression de l’utilisateur en cours d’enregistrement](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).
Graph documentation sur les API spécifiques est disponible ici pour [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http) et [incomingContext](/graph/api/resources/incomingcontext).

L’implémentation exacte du service d’enregistreur varie selon le partenaire, mais doit être conçue pour prendre en charge plusieurs enregistreurs afin d’obtenir une haute disponibilité et une distribution géographique du déploiement afin de réduire la latence de Teams à l’enregistreur. De plus, on s’attend à ce que les enregistreurs eux-mêmes soient conçus en tenant compte de la résilience et de la redondance.

Les partenaires doivent confirmer la version minimale requise des API et kits de développement logiciel (SDK) de communication Microsoft Graph avec Microsoft avant de soumettre leur solution pour certification afin de s’assurer que toutes les exigences d’intégration de l’enregistrement de conformité sont prises en charge.

Deux exigences spécifiques qui sont fondamentales pour le scénario d’enregistrement de conformité sont les suivantes :

- Le bot d’enregistreur doit être déployé dans Azure

- Le bot d’enregistreur doit s’exécuter sur une machine virtuelle Windows dans Azure

Les exigences relatives aux machines virtuelles Azure et Windows s’appliquent uniquement au composant bot Teams, ce qui signifie qu’un partenaire peut implémenter le reste de la plateforme de son choix, à condition qu’il puisse répondre aux exigences fonctionnelles et de performances appropriées pour l’enregistrement de conformité.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Attribution et provisionnement de stratégie d’enregistrement de conformité

Les administrateurs informatiques peuvent déterminer quels utilisateurs doivent être enregistrés et quels enregistreurs seront utilisés pour chaque utilisateur, en créant et en affectant des stratégies d’enregistrement de conformité. Les enregistreurs sont automatiquement invités à participer à des conversations en fonction de la configuration de ces stratégies lorsqu’une interaction de communication a lieu. Les stratégies d’enregistrement de conformité sont gérées à l’aide de [Microsoft PowerShell](./teams-powershell-overview.md) et peuvent être appliquées au niveau du locataire, de l’utilisateur et du groupe de sécurité pour chaque organisation. Vous trouverez plus d’informations sur les Microsoft Docs pour les [stratégies de réunion](./meeting-policies-overview.md), [les stratégies d’appel](./teams-calling-policy.md) et les [stratégies de groupe](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group).

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

   Voir [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy).

3. Affectez la stratégie d’enregistrement de conformité à un utilisateur.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   Voir [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy).

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Expériences utilisateur

La prise en charge des notifications est activée à l’aide des expériences client Teams. Les expériences peuvent être visuelles ou audio.

**clients Teams - avis visuel**
- Bureau/web
- Mobile (iOS/Android)
- téléphones Teams
- salles Teams

**Autres points de terminaison - Avis audio**
- Téléphones SIP
- Skype Entreprise
- Audioconférence
- Appelants RTC

> [!NOTE]
> L’enregistrement de conformité n’est pas pris en charge avec les files d’attente d’appels en mode conférence. Utilisez les files d’attente d’appels en mode transfert.
> L’enregistrement de conformité ne fonctionnera pas si les utilisateurs ont rencontré une panne Internet et effectuent et reçoivent des appels RTC à l’aide d’un SBA.

## <a name="compliance-recording-for-teams-certification-programs"></a>Enregistrement de conformité pour les programmes de certification Teams

En plus de publier des API disponibles publiquement permettant aux partenaires de développer et d’intégrer des solutions CCaaS à Teams, nous avons développé l’enregistrement de conformité pour Microsoft Teams programme de certification afin de fournir aux clients l’assurance que la solution de chaque partenaire participant a été testée et vérifiée pour fournir la qualité, la compatibilité et la fiabilité attendues des solutions Microsoft.  

Les partenaires suivants ont certifié leur solution pour Microsoft Teams.<br/><br/>

|Partenaire|Site web de la solution |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams](https://online.audiocodes.com/smarttap-360-live-for-microsoft-teams) |
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Dubber |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|Technologie insightful |[https://insightfultechnology.com/teams/](https://insightfultechnology.com/teams/) |
|NICE Engage |[https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage](https://www.nice.com/products/workforce-engagement/call-recording/air-and-engage) |
|NICE NTR |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |
|Zone rouge |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/red-box-partners/microsoft-integration/compliance-recording-for-microsoft-teams)  |
|Theta Lake |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Oak Innovation |[https://www.oakinnovate.com/clarify](https://www.oakinnovate.com/clarify) |

<br/>
Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams.<br/><br/>

|Partenaire|Site web de la solution |
|:--|:--|
|GuardRec |[https://www.guardrec.com/en/teams-compliance-recording/](https://www.guardrec.com/en/teams-compliance-recording/) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |


Cette liste sera mise à jour à mesure que d’autres partenaires rejoignent et répondent aux critères de certification.

## <a name="next-steps"></a>Étapes suivantes

Si vous êtes un fournisseur qui cherche à rejoindre le programme de certification, envoyez un e-mail à [Teamscategorypartner@microsoft.com](mailto:Teamscategorypartner@microsoft.com).
