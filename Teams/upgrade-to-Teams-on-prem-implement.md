---
title: Stratégies de mise à niveau pour les administrateurs informatiques
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Cet article est pour les administrateurs informatiques et décrit les stratégies de mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401339"
---
# <a name="upgrade-strategies-for-it-administrators"></a>Stratégies de mise à niveau pour les administrateurs informatiques

![Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")

Cet article est pour les administrateurs informatiques qui souhaitent implémenter leur mise à niveau vers Teams à partir de Skype Entreprise.

Avant d’implémenter votre mise à niveau, nous vous recommandons les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Comprendre la coexistence et l’interopérabilité de Microsoft Teams et De Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Options de mise à niveau

Cette section explique comment implémenter votre mise à niveau à l’aide de l’une des options de mise à niveau suivantes :

- [Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Mise à niveau des fonctionnalités de sélection pour une organisation qui n’a pas encore commencé à utiliser Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si vous avez besoin d’informations supplémentaires sur les options, assurez-vous que vous avez déjà lu Le chemin de mise à niveau de Skype Entreprise [vers Teams.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Mise à niveau des fonctionnalités superposées (à l’aide du mode Îles)

Pour l’option de mise à niveau des fonctionnalités superposées :

- Envisagez cette option si vous pouvez mettre à niveau rapidement l’ensemble de votre organisation.  Étant donné qu’il existe un risque potentiel de confusion pour les utilisateurs finaux lors de l’exécution des deux clients, il est préférable de réduire la période pendant laquelle les utilisateurs doivent exécuter les deux clients. Vous devez vous assurer que vos utilisateurs savent exécuter les deux clients.

- Cette option est le modèle pré-standard et ne nécessite aucune action de l’administrateur pour prendre en charge Teams, sauf pour affecter la licence Microsoft 365 ou Office 365. Si vos utilisateurs ont déjà Skype Entreprise Online, il est possible que vous soyez déjà dans ce modèle.

- Il peut être difficile de sortir du mode de fonctionnalités superposées et de passer à TeamsOnly. Étant donné que les utilisateurs mis à niveau communiquent uniquement via Teams, tous les autres utilisateurs de l’organisation qui communiquent avec cet utilisateur doivent utiliser Teams.  Si vous avez des utilisateurs qui n’ont pas commencé à utiliser Teams, ils sont exposés à des messages manquants. De plus, ils ne voient pas les utilisateurs de TeamsOnly en ligne dans Skype Entreprise. Certaines organisations choisissent d’opter pour une mise à niveau à l’échelle du client à l’aide de la stratégie globale du client afin d’éviter ce problème, ce qui nécessite toutefois une planification préalable, ainsi que l’attente jusqu’à ce que tous les utilisateurs soient prêts à être mis à niveau.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Mise à niveau des fonctionnalités de sélection pour une organisation qui n’a pas encore commencé à utiliser Teams

Si votre organisation n’a pas encore d’utilisateurs actifs dans Teams, la première étape consiste à définir la stratégie par défaut à l’échelle du client pour TeamsUpgradePolicy sur l’un des modes Skype Entreprise, par exemple, SfbWithTeamsCollab.  Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne remarqueront aucune différence de comportement. Toutefois, la définition de cette stratégie au niveau du client permet de commencer la mise à niveau des utilisateurs vers le mode TeamsOnly et garantit que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs qui ne sont pas mis à niveau.  Après avoir identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.  S’ils sont locaux, utilisez Move-CsUser. S’ils sont en ligne, affectez-leur simplement le mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy. Par défaut, les réunions Skype Entreprise programmées par ces utilisateurs sont migrées vers Teams.

Voici les principales commandes :

1. Définissez le mode SfbWithTeamsCollab à l’échelle du client comme suit :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Mettre à niveau les utilisateurs pilotes vers TeamsOnly comme suit :

   - Pour un utilisateur en ligne :

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Pour un utilisateur sur site :

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Remarques
 
- Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings. Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.
- `Move-CsUser` est une cmdlet dans les outils locaux. Le `MoveToTeams` basculement nécessite Skype Entreprise Server 2019 ou Skype Entreprise Server 2015 avec CU8 ou une date ultérieure. Si vous utilisez une version antérieure, vous pouvez d’abord déplacer l’utilisateur vers Skype Entreprise Online, puis lui octroyer le mode TeamsOnly.
- Par défaut, les réunions Skype Entreprise sont migrées vers Teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’affectation du mode SfbWithTeamsCollabAndMeetings.  

Le diagramme ci-dessous présente les phases conceptuelles de la mise à niveau des fonctionnalités de sélection pour une organisation sans utilisation préalable de Teams. La hauteur des barres représente le nombre d’utilisateurs. Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Les utilisateurs de Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’Interop, et inversement. Les utilisateurs en mode Îles doivent s’assurer d’exécuter les deux clients.

![Diagramme montrant la mise à niveau des fonctionnalités de sélection sans utilisation préalable de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Mise à niveau des fonctionnalités sélectionnées pour une organisation qui utilise déjà Teams en mode Îles

Si certains utilisateurs de votre organisation utilisent activement Teams en mode Îles, vous ne souhaitez probablement pas supprimer la fonctionnalité des utilisateurs existants. Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client. La solution consiste à « transformer » ces utilisateurs existants de Teams en mode Îles, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.  Une fois que vous aurez effectué cela, vous pourrez procéder au déploiement comme ci-dessus. Toutefois, vous aurez deux groupes d’utilisateurs qui vont passer à TeamsOnly : les utilisateurs qui étaient actifs dans Teams seront en mode Îles et les autres utilisateurs seront en mode SfbWithTeamsCollab. Vous pouvez progressivement déplacer ces utilisateurs vers le mode TeamsOnly.

1. Recherchez les utilisateurs actifs dans Teams comme suit :

   1. Dans le centre d’administration Microsoft 365, dans le panneau de navigation gauche, allez dans Rapports, puis Utilisation. 
   2. Dans ladown « Sélectionner un rapport », sélectionnez Microsoft Teams, puis Activité de l’utilisateur. Vous aurez ainsi une table exportable d’utilisateurs ayant été actifs dans Teams. 
   3. Cliquez sur Exporter, ouvrez Excel et filtrez pour afficher uniquement les utilisateurs actifs dans Teams.

2. Pour chaque utilisateur actif de Teams trouvé à l’étape 1, affectez-lui le mode Îles dans une powerShell distante. Cela vous permet de passer à l’étape suivante et de ne pas modifier l’expérience utilisateur.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly. Vous pouvez choisir de mettre à niveau soit les utilisateurs en mode Islands, soit en mode SfbWithTeamsCollab, même si vous pouvez d’abord hiérarchiser la mise à niveau des utilisateurs en mode Islands afin de minimiser le risque de confusion qui peut survenir lorsque les utilisateurs sont en mode Islands.   

   Pour les utilisateurs homed dans Skype Entreprise Online :  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Pour les utilisateurs homed in Skype Entreprise Server sur site :  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Le diagramme ci-dessous montre les phases conceptuelles d’une transition de fonctionnalités sélectionnées dans laquelle les utilisateurs d’îles actives sont au début. La hauteur des barres représente le nombre d’utilisateurs. Pendant toute phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Les utilisateurs de Skype Entreprise communiquent avec les utilisateurs de TeamsOnly à l’aide d’interop et vice versa. 


![Diagramme montrant la mise à niveau des fonctionnalités sélectionnées avec des utilisateurs actifs en mode Îles](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

