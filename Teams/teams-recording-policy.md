---
title: Présentation de l'enregistrement de stratégie Teams pour les appels & réunions
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
description: En savoir plus sur l'enregistrement de stratégie Teams pour les appels & réunions
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
ms.openlocfilehash: d5721f13a569ee240c33f2bf4262eb84966065d6
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874460"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a>Présentation de l'enregistrement de stratégie Teams pour les appels et & réunions

L'enregistrement basé sur une stratégie permet aux organisations qui adoptent Microsoft Teams pour les appels et les réunions d'être en cours d'utilisation, à l'aide d'une stratégie d'administration, lorsque les appels et les réunions en ligne doivent être enregistrés et capturés automatiquement pour un traitement et une rétention ultérieurs, comme requis par la stratégie d'entreprise ou réglementaires pertinente.

Teams a été amélioré pour prendre en charge l'intégration de solutions d'enregistrement tierces, notamment les fonctionnalités de plateforme, les expériences utilisateur et les interfaces d'administration nécessaires pour fournir une solution de bout en bout pour la configuration, la gestion, l'enregistrement, le stockage et l'analyse des communications Teams. Les améliorations ont été apportées aux API de plateforme de communication et aux événements pour l'enregistrement, qui offrent les possibilités suivantes :

- Capture transparente et de haute qualité des médias sur tous les appareils et tous les points de terminaison pris en charge pour l'audio, la vidéo, le partage d'écran et la conversation.

- Prise en charge de la capture d'interaction entre les utilisateurs de Teams et points de terminaison d'appel pris en charge (Teams, Teams Mobile, Skype Entreprise, PSTN)

- Nouvelles stratégies d'administration pour l'enregistrement de la conformité, notamment l'intégration aux stratégies et outils d'appel d'administration et de réunion Teams existants

L'enregistrement de conformité peut être activé sur Microsoft 365 A3/A5/E3/E5/Business Premium et les utilisateurs d'Office 365 A3/A5/E3/E5. 

Les fonctionnalités d'intégration de la solution d'enregistrement de la conformité ont également été examinées dans Ignite 2019 dans l'enregistrement de [<span class="underline">conformité et la session Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)

## <a name="teams-interaction-recording-overview"></a>Vue d'ensemble de l'enregistrement de l'interaction Teams

Les cas d'utilisation des enregistrements d'interaction peuvent être séparés en quatre catégories principales de fonctionnalités d'enregistrement : Commodité, Fonctionnel, Organisationnel et Origine légitime, comme illustré dans l'image :

