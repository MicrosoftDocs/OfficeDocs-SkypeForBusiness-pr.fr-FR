---
title: 'FAQ : stratégies de conservation dans Microsoft Teams'
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Forum aux questions sur les stratégies de rétention dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 955006d952454e31698156fa89e2a2047cff823b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243552"
---
# <a name="microsoft-teams-retention-policies-faq"></a>FAQ : stratégies de conservation dans Microsoft Teams

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Quels types de stratégies puis-je configurer dans les stratégies de rétention et comment les utiliser?

Dans le centre de sécurité & conformité, lorsque vous configurez une stratégie de rétention pour teams ou pour toute autre charge de travail, vous pouvez définir deux types principaux de stratégies: 
- Préservation: ces stratégies garantissent la conservation de vos données pour une période donnée, indépendamment des outils de l’utilisateur final. Ils garantissent la conservation des données pour des raisons de conformité et sont disponibles dans eDiscovery jusqu’à expiration de cette période. Après l’expiration de ce délai, votre stratégie peut indiquer s’il convient de ne rien faire ou de supprimer les données. Dans Teams, si vous créez une stratégie de conservation pour 7 ans, même si les utilisateurs finaux suppriment leurs messages Teams, ces messages sont toujours conservés pour l’eDiscovery pendant 7 ans.
- Suppression: ces stratégies garantissent que les données ne sont pas une responsabilité pour votre organisation. Après la durée spécifiée, les données sont supprimées de tout le stockage approprié dans Teams. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Est-il possible d’inclure teams dans des stratégies à l’échelle de l’Organisation? 

Non, pas pour le moment. Vous devez créer des stratégies spécifiques pour les discussions d’équipe et les messages de canal à l’aide de la ligne d’emplacement teams ou des applets de cmdlet teams: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Ces applets de applet disposent également de versions Get et Set.

### <a name="are-these-retention-policies-retroactive"></a>Ces stratégies de rétention sont-elles rétroactivement? 

Oui, c’est. Si vous créez une stratégie de rétention pour supprimer des données de plus de 60 jours, des données d’équipe sont créées plus de 60 jours. 

### <a name="what-is-the-default-retention-policy"></a>Qu’est-ce que la stratégie de rétention par défaut? 

Par défaut, les données de chat, de canal et de fichiers de teams sont conservées définitivement. Un utilisateur peut supprimer un message, mais en l’absence de stratégies de rétention, les données de teams sont toujours archivées dans les boîtes aux lettres Exchange Online (utilisateur et groupe) et restent là pour la découverte électronique. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Puis-je cibler des groupes d’utilisateurs ou d’équipes dans une stratégie? 

Oui, c’est. Dans l’Assistant de création de stratégie, à l’étape emplacements, vous pouvez inclure ou exclure des équipes (**messages de canal teams**) ou des utilisateurs (**discussions d’équipe**) et créer des stratégies ciblées pour votre organisation. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Quelle est la différence majeure entre l’utilisation de la ligne d’emplacement des boîtes aux lettres de groupe et la ligne d’emplacement des messages de canal équipes dans les stratégies de rétention? 

Si vous utilisez les lignes de boîte aux lettres de groupe et d’emplacement des boîtes aux lettres d’utilisateur pour Exchange Online, les données d’équipe seront supprimées des boîtes aux lettres spécifiées. Toutefois, cela supprime uniquement les données de la boîte aux lettres. Les autres données de teams sont supprimées, telles que le service de discussion. Nous vous recommandons d’utiliser des stratégies de rétention aux équipes pour gérer correctement toutes les données de l’équipe. Une stratégie de rétention teams supprime les données de teams de tous les emplacements de stockage (boîtes aux lettres, service de chat, clients Teams). 

Remarque: le lancement de la fonctionnalité stratégies de rétention pour les équipes vérifie que seules les stratégies d’équipe suppriment les éléments des équipes stockés dans les emplacements des boîtes aux lettres Exchange (utilisateur ou groupe). Les autres stratégies de configuration des boîtes aux lettres ne peuvent pas affecter les éléments Teams. C’est vrai auparavant, mais a été corrigé par le lancement de la fonctionnalité stratégies de rétention. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Qu’advient-il des discussions par le biais des stratégies de rétention de Skype entreprise Online et de teams?

Oui, Skype entreprise Online et les discussions d’interopérabilité teams fonctionnent de la même manière. Une fois la discussion de Skype entreprise Online transmise en équipe, elle devient un message dans un fil de discussion d’équipe et est intégré à la boîte aux lettres appropriée. Le même flux fonctionne donc: les stratégies de suppression d’équipes suppriment ces messages du thread Teams. Toutefois, si l’historique des conversations est activé pour Skype entreprise Online et que le client de Skype entreprise Online est enregistré dans une boîte aux lettres, les données de cette discussion ne sont pas gérées par une stratégie de rétention Teams.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Est-il possible de procéder de la sorte par le biais des cmdlets de Security & Compliance Center? Que dois-je utiliser? 

Essentielle. Vous pouvez créer des stratégies de rétention d’équipes à l’aide des [cmdlets PowerShell du centre de sécurité & conformité]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Notez qu’il ne s’agit pas de cmdlets Exchange Online. Voici les applets de cmdlet créées pour Teams. Ils suivent la nomenclature et le style des cmdlets de rétention actuellement disponibles dans le centre de sécurité & conformité.

|Politique|Elle|
|---|---|
|[Nouveau-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nouveau-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>S’il existe plusieurs stratégies de rétention pour les équipes ayant des durées variables, lesquelles gagnent-elles?

Nous suivirons les [principes des stratégies de](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)rétention et nous vous conseillons de le faire. La réponse courte est la suivante: 
-   La conservation est toujours WINS lors de la suppression
-   Période de conservation la plus longue toujours WINS
-   Inclusion explicite du WINS sur une inclusion implicite en termes d’emplacements
-   Durée de suppression la plus courte
