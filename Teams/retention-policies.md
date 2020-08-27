---
title: Stratégies de conservation dans Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer: prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Dans cet article, vous allez découvrir les stratégies de rétention et savoir comment créer et gérer celles-ci dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0db8b037bdf67f920e1089ae8f67f477e85e3e06
ms.sourcegitcommit: 39fa1aee7a5e067097b126aa619be5aa099888ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903803"
---
# <a name="retention-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams

Les stratégies de conservation vous permettent de gérer plus efficacement les informations au sein de votre organisation. Utilisez les stratégies de conservation pour conserver les données requises pour se conformer aux stratégies internes, aux réglementations sectorielles ou aux besoins juridiques de votre organisation, et pour supprimer les données considérées comme un passif, que vous n’avez plus besoin de conserver ou qui n’ont pas de valeur juridique ou commerciale.

Par défaut, les données de chat, de canal et de fichier de teams sont conservées indéfiniment, sauf si vous tentez de supprimer le contenu par le biais des stratégies de rétention, des suppressions de l’utilisateur, des suppressions de l’administrateur, etc. En tant qu’administrateur, vous pouvez configurer des stratégies de rétention aux équipes pour les conversations et les messages de canal, et décider de manière proactive s’il convient de conserver les données, de les supprimer ou de les conserver pendant une période spécifique, puis de les supprimer.

