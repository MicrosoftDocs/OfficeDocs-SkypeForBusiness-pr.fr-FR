---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955901"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Mettre en œuvre la mise à niveau de Skype entreprise vers teams &mdash; pour les administrateurs informatiques

Cet article décrit comment implémenter la mise à niveau. Cet article est le cinquième de ceux qui décrivent les concepts de mise à niveau et l’implémentation pour les administrateurs informatiques.  

- [Vue d’ensemble](upgrade-to-teams-on-prem-overview.md)
- [Méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- [Autres considérations concernant les organisations avec Skype entreprise en local](upgrade-to-teams-on-prem-considerations.md)
- **Mettre en œuvre la mise à niveau** (cet article)
- [Considérations relatives au réseau téléphonique public commuté (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :

- [Coexistence des équipes et de Skype entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence-référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>Options de mise à niveau

Cette section décrit comment implémenter la mise à niveau en utilisant l’une des options de mise à niveau suivantes :

- [Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode îlot)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Mise à niveau des fonctionnalités SELECT pour une organisation qui n’a pas encore commencé à utiliser teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [Mise à niveau des fonctionnalités SELECT pour une organisation qui utilise déjà teams en mode îlot](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Si vous avez besoin d’informations supplémentaires sur les options, assurez-vous d’avoir déjà lu les [méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md).

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode îlot)

Pour l’option de mise à niveau des fonctionnalités qui se chevauchent :

- Cette option est utile si vous pouvez effectuer une mise à niveau rapide de votre organisation globale.  Dans la mesure où il existe des risques potentiels de confusion pour les utilisateurs finaux exécutant les deux clients, il est préférable de réduire le temps de fonctionnement des utilisateurs aux deux clients. Vous devez veiller à ce que les utilisateurs sachent exécuter les deux clients.

- Cette option est le modèle de la boîte et ne nécessite pas d’action de l’administrateur pour commencer à utiliser teams à l’exception de l’attribution de la licence Microsoft 365 ou Office 365. Si vos utilisateurs disposent déjà de Skype entreprise Online, il est possible que vous soyez déjà dans ce modèle.

- Il peut être difficile de sortir du mode de superposition des capacités et de migrer vers TeamsOnly. Étant donné que les utilisateurs mis à niveau communiquent uniquement par le biais d’équipes, tout autre utilisateur de l’organisation qui communique avec cet utilisateur doit utiliser Teams.  Si certains de vos utilisateurs ne sont pas encore en cours d’utilisation, ils seront exposés à des messages manquants. De plus, ils ne verront pas les utilisateurs de TeamsOnly en ligne dans Skype entreprise. Certaines organisations choisissent de procéder à la mise à niveau du client à l’aide de la stratégie globale du client pour éviter cela, mais cela nécessite une planification approfondie ainsi que l’attente de la mise à niveau de tous les utilisateurs.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Mise à niveau des fonctionnalités SELECT pour une organisation qui n’a pas encore commencé à utiliser teams

Si votre organisation n’a pas encore de personnes actives dans Teams, la première étape consiste à définir la stratégie à l’échelle de locataire par défaut de TeamsUpgradePolicy sur l’un des modes Skype entreprise, par exemple, SfbWithTeamsCollab.  Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne noteront aucune différence de comportement. Toutefois, la définition de cette stratégie au niveau du client permet de commencer à mettre à niveau les utilisateurs vers le mode TeamsOnly et de s’assurer que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs non mis à niveau.  Une fois que vous avez identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.  S’il s’agit d’un environnement local, utilisez Move-CsUser. S’il est connecté, affectez-lui simplement le mode TeamsOnly à l’aide de Grant-CsTeamsUpgradePolicy. Par défaut, toutes les réunions Skype entreprise planifiées par ces utilisateurs seront déplacées vers Teams.

Voici les commandes clés :

1. Définissez la valeur par défaut du client sur mode SfbWithTeamsCollab comme suit :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Mettez à niveau les utilisateurs pilotes vers TeamsOnly comme suit :

   - Pour un utilisateur qui est en ligne :

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Pour un utilisateur local :

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Remarques
 
- Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings. Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.
- `Move-CsUser` est une cmdlet dans les outils locaux. Le `MoveToTeams` commutateur nécessite Skype entreprise server 2019 ou Skype entreprise server 2015 avec CU8 ou une version ultérieure. Si vous utilisez une version antérieure, vous pouvez d’abord déplacer l’utilisateur vers Skype entreprise Online, puis accorder le mode TeamsOnly à cet utilisateur.
- Par défaut, les réunions Skype entreprise sont déplacées vers teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’attribution du mode SfbWithTeamsCollabAndMeetings.  

Le diagramme ci-dessous présente les phases conceptuelles de la mise à niveau de fonctionnalités sélectionnées pour une organisation sans utilisation antérieure d’Teams. La hauteur des barres représente le nombre d’utilisateurs. Pendant une phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Les utilisateurs de Skype entreprise communiquent avec des utilisateurs de TeamsOnly à l’aide d’interopérabilité, et inversement. Les utilisateurs en mode îlot doivent veiller à exécuter les deux clients.

![Diagramme illustrant la mise à niveau de fonctionnalités sélectionnées sans utilisation antérieure des équipes](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Mise à niveau des fonctionnalités SELECT pour une organisation qui utilise déjà teams en mode îlot

Si certains utilisateurs de votre organisation utilisent activement teams en mode îlot, il est probable que vous ne vouliez pas supprimer les fonctionnalités des utilisateurs existants. Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client. La solution est de « grand-moi », qui sont des utilisateurs d’équipes actives actuellement en mode îlot, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.  Une fois cette opération effectuée, vous pourrez procéder au déploiement comme décrit ci-dessus, mais vous aurez deux groupes d’utilisateurs qui migrent vers TeamsOnly : les utilisateurs qui ont été actifs dans teams seront en mode d’îlot de travail et les utilisateurs restants seront en mode SfbWithTeamsCollab. Vous pouvez déplacer progressivement ces utilisateurs vers le mode TeamsOnly.

1. Recherchez les utilisateurs actifs dans teams en procédant comme suit :

   1. Dans le centre d’administration Microsoft 365, dans la barre de navigation gauche, accédez à rapports, puis sur utilisation. 
   2. Dans la liste déroulante « Sélectionner un rapport », cliquez sur Microsoft Teams, puis sur activité de l’utilisateur. Cela permet de fournir une table exportable d’utilisateurs qui ont été actifs dans Teams. 
   3. Cliquez sur Exporter, ouvrir Excel et filtre pour afficher uniquement les utilisateurs actifs dans Teams.

2. Pour chaque utilisateur d’équipe actif trouvé à l’étape 1, attribuez-lui le mode îlots dans Remote PowerShell. Cela vous permet d’accéder à l’étape suivante et de ne pas modifier l’interface utilisateur.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly. Vous pouvez choisir de mettre à niveau les utilisateurs en mode îlot ou SfbWithTeamsCollab, même si vous souhaitez que la mise à niveau des utilisateurs en mode îlot soit prioritaire pour réduire le risque de confusion lorsque les utilisateurs sont en mode îlot.   

   Pour les utilisateurs hébergés dans Skype entreprise Online :  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Pour les utilisateurs hébergés dans Skype entreprise Server en local :  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Le diagramme ci-dessous présente les phases conceptuelles d’une transition de sélection de fonctionnalités dans laquelle les utilisateurs d’îlots sont actifs au début. La hauteur des barres représente le nombre d’utilisateurs. Pendant une phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Les utilisateurs de Skype entreprise communiquent avec des utilisateurs de TeamsOnly à l’aide d’interopérabilité, et inversement. 


![Diagramme illustrant l’option Sélectionner les fonctionnalités mise à niveau avec des utilisateurs actifs en mode d’îlot](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

