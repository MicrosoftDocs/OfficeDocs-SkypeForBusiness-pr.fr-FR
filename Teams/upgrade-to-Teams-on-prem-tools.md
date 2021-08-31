---
title: Outils de mise à niveau Teams d’un déploiement Skype Entreprise local
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Outils de mise à niveau Skype Entreprise vers Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d98257e9a29564d22b57c5cc537d703bbb1fe842
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729303"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Outils pour la mise à niveau vers Teams &mdash; administrateurs informatiques

Cet article décrit les outils permettant de mettre à Teams niveau vers Skype Entreprise. 

Avant de commencer votre mise à niveau, Microsoft recommande les articles suivants qui décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Outils de gestion de la mise à niveau

Quelle que soit la méthode de mise à niveau que vous choisissez, pour les utilisateurs qui ont déjà Skype Entreprise Online, vous gérez la transition vers TeamsOnly à l’aide de [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)qui contrôle le mode de coexistence d’un utilisateur. Pour les utilisateurs qui ont un compte local dans Skype Entreprise Server, vous pouvez également les déplacer `Move-CsUser` [vers le cloud.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Pour plus d’informations sur chacun des modes, voir [Modes de coexistence.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants. Pour [plus d’Skype Entreprise, voir Déplacer du connecteur en ligne vers Teams module PowerShell.](teams-powershell-move-from-sfbo.md)

Que vous effectuez une transition de fonctionnalités sélectionnées à l’aide des modes Skype Entreprise ou que vous passiez simplement à niveau vers le mode TeamsOnly à partir de la configuration îles par défaut, TeamsUpgradePolicy est l’outil principal. Comme toute autre stratégie Teams, vous pouvez affecter TeamsUpgradePolicy directement à un utilisateur. Vous pouvez également définir la stratégie comme stratégie par défaut à l’échelle du client. Toute affectation à un utilisateur est prioritaire sur le paramètre par défaut du client.  Vous pouvez gérer la stratégie dans la console d’administration Teams et dans PowerShell.

Vous pouvez affecter n’importe quel mode de TeamsUpgradePolicy, à l’exception du mode TeamsOnly, aux utilisateurs Skype Entreprise sur site. À l’inverse, seul le mode TeamsOnly peut être attribué aux utilisateurs homed in the cloud. Le **mode TeamsOnly** ne peut être affecté qu’à un utilisateur qui est déjà dopé dans le cloud, car interop et la fédération avec des utilisateurs Skype Entreprise ainsi que des fonctionnalités de Microsoft 365 Système téléphonique ne sont possibles que si l’utilisateur est doté sur Skype Entreprise Online.  En outre, vous ne pouvez pas attribuer le **mode TeamsOnly** comme mode par défaut à l’échelle du client si vous avez un déploiement Skype Entreprise local (détecté par la présence d’un enregistrement DNS lyncdiscover qui pointe vers un emplacement autre que Office 365). Pour plus d’informations, voir Désactiver votre configuration hybride pour achever la [migration vers Teams uniquement.](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)

Les utilisateurs Skype Entreprise comptes locaux doivent être [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) déplacés en ligne vers le mode Teams Uniquement à l’aide de Move-CsUser dans le jeu d’outils Skype Entreprise local. 

Contrairement à d’autres stratégies, il n’est pas possible de créer de nouvelles instances de TeamsUpgradePolicy Microsoft 365 ou Office 365. Toutes les instances existantes sont intégrées au service.  (Notez que le mode est une propriété dans TeamsUpgradePolicy, plutôt que le nom d’une instance de stratégie.) Dans certains cas, mais pas tous, le nom de l’instance de stratégie est identique à celui du mode. En particulier, pour affecter le mode TeamsOnly à un utilisateur, vous accordez l’instance « UpgradeToTeams » de TeamsUpgradePolicy à cet utilisateur. Pour voir la liste de toutes les instances, vous pouvez exécuter la commande suivante :

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Pour mettre à niveau un utilisateur en ligne vers le mode TeamsOnly, affectez l’instance « UpgradeToTeams » : 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Pour mettre à niveau un utilisateur Skype Entreprise site vers le mode TeamsOnly, utilisez Move-CsUser dans le jeu d’outils local :

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

Pour modifier le mode pour tous les utilisateurs du client, à l’exception de ceux qui ont une autorisation explicite par utilisateur (qui prend la priorité), exécutez la commande suivante :

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si vous avez des utilisateurs Skype Entreprise comptes locaux, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client. Vous devez déplacer ces utilisateurs individuellement vers Teams mode Uniquement à l’aide de Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Utilisation des notifications dans Skype Entreprise clients

Les administrateurs ont la possibilité de fournir des notifications aux utilisateurs finaux dans le client Skype Entreprise pour informer les utilisateurs qu’ils seront bientôt mis à niveau vers Teams, comme illustré dans le diagramme suivant. Par exemple, une semaine avant que l’administrateur envisage de mettre à niveau un groupe d’utilisateurs en mode TeamsOnly, l’administrateur peut activer ces notifications pour ce groupe d’utilisateurs. Ces notifications sont activées à l’aide d’une instance de TeamsUpgradePolicy avec NotifySfbUsers=true.  Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.  Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers. 

![Diagramme montrant les notifications.](media/teams-upgrade-sfb-with-notifications.png)

Si vos utilisateurs sont homed in Skype Entreprise Online, affectez simplement l’instance de stratégie ayant le même mode que l’utilisateur, mais avec NotifySfbUsers=true. 

Si vos utilisateurs sont accueil dans Skype Entreprise Server local, vous devez utiliser le groupe d’outils local et vous devez utiliser Skype Entreprise Server 2019 ou CU8 pour Skype Entreprise Server 2015. Pour les utilisateurs homed in Skype Entreprise Server local, la propriété de mode de l’instance en ligne de TeamsUpgradePolicy est honorée, mais la propriété NotifySfbUsers ne l’est pas. Si vous souhaitez recevoir des notifications, vous devez créer une instance sur site de TeamsUpgradePolicy pour contrôler le comportement du client. 

Dans la fenêtre PowerShell en local, créez une instance de TeamsUpgradePolicy avec NotifySfbUsers=true :

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Ensuite, à l’aide de la même fenêtre PowerShell en local, affectez cette nouvelle stratégie aux utilisateurs souhaités :

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migration de réunions

Lorsqu’un utilisateur est migré vers le mode TeamsOnly, par défaut ses Skype Entreprise réunions existantes qu’il a organisées sont converties en Teams. Vous pouvez éventuellement désactiver le comportement par défaut lors de l’attribution du mode TeamsOnly à un utilisateur. Lors du déplacement d’utilisateurs à partir du site, les réunions doivent être migrées vers le cloud pour fonctionner avec le compte d’utilisateur en ligne, mais si vous ne spécifiez pas -MoveToTeams, les réunions seront migrées en tant que réunions Skype Entreprise, au lieu d’être converties en Teams. 

Lors de l’attribution du mode TeamsOnly au niveau du client, la migration de réunions n’est déclenchée pour aucun utilisateur. Si vous souhaitez attribuer le mode TeamsOnly au niveau du client et migrer des réunions, vous pouvez utiliser PowerShell pour obtenir la liste des utilisateurs dans le client (par exemple, en utilisant Get-CsOnlineUser avec les filtres nécessaires), puis passer en boucle chacun de ces utilisateurs pour déclencher la migration de réunion à l’aide de Start-CsExMeetingMigration. Pour plus d’informations, [consultez Utiliser meeting Migration Service (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Liens connexes

[Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre les Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
