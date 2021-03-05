---
title: Outils pour la mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Outils de mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c272cdd6eac98b8847b6f915d59b62444d16c97
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460434"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Outils de mise à niveau vers Teams &mdash; pour les administrateurs informatiques

Cet article décrit les outils permettant de mettre à niveau vers Teams à partir de Skype Entreprise. 

Avant de commencer votre mise à niveau, Microsoft recommande les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et de Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Outils de gestion de la mise à niveau

Quelle que soit la méthode de mise à niveau que vous choisissez, pour les utilisateurs qui ont déjà Skype Entreprise Online, vous gérez la transition vers TeamsOnly à l’aide de [TeamsUpgradePolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)qui contrôle le mode de coexistence d’un utilisateur. Pour les utilisateurs utilisant un compte local dans Skype Entreprise Server, vous pouvez également les `Move-CsUser` [déplacer vers le cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Pour plus d’informations sur chacun des modes, voir [Modes de coexistence.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants. Pour [plus d’informations,](teams-powershell-move-from-sfbo.md) voir Déplacer de Skype Entreprise Online Connector vers le module Teams PowerShell.

Que vous effectuez une transition de fonctionnalités sélectionnées à l’aide des modes Skype Entreprise ou que vous passiez simplement à la mise à niveau vers le mode TeamsOnly à partir de la configuration îles par défaut, TeamsUpgradePolicy est l’outil principal pour les utilisateurs qui ont déjà Skype Entreprise Online. Comme toute autre stratégie dans Teams, vous pouvez affecter TeamsUpgradePolicy directement à un utilisateur. Vous pouvez également définir la stratégie comme stratégie par défaut à l’échelle du client. Toute affectation à un utilisateur est prioritaire sur le paramètre par défaut du client.  Vous pouvez gérer la stratégie dans la Console d’administration Teams et dans PowerShell.

Vous pouvez également affecter n’importe quel mode de TeamsUpgradePolicy, à l’exception du mode TeamsOnly, aux utilisateurs homed in Skype Entreprise sur site. **Le mode TeamsOnly ne peut être affecté** qu’à un utilisateur déjà domicile dans Skype Entreprise Online. Cela est dû au fait que l’interopation avec les utilisateurs et la fédération Skype Entreprise ainsi que les fonctionnalités du système téléphonique Microsoft 365 ne sont possibles que si l’utilisateur est do domicile dans Skype Entreprise Online. En outre, vous ne pouvez pas attribuer le **mode TeamsOnly** comme mode par défaut à l’échelle du client si vous avez un déploiement local de Skype Entreprise (détecté par la présence d’un enregistrement DNS lyncdiscover qui pointe vers un emplacement autre qu’Office 365).

Les utilisateurs départagent des comptes Skype Entreprise sur site [doivent](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) être déplacés en ligne (vers Skype Entreprise Online ou directement dans Teams) à l’aide de Move-CsUser dans le jeu d’outils Skype Entreprise local. Ces utilisateurs peuvent être déplacés vers TeamsOnly en 1 ou 2 étapes :

-   1 étape : spécifier le commutateur -MoveToTeams dans Move-CsUser. Cela nécessite Skype Entreprise Server 2019 ou Skype Entreprise Server 2015 avec CU8 ou une suite ultérieure.

-   2 étapes : Après avoir exécutez Move-CsUser, accordez le mode TeamsOnly à l’utilisateur utilisant TeamsUpgradePolicy.

Contrairement à d’autres stratégies, il n’est pas possible de créer de nouvelles instances de TeamsUpgradePolicy dans Microsoft 365 ou Office 365. Toutes les instances existantes sont intégrées au service.  (Notez que le mode est une propriété dans TeamsUpgradePolicy, plutôt que le nom d’une instance de stratégie.) Dans certains cas, mais pas tous, le nom de l’instance de stratégie est identique à celui du mode. En particulier, pour affecter le mode TeamsOnly à un utilisateur, vous accordez l’instance « UpgradeToTeams » de TeamsUpgradePolicy à cet utilisateur. Pour voir la liste de toutes les instances, vous pouvez exécuter la commande suivante :

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Pour mettre à niveau un utilisateur en ligne vers le mode TeamsOnly, affectez l’instance « UpgradeToTeams » : 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Pour mettre à niveau un utilisateur Skype Entreprise sur site vers le mode TeamsOnly, utilisez Move-CsUser dans le jeu d’outils local :

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Pour modifier le mode pour tous les utilisateurs du client, à l’exception de ceux qui ont une autorisation explicite par utilisateur (qui prend la priorité), exécutez la commande suivante :

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si vous avez des utilisateurs avec des comptes Skype Entreprise en local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client. Vous devez déplacer ces utilisateurs individuellement vers le cloud à l’aide de Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Utilisation des notifications dans les clients Skype Entreprise

Les administrateurs ont la possibilité de fournir des notifications aux utilisateurs finaux dans le client Skype Entreprise pour informer les utilisateurs qu’ils seront bientôt mis à niveau vers Teams, comme illustré dans le diagramme suivant. Par exemple, une semaine avant que l’administrateur envisage de mettre à niveau un groupe d’utilisateurs en mode TeamsOnly, l’administrateur peut activer ces notifications pour ce groupe d’utilisateurs. Ces notifications sont activées à l’aide d’une instance de TeamsUpgradePolicy avec NotifySfbUsers=true.  Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.  Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers. 

![Diagramme montrant les notifications](media/teams-upgrade-sfb-with-notifications.png)

Si vos utilisateurs sont homed in Skype Entreprise Online, affectez simplement l’instance de stratégie ayant le même mode que l’utilisateur, mais avec NotifySfbUsers=true. 

Si vos utilisateurs sont homed dans Skype Entreprise Server sur site, vous devez utiliser le jeu d’outils local et vous avez besoin de Skype Entreprise Server 2019 ou CU8 pour Skype Entreprise Server 2015. Pour les utilisateurs homed in Skype For Business Server local, la propriété de mode de l’instance en ligne de TeamsUpgradePolicy est honorée, mais la propriété NotifySfbUsers ne l’est pas. Si vous souhaitez recevoir des notifications, vous devez créer une instance sur site de TeamsUpgradePolicy pour contrôler le comportement du client. 

Dans la fenêtre PowerShell en local, créez une instance de TeamsUpgradePolicy avec NotifySfbUsers=true :

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Ensuite, à l’aide de la même fenêtre PowerShell en local, affectez cette nouvelle stratégie aux utilisateurs souhaités :

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migration de réunions

Lorsqu’un utilisateur est migré vers le mode TeamsOnly, par défaut ses réunions Skype Entreprise existantes qu’il a organisées sont converties en équipes. Vous pouvez éventuellement désactiver le comportement par défaut lors de l’attribution du mode TeamsOnly à un utilisateur. Lors du déplacement d’utilisateurs à partir du site, les réunions doivent être migrées vers le cloud pour fonctionner avec le compte d’utilisateur en ligne, mais si vous ne spécifiez pas -MoveToTeams, les réunions seront migrées en tant que réunions Skype Entreprise, plutôt que converties en équipes. 

Lors de l’attribution du mode TeamsOnly au niveau du client, la migration de réunions n’est déclenchée pour aucun utilisateur. Si vous souhaitez attribuer le mode TeamsOnly au niveau du client et migrer des réunions, vous pouvez utiliser PowerShell pour obtenir la liste des utilisateurs dans le client (par exemple, en utilisant Get-CsOnlineUser avec les filtres nécessaires), puis passer en boucle chacun de ces utilisateurs pour déclencher la migration de réunion à l’aide de Start-CsExMeetingMigration. Pour plus d’informations, [consultez Utiliser meeting Migration Service (MMS).](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Liens connexes

[Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

