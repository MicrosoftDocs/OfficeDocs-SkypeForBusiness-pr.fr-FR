---
title: 'FAQ : stratégies de conservation dans Microsoft Teams'
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Forum aux questions sur les stratégies de rétention dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14e398908a13e621d739a5a923b52588551506f8
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641334"
---
# <a name="microsoft-teams-retention-policies-faq"></a>FAQ : stratégies de conservation dans Microsoft Teams

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Quels types de stratégies puis-je configurer les stratégies de rétention et comment fonctionnent-ils ?

Dans le centre de conformité & sécurité, lorsque vous configurez une stratégie de rétention, des équipes ou pour n’importe quel autre charge de travail, vous pouvez configurer deux principaux types de stratégies : 
- Conservation : Ces stratégies assurer la préservation de vos données pour une période donnée, quel que soit ce qui se passe dans les outils de l’utilisateur final. Elles Vérifiez que les données sont conservées pour des raisons de conformité expire disponibles dans eDiscovery jusqu'à cette date. Après l’expiration du délai, votre stratégie peut indiquer s’il faut ne rien faire ou supprimer les données. Dans les équipes, si vous créez une stratégie de conservation pour 7 ans, même si les utilisateurs finaux suppriment leurs messages équipes, ces messages sont conservées pour la découverte de 7 ans.
- Suppression : Ces stratégies vous assurer que les données ne sont pas un passif pour votre organisation. Après la durée spécifiée, les données sont supprimées à partir du stockage pertinent toutes les équipes. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Pouvons nous incluons des équipes de stratégies à l’échelle de l’organisation ? 

Non, pas actuellement. Vous devez créer des stratégies spécifiques pour les messages équipes conversation et de canal à l’aide de la ligne d’emplacement équipes ou ces applets de commande équipes : [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Ces applets de commande ont obtenir et définir les versions.

### <a name="are-these-retention-policies-retroactive"></a>Ces stratégies de rétention sont rétroactif ? 

Oui, ils se trouvent. Si vous créez une stratégie de rétention pour supprimer les données de plus de 60 jours, il supprime les données des équipes créées plus de 60 jours. 

### <a name="what-is-the-default-retention-policy"></a>Qu’est la stratégie de rétention par défaut ? 

Par défaut, équipes conversation, canal et les données de fichiers sont conservées indéfiniment. Un utilisateur peut supprimer un élément, mais en l’absence de stratégies de rétention, données équipes sont toujours archivées dans Exchange online boîtes aux lettres (utilisateur et groupe) et il restent eDiscovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Puis-je cibler des ensembles d’utilisateurs ou des équipes au sein d’une stratégie ? 

Oui, vous le faire. Dans l’Assistant de création de stratégie, dans l’étape d’emplacements, vous pouvez inclure ou exclure des équipes (**équipes channel messages**) ou des utilisateurs (**conversation équipes**) et créer des stratégies cibles pour votre organisation. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Quelle est la différence principale entre l’utilisation de la ligne d’emplacement de boîte aux lettres de groupe et la ligne d’emplacement de messages de canal équipes dans les stratégies de rétention ? 

Si vous utilisez la boîte aux lettres de groupe et les lignes d’emplacement utilisateur boîte aux lettres pour Exchange Online, données équipes seront supprimées de boîtes aux lettres spécifiées. Toutefois, cela supprime uniquement données à partir de la boîte aux lettres. Elle ne supprime pas autres données équipes, telles que les salles de conversation service. Nous vous recommandons d’utiliser des stratégies de rétention équipes pour gérer correctement toutes les données d’équipes. Une stratégie de rétention équipes supprime les données d’équipes de tous les service de la conversation de boîtes aux lettres, des emplacements stockage, clients équipes. 

Remarque : Lancement de la fonctionnalité de stratégies de rétention pour les équipes permet de s’assurer que seules les stratégies équipes supprimer des éléments d’équipes stockées dans les emplacements de boîte aux lettres Exchange (groupe ou utilisateur). Autre programme d’installation de stratégies de boîtes aux lettres ne peut pas avoir une incidence sur les éléments équipes. Il a la valeur true dans le passé, mais a été corrigé avec le lancement de la fonctionnalité de stratégies de rétention. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Que se passe-t-il à Skype pour Business en ligne et les équipes conversations interopérabilitées – ils sont affectés par les stratégies de rétention ?

Oui, Skype pour Business en ligne et conversations interopérabilitées équipes fonctionnent de la même manière. Une fois le Skype pour la conversation en ligne Business entame équipes, il devient un message dans un thread de conversation équipes et obtient ingéré dans la boîte aux lettres appropriée. Afin que les mêmes flux works – stratégies de suppression des équipes supprimera ces messages à partir du thread d’équipes. Toutefois, si l’historique des conversations sont activé pour Skype pour Business Online et de la Skype pour côté client Business Online ceux sont enregistrés dans une boîte aux lettres, ces données de conversation ne sont pas gérées par une stratégie de rétention les équipes.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Puis-je faire ces par le biais de sécurité & applets de commande de centre de conformité ? Que dois-je utiliser ? 

Absolument. Vous pouvez créer des stratégies de rétention équipes à l’aide de la [sécurité & applets de commande Powershell de centre de conformité]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). N’oubliez pas que ces applets de commande Exchange Online ne sont pas. Voici les applets de commande que nous avons créée pour les équipes. Ils suivent nomenclature existant et le style à partir de la rétention des applets de commande aujourd'hui disponibles dans sécurité & centre de conformité.

|Stratégie|Règle|
|---|---|
|[Nouvelle TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nouvelle TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>S’il existe plusieurs stratégies de rétention pour les équipes avec différentes durées, laquelle wins ?

Nous principes [de stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)et nous vous recommandons de procéder trop. La réponse est simple : 
-   Conservation toujours l’emporte sur suppression
-   Conservation plus longtemps toujours wins
-   Inclusion explicite l’emporte sur l’inclusion implicite en termes d’emplacements
-   Le plus court wins période suppression
