---
title: Stratégies de mise à niveau pour les administrateurs informatiques
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Cet article s’applique aux administrateurs informatiques et décrit les stratégies d’implémentation de leur mise à niveau de Skype Entreprise vers Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681735"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Stratégies de mise à niveau pour les administrateurs informatiques

![Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation")

Cet article s’applique aux administrateurs informatiques qui souhaitent implémenter leur mise à niveau vers Teams à partir de Skype Entreprise.

Avant d’implémenter votre mise à niveau, nous vous recommandons les articles suivants qui décrivent les concepts de mise à niveau importants et les comportements de coexistence :

- [Comprendre la coexistence et l’interopérabilité Microsoft Teams et Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Options de mise à niveau

Cette section explique comment implémenter votre mise à niveau à l’aide de l’une des options de mise à niveau suivantes :

- [Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode Islands)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Mise à niveau de certaines fonctionnalités pour une organisation qui n’a pas encore commencé à utiliser Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Mise à niveau de certaines fonctionnalités pour une organisation qui utilise déjà Teams en mode Îles](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si vous avez besoin d’informations supplémentaires sur les options, vérifiez que vous avez déjà lu [Choisir votre parcours de mise à niveau de Skype Entreprise à Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode Islands)

Pour l’option de mise à niveau des fonctionnalités qui se chevauchent :

- Envisagez cette option si vous pouvez effectuer une mise à niveau rapide pour votre organisation globale.  Étant donné qu’il existe un risque potentiel de confusion pour les utilisateurs finaux avec l’exécution des deux clients, il est préférable de réduire la période pendant laquelle les utilisateurs doivent exécuter les deux clients. Vous devez vous assurer que vos utilisateurs savent exécuter les deux clients.

- Cette option est le modèle d’out-of-the-box et ne nécessite pas d’action de l’administrateur pour bien démarrer avec Teams, sauf pour affecter la licence Microsoft 365 ou Office 365. Si vos utilisateurs ont déjà Skype Entreprise Online, vous êtes peut-être déjà dans ce modèle.

- Il peut être difficile de sortir du mode des fonctionnalités qui se chevauchent et de passer à TeamsOnly. Étant donné que les utilisateurs mis à niveau communiquent uniquement via Teams, tout autre utilisateur de l’organisation qui communique avec cet utilisateur doit utiliser Teams.  Si vous avez des utilisateurs qui n’ont pas commencé à utiliser Teams, ils seront exposés à des messages manquants. En outre, ils ne verront pas les utilisateurs TeamsOnly en ligne dans Skype Entreprise. Certaines organisations choisissent d’effectuer une mise à niveau à l’échelle du locataire à l’aide de la stratégie globale du locataire pour éviter cela, mais cela nécessite une planification initiale et l’attente jusqu’à ce que tous les utilisateurs soient prêts à être mis à niveau.

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Mise à niveau de certaines fonctionnalités pour une organisation qui n’a pas encore commencé à utiliser Teams

Si votre organisation n’a pas encore d’utilisateurs actifs dans Teams, la première étape consiste à définir la stratégie de locataire par défaut pour TeamsUpgradePolicy sur l’un des modes Skype Entreprise, par exemple, SfbWithTeamsCollab.  Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne remarqueront aucune différence de comportement. Toutefois, la définition de cette stratégie au niveau du locataire permet de commencer à mettre à niveau les utilisateurs vers le mode TeamsOnly et garantit que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs non mis à niveau.  Une fois que vous avez identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.  S’ils sont locaux, utilisez Move-CsUser. S’ils sont en ligne, affectez-leur simplement le mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy. Par défaut, toutes les réunions Skype Entreprise planifiées par ces utilisateurs sont migrées vers Teams.

Voici les commandes clés :

1. Définissez la valeur par défaut à l’échelle du locataire sur le mode SfbWithTeamsCollab comme suit :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Mettez à niveau les utilisateurs pilotes vers TeamsOnly comme suit :

   - Pour un utilisateur en ligne :

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - Pour un utilisateur local :

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**Remarques** :

- Au lieu de définir la stratégie à l’échelle du locataire sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings. Cela amène tous les utilisateurs à planifier toutes les nouvelles réunions dans Teams.
- Par défaut, Skype Entreprise réunions sont migrées vers Teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’affectation du mode SfbWithTeamsCollabAndMeetings.

> [!NOTE]
> En préparation de la prochaine mise hors service de Skype Entreprise Online, Microsoft a simplifié la façon dont les organisations passent à Teams. Il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur `Move-CsUser` pour déplacer les utilisateurs directement de l’environnement local vers TeamsOnly. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs sont passés de Skype Entreprise Server local à Skype Entreprise Online, et leur mode est resté inchangé. Maintenant, lors du déplacement d’un utilisateur d’un site local vers le cloud avec `Move-CsUser`, les utilisateurs sont automatiquement affectés en mode TeamsOnly et leurs réunions locales sont converties de manière automtique en réunions Teams, comme si le `-MoveToTeams switch had been specified`, indépendamment de si le commutateur est réellement spécifié. Ce comportement est disponible sur toutes les versions de Skype For Business Server et Lync Server 2013 (qui n’ont jamais pris en charge `-MoveToTeams`).

Le diagramme ci-dessous montre les phases conceptuelles de mise à niveau des fonctionnalités de sélection pour une organisation sans utilisation préalable de Teams. La hauteur des barres représente le nombre d’utilisateurs. Pendant n’importe quelle phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Skype Entreprise les utilisateurs communiquent avec les utilisateurs TeamsOnly à l’aide d’Interop, et vice versa. Les utilisateurs en mode Îles doivent s’assurer d’exécuter les deux clients.

![Diagramme montrant la mise à niveau de certaines fonctionnalités sans aucune utilisation préalable de Teams.](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Mise à niveau de certaines fonctionnalités pour une organisation qui utilise déjà Teams en mode Îles

Si certains utilisateurs de votre organisation utilisent activement Teams en mode Îles, vous ne souhaitez probablement pas supprimer les fonctionnalités des utilisateurs existants. Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du locataire. La solution consiste à « grand-père » ces utilisateurs actifs Teams existants en mode Îles, avant de définir la stratégie à l’échelle du locataire sur SfbWithTeamsCollab.  Une fois que vous avez effectué cette opération, vous pouvez procéder au déploiement comme ci-dessus. Toutefois, vous avez deux groupes d’utilisateurs qui passent à TeamsOnly : les utilisateurs qui étaient actifs dans Teams seront en mode Îles et les autres utilisateurs seront en mode SfbWithTeamsCollab. Vous pouvez déplacer progressivement ces utilisateurs vers le mode TeamsOnly.

1. Recherchez les utilisateurs actifs dans Teams comme suit :

   1. À partir de la Centre d'administration Microsoft 365, dans le volet de navigation de gauche, accédez à Rapports, puis Utilisation.
   2. Dans la liste déroulante « Sélectionner un rapport », choisissez Microsoft Teams, puis Activité de l’utilisateur. Cela fournit une table exportable des utilisateurs qui ont été actifs dans Teams.
   3. Cliquez sur Exporter, ouvrez Excel et filtrez pour afficher uniquement les utilisateurs actifs dans Teams.

2. Pour chaque utilisateur Teams actif trouvé à l’étape 1, attribuez-lui le mode Îles dans PowerShell distant. Cela vous permet d’accéder à l’étape suivante et de vous assurer que vous ne modifiez pas l’expérience utilisateur.

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. Définissez la stratégie à l’échelle du locataire sur SfbWithTeamsCollab :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. Mettez à niveau les utilisateurs sélectionnés vers le mode TeamsOnly. Vous pouvez choisir de mettre à niveau les utilisateurs en mode Îles ou en mode SfbWithTeamsCollab, bien que vous souhaitiez d’abord hiérarchiser la mise à niveau des utilisateurs en mode Îles afin de réduire le risque de confusion qui peut survenir lorsque les utilisateurs sont en mode Îles.

   Pour les utilisateurs hébergés dans Skype Entreprise Online :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   Pour les utilisateurs hébergés dans Skype Entreprise Server local :

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

Le diagramme ci-dessous montre les phases conceptuelles d’une transition de fonctionnalités sélectionnées dans lesquelles il y a des utilisateurs Islands actifs au début. La hauteur des barres représente le nombre d’utilisateurs. Pendant n’importe quelle phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Skype Entreprise les utilisateurs communiquent avec les utilisateurs TeamsOnly à l’aide de l’interopérabilité, et vice versa.

![Diagramme montrant la mise à niveau de certaines fonctionnalités avec des utilisateurs actifs en mode Îles.](media/teams-upgrade-2.png)

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Utilisation du service de migration de réunion (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