Pour créer et gérer des stratégies de rétention, vous pouvez créer et gérer des stratégies de rétention dans le [Centre de conformité Microsoft 365](https://protection.office.com/) ou utiliser les cmdlets PowerShell du centre de sécurité & conformité. Vous pouvez appliquer une stratégie de conservation Teams à l’ensemble de votre organisation ou à des utilisateurs et des équipes spécifiques.

> [!NOTE]
> Nous ne prenons pas encore en charge la configuration de la conservation des messages de canal privé. La conservation des fichiers partagés dans des canaux privés est prise en charge.

Pour en savoir plus sur les stratégies de rétention pour Microsoft 365 ou Office 365, voir [vue d’ensemble des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>Procédures de rétention pour teams

Vous pouvez configurer une stratégie de conservation pour Teams ou pour toute autre charge de travail comme suit :

- **Conserver les données** : utilisez une stratégie de conservation pour garantir la conservation de vos données pour une période donnée, indépendamment de ce qui se passe dans l'application utilisateur. Les données sont conservées pour des raisons de conformité et sont disponibles pour eDiscovery jusqu’à l’expiration de la période de conservation, au terme de laquelle votre stratégie indique s’il convient de ne rien faire ou de supprimer les données. Par exemple, si vous créez une stratégie de conservation Teams pour conserver les messages de canal pendant 7 ans, les messages sont conservés pour eDiscovery pendant 7 ans, même si les utilisateurs suppriment leurs messages dans Teams.
- **Supprimer les données** : utilisez une stratégie de conservation pour supprimer des données afin de vous assurer qu’elles ne constituent pas une responsabilité pour votre organisation. Lorsque vous supprimez des données avec une stratégie de conservation Teams, celles-ci sont supprimées définitivement de tous les emplacements de stockage du service Teams.

Avec les stratégies de conservation pour Teams, vous pouvez :

- Conserver les conversations et/ou les messages de canal Teams pour une période donnée, puis ne rien faire.
- Conserver les conversations et/ou les messages de canal Teams pour une période donnée, supprimer les données.
- Supprimer les conversations et/ou les messages de canal Teams après une période donnée.

> [!NOTE]
> N'oubliez pas que dans Teams, les fichiers que les utilisateurs partagent dans des chats privés sont stockés dans le compte OneDrive Entreprise de l'utilisateur qui a partagé le fichier. De même, les fichiers que les membres d’une équipe chargent dans une conversation de canal sont stockés sur le site SharePoint de l'équipe. Par conséquent, pour conserver ou supprimer des fichiers dans Teams, créez des stratégies de conservation qui s'appliquent à OneDrive Entreprise et SharePoint Online.

Les utilisateurs peuvent continuer à travailler avec les données soumises à une stratégie de conservation car celles-ci sont conservées dans leur emplacement d’origine. Si un utilisateur modifie ou supprime les données soumises à la stratégie, une copie est enregistrée dans un emplacement sécurisé et est conservée tant que la stratégie est en vigueur.

La licence minimale requise pour les stratégies de conservation est Office 365 E3. Pour en savoir plus sur les licences, consultez la rubrique [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-work"></a>Fonctionnement des stratégies de conservation Teams

Les discussions d’équipe sont stockées dans un dossier masqué (Teamschat) de la boîte aux lettres de chaque utilisateur dans la conversation, et les messages de canal d’équipe sont stockés dans un dossier masqué (Teamschat) dans la boîte aux lettres de groupe pour une équipe. Teams utilise un service de conversation basé sur Azure qui stocke également ces données et, par défaut, ce service stocke les données sans limite de durée. Lorsque vous supprimez des données avec une stratégie de conservation Teams, celles-ci sont supprimées définitivement des boîtes aux lettres Exchange et du service de conversation sous-jacent.

Lorsque vous appliquez une stratégie d' **attente de rétention** aux discussions d’équipe ou aux messages de canal, voici ce qui se produit :

- Si une discussion ou un message de canal est modifié ou supprimé par un utilisateur au cours de la période de rétention, le message est copié (s’il a été modifié) ou déplacé (s’il a été supprimé) vers le dossier SubstrateHolds et stocké depuis la fin de la période de rétention. Si la stratégie est configurée pour supprimer des données à l’expiration de la période de conservation, les messages sont supprimés définitivement le jour où la période de conservation expire.
- Si une conversation ou un message de canal n’est pas supprimé par un utilisateur pendant la période de **conservation** , le message est déplacé vers le dossier SubstrateHolds dans un délai d’un jour après la fin de la période de rétention. Si la stratégie est configurée pour supprimer les données à l'expiration de la période de conservation, le message est définitivement supprimé un jour après son déplacement vers le dossier.

Lorsque vous appliquez une stratégie de **Suppression de rétention** aux conversations et messages de canal de teams, voici ce qui se produit :

- Lorsqu’une conversation ou un message de canal expire, c’est-à-dire que l’âge du message n’est pas autorisé par la stratégie de **Suppression de rétention** , un service principal, identifie les messages expirés et commence à les supprimer dans le stockage principal (utilisateur ou boîte aux lettres du groupe).
- Une fois qu’un message a été supprimé du stockage principal, un processus est déclenché de suppression du même message dans l’application teams de l’utilisateur et du service Azure chat. Pour que les messages soient supprimés dans l’application Teams, l’application doit être connectée à Internet et rester dans l’état inactif (aucune activité de l’utilisateur), de sorte que le processus de suppression n’interférerait pas dans l’interface utilisateur. Dans la mesure où un utilisateur peut avoir plusieurs appareils, qui peuvent se trouver dans des États différents, les suppressions de rétention ne se synchronisent pas avec ces périphériques en même temps.
- Après la suppression des messages dans le stockage principal, ces messages ne s’affichent plus dans les rapports de recherche de conformité tels que eDiscovery.

> [!NOTE]
> Le même flux fonctionne pour les conversations d’interopérabilité Skype Entreprise Online et Teams. Lorsqu’une conversation Skype Entreprise Online intervient dans Teams, celle-ci devient un message de la conversation Teams et est stockée dans la boîte aux lettres appropriée. Les stratégies de conservation Teams supprimeront ces messages du fil de conversation Teams. Cependant, si l'historique des conversations est activé pour Skype Entreprise Online et par le côté client Skype Entreprise Online, ceux-ci sont enregistrés dans une boîte aux lettres. Ces données de conversation ne sont pas gérées par une stratégie de conservation Teams.

> [!NOTE]
> La suppression des messages est définitive et irréversible.

Les stratégies de conservation dans Teams sont basées sur la date de création des messages de chat ou de canal et sont rétroactives. En d’autres termes, si vous créez une stratégie de conservation pour supprimer des données datant de plus de 90 jours, les données Teams créées il y a plus de 90 jours sont supprimées.

Il est possible qu’une stratégie de conservation appliquée à SharePoint Online ou OneDrive Entreprise supprime un fichier référencé dans une conversation ou un message de canal Teams avant la suppression de ces messages. Dans ce cas, le fichier apparaîtra toujours dans le message Teams, mais lorsque les utilisateurs cliquent sur le fichier, le message d’erreur « fichier introuvable » s’affiche. Cela peut également se produire en l’absence de stratégie, si quelqu’un supprime manuellement un fichier de SharePoint Online ou OneDrive Entreprise.

### <a name="considerations-and-limitations"></a>Considérations et limitations

Voici quelques considérations et limitations à prendre en compte lorsque vous travaillez avec des stratégies de conservation Teams :

- Teams nécessite une stratégie de conservation distincte des autres charges de travail. En d’autres termes, vous devez créer des stratégies de conservation spécifiques pour les conversations et/ou les messages de canal Teams. Pour cette raison, vous ne pouvez pas inclure Teams dans les stratégies de conservation à l’échelle de l’organisation.

- Les messages de canal privé ne sont pas pris en charge. Actuellement, les stratégies de conservation créées pour Teams s’appliquent uniquement aux messages de canal standard.

- Teams ne prend pas en charge les paramètres de conservation avancés, comme la possibilité d’appliquer une stratégie au contenu avec des mots clés ou des informations sensibles. Actuellement, les stratégies de conservation dans Teams s’appliquent à tous les contenus de conversation et/ou de canal.

- Une stratégie de rétention teams déclenche un processus de suppression des conversations et des messages de canal lorsque ces messages expirent (en fonction de la date de création du message). Toutefois, en fonction de la charge de service, il est possible que vous deviez supprimer définitivement ces messages du stockage principal et de l’application Teams. De plus, ces messages pourront être recherchés avec des outils de mise en conformité (eDiscovery, recherche d’utilisateur final) jusqu’à ce qu’ils soient supprimés de manière définitive du stockage principal.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Politiques de conservation multiples et principes de conservation

Si vous configurez des stratégies de conservation multiples Teams avec des durées variables, les [principes des stratégies de conservation](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) s’appliquent. Voici un aperçu de ce qui passe en priorité :

- La conservation prévaut toujours sur la suppression
- La période de conservation la plus longue prévaut toujours
- L'inclusion explicite prévaut sur l'inclusion implicite en termes d’emplacements
- La période de suppression la plus courte prévaut

## <a name="when-to-use-retention-policies-for-teams"></a>Quand utiliser les politiques de conservation pour Teams

Dans de nombreux cas, les organisations considèrent les données de conversation privé plus comme une responsabilité que les messages de canal, qui sont généralement des conversations plus liées au projet.

Vous pouvez configurer des stratégies de conservation distinctes pour les conversations privées (1:1 ou 1 : plusieurs conversations) et les messages de canal. Vous pouvez également configurer des stratégies uniques qui s'appliquent à des utilisateurs ou des équipes spécifiques de votre organisation. Pour les conversations Teams, vous pouvez sélectionner les utilisateurs auxquels la stratégie s’applique. Pour les conversations Teams, vous pouvez sélectionner les équipes auxquels la stratégie s’applique.

Par exemple, pour les messages de canal, vous pouvez appliquer une stratégie de suppression d’un an à des équipes spécifiques au sein de votre organisation et appliquer une stratégie de suppression de trois ans à toutes les autres équipes.

## <a name="manage-retention-policies-for-teams"></a>Gérer les stratégies de conservation pour Teams

### <a name="using-the-security--compliance-center"></a>Utiliser le Centre de sécurité et conformité

#### <a name="create-a-retention-policy"></a>Création d’une stratégie de conservation

Pour créer une stratégie de conservation pour les conversations et les messages de canal Teams, procédez comme suit :

1. Dans le volet gauche du Centre de sécurité et conformité, cliquez sur **Gouvernance des données**  >  **Conservation**.
2. Sélectionnez **Créer**.
3. Sur la page **Nommez votre stratégie**, entrez un nom et une description pour votre stratégie, puis cliquez sur **Suivant**.
4. Dans la page **Paramètres**, indiquez si vous souhaitez conserver les données, les supprimer, ou les deux, la période de conservation, puis cliquez sur **suivant**.
5. Dans la page **Choisir les emplacements**, procédez comme suit, puis cliquez sur **Suivant** :

    - Pour appliquer la stratégie à des messages de canal, activez **Messages de canal Teams**.  Si vous souhaitez appliquer la stratégie à des équipes spécifiques au sein de votre organisation, sélectionnez **Choisir les équipes**, puis sélectionnez les équipes de votre choix.
    - Pour appliquer la stratégie aux conversations, activez **Conversations Teams**. Si vous souhaitez appliquer la stratégie à des utilisateurs spécifiques au sein de votre organisation, sélectionnez **Choisir les utilisateurs**, puis sélectionnez les utilisateurs de votre choix.
      > [!NOTE]
      > Lorsque vous activez **les messages de canal Teams** et/ou **les conversations Teams**, tous les autres emplacements sont automatiquement désactivés. Une stratégie de conservation Teams peut inclure uniquement les emplacements Teams.

        ![Capture d'écran des messages de canal Teams et des options de conversations Teams sur la page Choisir des emplacements](media/retention-policies-create.png)

      > [!IMPORTANT]
      > Les discussions d’équipe et les messages de canal ne sont pas affectés par les stratégies de rétention appliquées aux boîtes aux lettres d’utilisateur ou de groupe dans les emplacements de **messagerie Exchange** ou de **groupes Microsoft 365** . Même si les conversations et les messages de canal Teams sont stockés dans Exchange, ils sont uniquement affectés par une stratégie de conservation appliquée à l’emplacement Teams.

6. Vérifiez vos paramètres, et lorsque vous êtes prêt, sélectionnez **créer cette stratégie**.

#### <a name="edit-a-retention-policy"></a>Modifier une stratégie de conservation

Pour modifier une stratégie de conservation Teams, procédez comme suit :

1. Dans le volet gauche du Centre de sécurité et conformité, cliquez sur **Gouvernance des données**  >  **Conservation**.
2. Dans la liste des stratégies de conservation, cochez la case en regard de la stratégie de conservation que vous souhaitez modifier.
3. Sélectionnez **modifier** en regard de ce que vous voulez modifier, apportez vos modifications, cliquez sur **enregistrer**, puis cliquez sur **Fermer**.

    ![Capture d'écran des messages de canal Teams et des options de conversations Teams sur la page Choisir des emplacements](media/retention-policies-edit.png)

> [!WARNING]
> Si vous avez configuré des équipes spécifiques ou des utilisateurs spécifiques à inclure pour les messages de canaux des équipes ou les discussions d’équipe, et que vous les modifiez pour supprimer le dernier emplacement pour l’emplacement, la configuration de cet emplacement devient **tout**. Assurez-vous qu’il s’agit de la configuration que vous envisagez avant d’enregistrer la stratégie.
> 
> Par exemple, si vous avez spécifié un utilisateur de la discussion d’équipes à inclure dans votre stratégie de rétention configurée pour supprimer des données, puis que vous modifiez la stratégie pour supprimer cet utilisateur, tous les utilisateurs seront ensuite soumis à la stratégie de rétention qui supprime définitivement leurs messages de discussion. La même chose s’applique également aux messages des canaux des équipes.
> 
> Dans ce scénario, activez le paramètre emplacement si vous ne voulez pas que le paramètre **tous** pour les messages de canal teams ou les messages de chat teams soient soumis à la stratégie de rétention. Vous pouvez également spécifier les exclusions à exempter de la stratégie.


#### <a name="delete-a-retention-policy"></a>Supprimer une stratégie de conservation

Pour supprimer une stratégie de conservation Teams, procédez comme suit :

1. Dans le volet gauche du Centre de sécurité et conformité, cliquez sur **Gouvernance des données**  >  **Conservation**.
2. Dans la liste des stratégies de-conservation, cochez la case en regard de la stratégie de conservation que vous souhaitez supprimer.
3. Sélectionnez **Supprimer la stratégie**.

### <a name="end-user-experience"></a>Utilisation de l’utilisateur final

Pour les discussions privées (discussions 1:1) ou les discussions de groupe, les utilisateurs finaux verront que les discussions antérieures à la configuration de la stratégie de rétention sont supprimées et qu’un message de contrôle indiquant « nous avons supprimé plus ancien message en raison de la stratégie de rétention de votre organisation » s’affiche dans la partie supérieure de messages encore non supprimés.
:::image type="content" source="media/retention-policies-image1.png" alt-text="Capture d’écran de la rétention des conversations":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Capture d’écran de la rétention des discussions de groupe":::

Pour les messages de canal, les utilisateurs finaux (membres du canal) verront que les messages supprimés disparaissent de l’affichage une fois les messages expirés. Si le message supprimé était un message parent d’une conversation thématique, alors, à la place du message parent, un message indiquant « ce message a été supprimé en raison d’une stratégie de rétention » s’affiche.

:::image type="content" source="media/retention-policies-image3.png" alt-text="Capture d’écran du canal avant la rétention":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Capture d’écran du canal après rétention":::

> [!NOTE]
> La messagerie de l’utilisateur final n’est pas modifiable par l’utilisateur ou par l’administrateur pour le moment.


### <a name="using-powershell"></a>Utiliser PowerShell

Pour créer et gérer des stratégies de rétention d’équipes à l’aide de [Security & PowerShell Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell), utilisez les applets de commande suivantes :

|Stratégie|Règle|
|---|---|
|[Nouveau-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [Nouveau-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problèmes connus

Les problèmes suivants sont rencontrés pour les stratégies de conservation dans Teams et font l'objet d'un suivi et d'une enquête.

- Sous **choisir des équipes** dans la ligne d’emplacement des **messages de canal teams** , vous pouvez voir les groupes Microsoft 365 qui ne sont pas également équipes. Ce problème sera corrigé à l'avenir.

- Sous **Sélectionnez les utilisateurs** dans la ligne d’emplacement **Conversations Teams**, vous pouvez voir les invités et les utilisateurs qui n’utilisent pas la boîte aux lettres. Les stratégies de conservation ne sont pas censées être définies pour les invités et nous travaillons afin de les supprimer de la liste.

- L’Assistant ELC (Exchange Life cycle Assistant) s’exécute quotidiennement, mais la latence est connue pour s’exécuter jusqu’à 7 jours, dans certains cas. Par conséquent, si vous avez une stratégie de conservation Teams pour supprimer des éléments datant de plus de 60 jours, il est possible que ces éléments soient conservés pendant 67 jours. Il ne s’agit pas d’une situation nouvelle : elle suit le modèle Exchange. Bien sûr, dans la plupart des cas, il n’y a aucun décalage.

## <a name="related-topics"></a>Sujets associés

- [Présentation des stratégies de conservation](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