![Capture d'écran montrant l'enregistrement de l'interaction.](media/recording-taxonomy.png "L'image affiche les catégories d'enregistrements.")

Chacune de ces catégories implique des exigences différentes en matière de procédure d'enregistrement, d'enregistrement, de stock des enregistrements, d'notification, de contrôle de l'accès et de gestion de la rétention.

| Type                   | Commodité (enregistrement Teams normal) | Organisation - Régulée (enregistrement de conformité) |
| ---------------------- | ------------------ | --------------- |
| Initiator              | Utilisateur               | Administrateur (système)  |
| Cible                 | Par appel/réunion | Par utilisateur        |
| Propriétaire du stockage          | Utilisateur               | Conformité      |
| Notification requise ? | Oui                | Oui             |
| Propriétaire d'Access           | Utilisateur               | Conformité      |
| Stratégie de rétention ?      | Facultatif           | Oui             |

Teams offre différentes fonctionnalités pour l'enregistrement [<span class="underline">pratique</span>](./cloud-recording.md) et fonctionnel de réunions et d'événements en direct. L'enregistrement organisationnel signifie permettre aux organisations qui adoptent Teams pour les appels et les réunions d'être en cours d'utilisation, par le moyen d'une stratégie administrative, lorsque les appels et les réunions en ligne doivent être enregistrés et capturés automatiquement à des fins de traitement et de rétention ultérieurs, comme requis par la stratégie d'entreprise ou réglementaires pertinente. Les utilisateurs dans le cadre de cette stratégie se rendront compte que leurs interactions numériques avec Teams sont enregistrées, mais ne pourront pas désactiver l'enregistrement et n'auront pas accès à l'enregistrement une fois l'interaction terminée. L'enregistrement devient partie intégrante de l'archive organisationnelle mise à la disposition du personnel juridique et de conformité pour la découverte électronique, la conservation légale et d'autres utilisations de la rétention d'entreprise.

## <a name="example-user-needs"></a>Exemples de besoins de l'utilisateur

<table>
<thead>
<tr class="header">
<th><strong>Personnage</strong></th>
<th><strong>Besoins</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilisateurs enregistrés</td>
<td><ul>
<li><p>Soyez informé lorsque l'enregistrement est en cours.</p></li>
<li><p>Soyez informé lorsque l'erreur de stratégie et/ou d'enregistreur entraîne des modifications du comportement des appels.</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Administrateur des communications</td>
<td><ul>
<li><p>Comprenez pourquoi et comment appliquer / appliquer des stratégies d'enregistrement aux utilisateurs/points de terminaison Teams.</p></li>
<li><p>Configurez et tenez à jour des stratégies d'enregistrement Teams pour l'organisation.</p></li>
<li><p>Surveillez et dépannage des problèmes liés à l'enregistrement des appels et réunions Teams.</p></li>
<li><p>Responsable de la conformité interne au niveau de l'analyse opérationnelle de l'utilisation, de la qualité et de la fiabilité.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>Responsable de la conformité</td>
<td><ul>
<li><p>Recueillez toutes les communications Teams de la manière requise pour respecter les obligations en matière de conformité dans les limites régionales appropriées.</p></li>
<li><p>Recherchez des interactions basées sur des métadonnées ou du contenu d'interaction liés à la communication. Voici des exemples courants :</p>
<ul>
<li><p><strong>Métadonnées</strong> - Participants, heure, itinéraire, numéro composé, numéro de départ, données métiers personnalisées</p></li>
<li><p><strong>Contenu</strong> – Transcription, sentiment, phonétique, interactions associées</p></li>
</ul></li>
<li><p>Analyser et interagir avec les communications collectées, notamment la possibilité de surveiller les interactions pendant qu'elles sont collectées.</p></li>
<li><p>Assurez la sécurité des communications collectées et empêchez les falsifications à toutes les étapes.</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a>Vue d'ensemble de l'architecture de solution

Les solutions d'enregistrement de conformité sont intégrées à Teams, comme illustré dans le diagramme suivant :

![Capture d'écran montrant le paramètre de l'application personnalisée d'équipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Les images illustrent le flux d'envoi et de réception d'une réunion ou d'un appel Teams.")

## <a name="recorder"></a>Enregistreur

Le composant principal de la solution d'enregistrement de conformité est l'enregistreur.
Les enregistreurs sont conçus sous la forme de services Azure évolutifs (bots) qui tirent parti de la plateforme de communication de Microsoft et s'inscrivent en tant [<span class="underline">qu'applications</span>](/graph/cloud-communications-concept-overview) auprès de Microsoft Graph. L'enregistreur fournit l'interaction directe avec les appels et les api de [<span class="underline">communication</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) de la plateforme teams et fournit le point de terminaison pour l'ingestion multimédia.

Un [<span class="underline">exemple d'application</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) enregistreur de conformité est disponible pour vous aider à configurer le robot, à créer l'instance d'application et à attribuer les stratégies de conformité. L'exemple présente également des exemples sur l'utilisation de l'API pour enregistrer des interactions spécifiques telles que la gestion du [<span class="underline">routage</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) d'appel [<span class="underline">entrant,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)la modification des états d'enregistrement et la suppression de l'utilisateur en [<span class="underline">cours d'enregistrement.</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)
Vous pouvez trouver de la documentation graphique sur les API spécifiques ici pour [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) et [<span class="underline">incomingContext.</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0)

L'implémentation exacte du service d'enregistreur variera selon le partenaire, mais doit être conçue pour prendre en charge plusieurs enregistreurs afin d'obtenir une haute disponibilité et une distribution géographique du déploiement afin de réduire la latence entre Teams et l'enregistreur. En outre, il est prévu que les enregistreurs eux-mêmes soient conçus avec une résilience et une redondance à l'esprit.

Les partenaires doivent confirmer la version de publication minimale requise des API et des SDK de Microsoft Graph communications avec Microsoft avant de soumettre leur solution pour certification afin de s'assurer que toutes les exigences d'intégration de l'enregistrement de conformité sont pris en charge.

Deux conditions spécifiques fondamentales pour le scénario d'enregistrement de conformité sont les suivants :

- Le robot enregistreur doit être déployé dans Azure

- Le robot enregistreur doit s'exécuter sur une VM Windows dans Azure

Les exigences relatives à la gestion des appareils VM Azure et Windows s'appliquent uniquement au composant Teams Bot, ce qui signifie qu'un partenaire peut implémenter le reste de la plateforme de son choix, à condition qu'il réponde aux exigences fonctionnelles et de performances pertinentes pour l'enregistrement de la conformité.

## <a name="compliance-recording-policy-assignment-and-provisioning"></a>Affectation et mise en service des stratégies d'enregistrement de conformité

Les administrateurs informatiques peuvent déterminer les utilisateurs à enregistrer et l'enregistreur à utiliser pour chaque utilisateur, en créant et en attribuant des stratégies d'enregistrement de conformité. Les enregistreurs sont invités automatiquement à participer à des conversations en fonction de la configuration de ces stratégies lors d'une interaction de communication. Les stratégies d'enregistrement de conformité sont gérées à l'aide de [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) et peuvent être appliquées au niveau du client, par utilisateur et du groupe de sécurité pour chaque organisation. Vous trouverez davantage d'informations [<span class="underline"></span>](./meeting-policies-in-teams.md)sur les [<span class="underline"></span>](./teams-calling-policy.md) stratégies de réunion, les stratégies d'appel et les stratégies de groupe de Microsoft Docs pour [<span class="underline">les réunions.</span>](./assign-policies.md#assign-a-policy-to-a-group)

1. Créez une instance d'application dans votre client.

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

2. Créer une stratégie d'enregistrement de conformité.

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

   [<span class="underline">Set-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. Attribuez la stratégie d'enregistrement de conformité à un utilisateur.

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a>Expériences utilisateur

La prise en charge des notifications est activée à l'aide de l'expérience client Teams. Les expériences peuvent être visuelles ou audio.

**Clients Teams - remarque visuelle**
- Bureau/Web
- Mobile (iOS/Android)
- Téléphones Teams
- Salles Teams

**Autres points de terminaison - Avis audio**
- Téléphones SIP
- Skype Entreprise
- Audioconférence
- Appelants PSTN

## <a name="compliance-recording-for-teams-certification-programs"></a>Enregistrement de conformité pour les programmes de certification Teams

En plus de publier des API disponibles publiquement permettant aux partenaires de développer et d'intégrer des solutions CCaaS avec Teams, nous avons développé l'enregistrement de conformité pour le programme de certification de Microsoft Teams afin de fournir aux clients la assurance que la solution de chaque partenaire participant a été testée et vérifiée afin de fournir la qualité, la compatibilité et la fiabilité qu'ils attendent des solutions Microsoft.  

Les partenaires suivants ont certifié leur solution pour Microsoft Teams.

|Partenaire|Site web de la solution |
|:--|:--|
|ASC Technologies |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|AudioCodes |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|Dunker |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|NICE |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|Numonix |[https://numonix.cloud](https://numonix.cloud)    |

Les partenaires suivants sont en train de certifier leur solution pour Microsoft Teams.

|Partenaire|Site web de la solution |
|:--|:--|
|CallCabinet |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|Landis Technologies |[https://landistechnologies.com/](https://landistechnologies.com/) |
|Luware |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|Innovations dans Le Monde |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|Red Box |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|Verint |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|Lac Ntêta |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

Cette liste est mise à jour à mesure que de nouveaux partenaires rejoignent et répondent aux critères de certification.

## <a name="next-steps"></a>Étapes suivantes

Si vous êtes un fournisseur désireux de participer au programme de certification, veuillez envoyer un <a href= "mailto:Teamscategorypartner@microsoft.com">e-mail Teamscategorypartner@microsoft.com.</a>
