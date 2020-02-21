---
title: Stratégies de conservation dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: En savoir plus sur les stratégies de rétention et la création et la gestion de celles-ci dans Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160748"
---
# <a name="retention-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams

Les stratégies de rétention vous permettent de gérer plus efficacement les informations de votre organisation. Utilisez des stratégies de rétention pour conserver les données nécessaires conformément aux politiques internes de votre organisation, aux réglementations sectorielles ou aux besoins juridiques, ainsi qu’à la suppression des données considérées comme une responsabilité, que vous n’avez plus besoin de conserver ou qu’il n’y a plus aucune valeur commerciale ou morale.

Par défaut, les données de chat, de canal et de fichiers de teams sont conservées définitivement. En tant qu’administrateur, vous pouvez configurer des stratégies de rétention aux équipes pour les conversations et les messages de canal, et décider de manière proactive s’il convient de conserver les données, de les supprimer ou de les conserver pendant une période spécifique, puis de les supprimer.

Pour créer et gérer des stratégies de rétention, vous pouvez créer et gérer des stratégies de rétention pour les équipes et les autres charges de travail dans le [Centre de sécurité & conformité Office 365](https://protection.office.com/) ou à l’aide des applets de & Vous pouvez appliquer une stratégie de rétention aux équipes pour l’ensemble de votre organisation ou pour des utilisateurs et des équipes spécifiques.

> [!NOTE]
> Nous ne prenons pas encore en charge la configuration de la conservation des messages de canal privé. La conservation des fichiers partagés dans des canaux privés est prise en charge.

Pour en savoir plus sur les stratégies de rétention pour Office 365, voir [vue d’ensemble des stratégies de](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)rétention.

## <a name="what-are-retention-policies-for-teams"></a>Présentation des stratégies de rétention pour les équipes

Lorsque vous configurez une stratégie de rétention pour teams ou toute autre charge de travail, vous pouvez les configurer comme suit :

- **Conservation des données**: utilisez une stratégie de rétention pour vous assurer que vos données sont conservées pendant une période spécifiée, quel que soit le résultat de l’application utilisateur. Les données sont conservées pour des raisons de conformité et sont disponibles pour l’eDiscovery jusqu’à la fin de la période de rétention, après lequel votre stratégie indique s’il convient de ne rien faire ou supprimer les données. Par exemple, si vous créez une stratégie de rétention teams pour conserver les messages de canal pendant 7 ans, les messages sont conservés pour l’eDiscovery pendant 7 ans, même si les utilisateurs suppriment leurs messages dans Teams.
- **Supprimer des données**: utilisez une stratégie de rétention pour supprimer des données afin de vous assurer qu’il ne s’agit pas d’une responsabilité pour votre organisation. Avec une stratégie de rétention Teams, lorsque vous supprimez des données, celle-ci est supprimée de manière définitive de tous les emplacements de stockage du service Teams.

Grâce aux stratégies de rétention pour les équipes, vous pouvez :

- Conservez les discussions d’équipes et/ou les messages de canal pour une durée spécifiée et ne faites rien.
- Conservez les discussions d’équipes et/ou les messages de canal pour une durée spécifiée, puis supprimez les données.
- Supprimer des discussions d’équipes et/ou des messages de canal après une durée spécifiée.

> [!NOTE]
> Rappelez-vous que dans Teams, les fichiers partagés par les utilisateurs dans les discussions privées sont stockés dans le compte OneDrive entreprise de l’utilisateur qui a partagé le fichier. De plus, les fichiers chargés d’une équipe sur une conversation de canal sont stockés sur le site SharePoint de l’équipe. Par conséquent, pour conserver ou supprimer des fichiers dans Microsoft Teams, créez des stratégies de rétention qui s’appliquent à OneDrive entreprise et à SharePoint Online.

Lorsque les données sont soumises à une stratégie de rétention, les utilisateurs peuvent continuer à travailler dessus, car les données sont conservées dans leur emplacement d’origine. Si un utilisateur modifie ou supprime les données soumises à la stratégie, une copie est enregistrée à un emplacement sécurisé dans lequel la stratégie est en vigueur.

La configuration minimale requise pour les licences pour les stratégies de rétention est Office 365 E3. Pour en savoir plus sur les licences, voir gestion [des licences Office 365 pour teams](Office-365-licensing.md).

## <a name="how-teams-retention-policies-work"></a>Fonctionnement des stratégies de rétention des équipes

Les discussions d’équipe sont stockées dans un dossier SubstrateHolds caché de la boîte aux lettres de chaque utilisateur dans la conversation, et les messages de canal d’équipe sont stockés dans un dossier SubstratesHolds caché de la boîte aux lettres de groupe pour une équipe. Teams utilise un service de chat d’Azure qui stocke également ces données, et par défaut ce service stocke les données de façon permanente. Avec une stratégie de rétention Teams, lorsque vous supprimez des données, celles-ci sont définitivement supprimées des boîtes aux lettres Exchange et du service de conversation sous-jacent.

Lorsque vous appliquez une stratégie de rétention aux discussions d’équipes et aux messages de canal, voici ce qui se produit :

- Si une discussion ou un message de canal est modifié ou supprimé par un utilisateur au cours de la période de rétention, le message est copié (s’il a été modifié) ou déplacé (s’il a été supprimé) vers le dossier SubstrateHolds et stocké depuis la fin de la période de rétention. Si la stratégie est configurée pour supprimer des données au moment de la fin de la période de rétention, les messages sont supprimés de manière définitive le jour de la période de rétention.
- Si une conversation ou un message de canal n’est pas supprimé par un utilisateur pendant la période de rétention, le message est déplacé vers le dossier SubstrateHolds dans un délai d’un jour après la fin de la période de rétention. Si la stratégie est configurée pour supprimer des données au moment de la fin de la période de rétention, le message est supprimé de manière définitive d’un jour après son déplacement dans le dossier.

> [!NOTE]
> Le même flux fonctionne pour les discussions d’interopérabilité entre Skype entreprise Online et Teams. Lorsqu’une discussion Skype entreprise Online se trouve dans Teams, elle devient un message dans un fil de discussion teams et est intégré à la boîte aux lettres appropriée. Les stratégies de rétention teams suppriment ces messages du thread Teams. Toutefois, si l’historique des conversations est activé pour Skype entreprise Online et que le client Skype entreprise Online est enregistré dans une boîte aux lettres, ces données ne sont pas gérées par une stratégie de rétention Teams.

Les stratégies de rétention dans teams sont basées sur la date de création des conversations ou messages de canal et sont rétroactives. En d’autres termes, si vous créez une stratégie de rétention pour supprimer des données de plus de 90 jours, les données de teams créées depuis plus de 90 jours sont supprimées.

Il est possible qu’une stratégie de rétention appliquée à SharePoint Online ou OneDrive entreprise puisse supprimer un fichier référencé dans une conversation d’équipe ou un message de canal avant que ces messages soient supprimés. Dans ce scénario, le fichier s’affichera toujours dans le message Teams, mais lorsque les utilisateurs cliquent sur le fichier, ils reçoivent une erreur « fichier introuvable ». Ce problème peut également se produire en l’absence de stratégie, si une personne supprime manuellement un fichier de SharePoint Online ou OneDrive entreprise.

### <a name="considerations-and-limitations"></a>Considérations et limitations

Voici quelques considérations et limitations à connaître lorsque vous travaillez avec des stratégies de rétention aux équipes :

- Teams nécessite une stratégie de rétention distincte des autres charges de travail. En d’autres termes, vous devez créer des stratégies de rétention spécifiques pour les discussions d’équipes et/ou les messages de canal. Pour cette raison, vous ne pouvez pas inclure d’équipes dans des stratégies de rétention à l’échelle de l’organisation.

- Les messages des canaux privés ne sont pas pris en charge. Pour le moment, les stratégies de rétention pour les équipes s’appliquent uniquement aux messages de canal standard.

- Teams ne prend pas en charge les paramètres de rétention avancés, tels que la possibilité d’appliquer une stratégie au contenu comportant des mots clés ou des informations sensibles. Pour l’instant, les stratégies de rétention dans teams s’appliquent à tout le contenu des messages de conversation et/ou de canal.

- Le nettoyage des messages expirés risque de durer trois jours. Une stratégie de rétention teams supprimera les discussions et les messages de canal dès la fin de la période de rétention. Toutefois, le nettoyage de ces messages risque de durer jusqu’à 3 jours. De plus, les conversations et les messages de canal pourront être utilisés dans les outils eDiscovery entre le moment de la période de rétention et le moment où les messages sont supprimés de manière définitive.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Plusieurs stratégies de rétention et principes de rétention

Si vous configurez plusieurs stratégies de rétention aux équipes avec des durées variables, les [principes des politiques de rétention](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) s’appliquent. Voici un aperçu des éléments à prendre en priorité :

- La conservation est toujours WINS lors de la suppression
- Période de conservation la plus longue toujours WINS
- Inclusion explicite du WINS sur une inclusion implicite en termes d’emplacements
- Durée de suppression la plus courte

## <a name="when-to-use-retention-policies-for-teams"></a>Quand utiliser des stratégies de rétention pour les équipes

Dans de nombreux cas, une entreprise considère qu’il s’agit d’une plus grande responsabilité par le biais de messages de canal, qui sont généralement davantage des conversations relatives au projet.

Vous pouvez configurer des stratégies de rétention distinctes pour les discussions privées (1:1 ou 1 : plusieurs discussions) et des messages de canal. Vous pouvez également configurer des stratégies uniques qui s’appliquent à des utilisateurs ou des équipes spécifiques au sein de votre organisation. Pour les discussions d’équipe, vous pouvez sélectionner les utilisateurs auxquels la politique s’applique. Pour les messages de canal Teams, vous pouvez sélectionner les équipes auxquelles la stratégie s’applique.

Par exemple, dans le cas de messages de canal, vous pouvez appliquer une stratégie de suppression d’une année à des équipes spécifiques au sein de votre organisation et appliquer une stratégie de suppression de trois ans à toutes les autres équipes.

## <a name="manage-retention-policies-for-teams"></a>Gérer les stratégies de rétention pour les équipes

### <a name="using-the-security--compliance-center"></a>Utiliser le centre de sécurité & conformité

#### <a name="create-a-retention-policy"></a>Créer une stratégie de rétention

Pour créer une stratégie de rétention pour les discussions d’équipe et les messages de canal, procédez comme suit :

1. Dans le volet de navigation de gauche du centre de sécurité & conformité, accédez à**rétention** **gouvernance** > d’information.
2. Sélectionnez **créer**.
3. Dans la page **nommer votre stratégie** , entrez un nom et une description pour votre stratégie, puis cliquez sur **suivant**.
4. Dans la page **paramètres** , spécifiez si vous souhaitez conserver les données, les supprimer ou les deux, la période de rétention, puis cliquez sur **suivant**.
5. Dans la page **choisir les emplacements** , procédez comme suit, puis cliquez sur **suivant**:

    - Pour appliquer la stratégie aux messages de canal, activez la case à **coéquipes messages de canal**.  Si vous voulez appliquer la stratégie à des équipes spécifiques de votre organisation, sélectionnez **choisir des équipes**, puis sélectionnez les équipes souhaitées.
    - Pour appliquer la stratégie aux discussions, activez les **discussions d’équipe**. Si vous voulez appliquer la stratégie à des utilisateurs spécifiques de votre organisation, sélectionnez **sélectionnez les utilisateurs**, puis sélectionnez les utilisateurs souhaités.
      > [!NOTE]
      > Lorsque vous activez les **messages du canal équipes** et/ou les **discussions d’équipe**, tous les autres emplacements sont automatiquement désactivés. Une stratégie de rétention teams peut inclure uniquement les emplacements des équipes.

        ![Capture d’écran des options messages de canal équipes et conversations teams dans la page Sélectionner des emplacements](media/retention-policies-create.png)

      > [!IMPORTANT]
      > Les discussions d’équipe et les messages de canal ne sont pas affectés par les stratégies de rétention appliquées aux boîtes aux lettres d’utilisateur ou de groupe dans les emplacements de **messagerie Exchange** ou **groupes Office 365** . Même si les discussions d’équipe et les messages de canal sont stockés dans Exchange, elles sont uniquement affectées par les stratégies de rétention appliquées aux emplacements des équipes.

6. Passez en revue vos paramètres, puis, lorsque vous êtes prêt, sélectionnez **créer cette stratégie**.

#### <a name="edit-a-retention-policy"></a>Modifier une stratégie de rétention

Pour modifier une stratégie de rétention Teams, procédez comme suit :

1. Dans le volet de navigation de gauche du centre de sécurité & conformité, accédez à**rétention** **gouvernance** > d’information.
2. Dans la liste des stratégies de rétention, activez la case à cocher en regard de la stratégie de rétention que vous voulez modifier.
3. Sélectionnez **modifier** en regard de ce que vous voulez modifier, apportez les modifications souhaitées, cliquez sur **Enregistrer**, puis sur **Fermer**.

    ![Capture d’écran des options messages de canal équipes et conversations teams dans la page Sélectionner des emplacements](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>Supprimer une stratégie de rétention

Pour supprimer une stratégie de rétention Teams, procédez comme suit :

1. Dans le volet de navigation de gauche du centre de sécurité & conformité, accédez à**rétention** **gouvernance** > d’information.
2. Dans la liste des stratégies de rétention, activez la case à cocher en regard de la stratégie de rétention que vous voulez supprimer.
3. Sélectionnez **Supprimer la stratégie**.

### <a name="using-powershell"></a>Utiliser PowerShell

Pour créer et gérer des stratégies de rétention d’équipes à l’aide de PowerShell, utilisez les applets de commande suivantes.

|Politique|Elle|
|---|---|
|[Nouveau-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nouveau-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problèmes connus

Vous trouverez ci-après des problèmes connus liés aux stratégies de rétention dans les équipes qui sont suivies et examinées.

- Sous **choisir des équipes** dans la ligne d’emplacement des **messages de canal teams** , vous pouvez voir les groupes Office 365 qui ne sont pas aussi équipes. Ce problème sera résolu dans le futur.

- Sous **choisir les utilisateurs** dans la ligne d’emplacement **discussions de teams** , il est possible que les utilisateurs invités et non-boîte aux lettres apparaissent. Les stratégies de rétention ne sont pas destinées à être définies pour les invités et nous travaillons à la suppression de celles-ci dans la liste.

- L’Assistant ELC (Exchange Life cycle Assistant) s’exécute quotidiennement, mais il dispose d’un SLA de 7 jours. Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention teams pour supprimer des éléments de plus de 60 jours, ces éléments peuvent persister pendant 67 jours maximum. Ce n’est pas une nouvelle situation : elle suit le modèle Exchange. Dans la plupart des cas, il n’y a aucun retard.

## <a name="related-topics"></a>Rubriques connexes

- [Vue d’ensemble des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
