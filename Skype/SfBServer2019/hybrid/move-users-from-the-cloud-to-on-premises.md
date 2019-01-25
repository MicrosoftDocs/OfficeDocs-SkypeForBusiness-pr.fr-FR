---
title: Déplacer les utilisateurs du nuage vers sur site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Découvrez comment déplacer des utilisateurs Skype pour Business en ligne et sur site.
ms.openlocfilehash: 7032e7f2968b7861a7fac199fd8ba949980fe770
ms.sourcegitcommit: f091c351bec56219a8c91b8c12b9c1f5c5983c95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2019
ms.locfileid: "29530942"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Déplacer les utilisateurs du nuage vers sur site 

Si nécessaire, vous pouvez déplacer un utilisateur qui a déjà été migré à partir de sur site vers le nuage (que vous utilisiez Skype pour Business Online ou équipes uniquement) précédent vers localement. Pour déplacer les utilisateurs soit Skype pour le mode en ligne Business ou TeamsOnly retour vers un déploiement local de Skype pour Business Server, utilisez l’applet de commande Move-CsUser, soit la Skype pour Business Server Control Panel, qui sont tous deux outils locale. Lorsque vous déplacez un utilisateur de retour à un déploiement sur site, vous devez décider quel pool vers lequel déplacer l’utilisateur.

> [!Important]
> Si l’utilisateur a été précédemment en mode TeamsOnly, et que vous utilisez une version antérieure à Skype pour Business Server 2015 avec CU8, vous devez également supprimer l’affectation de mode TeamsOnly de TeamsUpgradePolicy pour cet utilisateur. Les utilisateurs ne doivent pas avoir le mode local = TeamsOnly.  Les versions ultérieures de Skype pour Business Server supprimer automatiquement cette affectation. Pour plus d’informations, voir [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Conditions requises

- L’organisation doit avoir Azure AD se connecter correctement configurée et à la synchronisation de tous les attributs pertinents pour l’utilisateur, comme décrit dans [Azure configurer AD connexion](configure-azure-ad-connect.md).
- L’utilisateur en cours de déplacement à nouveau en ligne sur site doit déjà exister dans Active Directory local.
- Skype pour un environnement hybride Business doit être configuré, comme décrit dans [Configurer le Skype pour un environnement hybride Business](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Déplacement d’utilisateurs retour à sur site

Une fois que vous déplacez un utilisateur du nuage vers locale :

- L’utilisateur interagit avec votre Skype pour le déploiement de serveur d’entreprise pour ses fonctionnalités. 
- Les contacts qui existaient dans soit Skype pour Business en ligne ou les équipes sont migrés vers Skype pour Business Server. Ces deux jeux de contacts est fusionnées et migrées vers localement.  En outre, les contacts existants dans les équipes restent dans les équipes.
- Si l’utilisateur utilise également des équipes, n’ont pas la possibilité d’interagir avec Skype pour les utilisateurs professionnels, ni qu’ils seront en mesure de communiquer avec les utilisateurs des organisations fédérées.
- Réunions dans Skype pour Business Online ne sont *pas* migrés automatiquement à localement. Les utilisateurs doivent soit replanifier leurs réunions ou, si vous le souhaitez, utiliser l' [Outil de Migration de réunion](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Déplacer les utilisateurs avec Move-CsUser

Move-CsUser est disponible à partir d’un Skype locale de fenêtre Business Management Shell PowerShell. Vous devez disposer de privilèges suffisants dans l’environnement local ainsi que le client Office 365, comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Vous pouvez utiliser un seul compte disposant de privilèges dans les deux environnements, ou vous pouvez démarrer une Skype dans les locaux de fenêtre Business Server Management Shell avec des informations d’identification dans les locaux et utiliser le `-Credential` paramètre pour spécifier les informations d’identification pour un Office 365 compte doté du rôle d’administration Office 365 nécessaire.

Pour déplacer un utilisateur sur site à l’aide de Move-CsUser :

- Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez-paramètre cible avec le nom de domaine complet du pool qui hébergera l’utilisateur local souhaité.
- Si vous ne disposez pas d’un compte disposant des autorisations suffisantes dans les locaux et Office 365, utilisez le paramètre - credential pour fournir un compte disposant des autorisations suffisantes dans Office 365.
- Si le compte possédant des autorisations dans Office 365 ne se termine pas par « on.microsoft.com », vous devez spécifier le paramètre - HostedMigrationOverrideUrl, avec la valeur correcte, comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La séquence d’applet de commande suivante peut être utilisée pour déplacer un utilisateur vers Skype pour Business Server et suppose que les informations d’identification Office 365 est un compte distinct et fourni comme entrée pour l’invite de Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Déplacer les utilisateurs avec le Skype pour Business Server Control Panel

1. Ouvrez le Skype pour le contrôle serveur Business application du Panneau de configuration.
2. Dans la navigation de gauche, choisissez **utilisateurs**.
3. Utiliser la **recherche** pour localiser les utilisateurs que vous souhaitez atteindre dans les locaux.
4. Sélectionnez l’ou les utilisateurs, puis, dans la liste déroulante **Action** au-dessus de la liste, cliquez sur **déplacer les utilisateurs sélectionnés vers le site**.
5. Dans l’Assistant, sélectionnez le pool de l’utilisateur qui hébergera l’utilisateur et cliquez sur **suivant**.
6. Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et dispose des autorisations suffisantes.
7. Cliquez sur **suivant**, puis **suivant** une fois plus de déplacer l’utilisateur.
8. Notez que les messages d’état en ce qui concerne la réussite ou l’échec sont fournis dans la partie supérieure de l’application le panneau de configuration principale, pas dans l’Assistant.

### <a name="removing-teamsonly-mode"></a>Suppression du mode TeamsOnly

Si vous utilisez une version antérieure à Skype pour Business 2015 avec CU8 et que l’utilisateur est en cours déplacé vers localement en mode TeamsOnly, vous devez supprimer l’instance UpgradeToTeams de `TeamsUpgradePolicy` avant de déplacer l’utilisateur sur site. Vous pouvez explicitement accorder une stratégie avec un autre mode ou simplement supprimer l’affectation de stratégie existant pour cet utilisateur à utiliser la stratégie globale (à condition que stratégie globale de votre client n’est pas UpgradeToTeams).

Pour supprimer l’affectation de l’utilisateur de TeamsUpgradePolicy, exécutez l’applet de commande suivante à partir d’un Skype pour fenêtre Business Online PowerShell :

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Autrement, à une autre instance de TeamsUpgradePolicy qui n’a pas le mode = TeamsOnly, vous pouvez spécifier le nom de l’instance souhaitée en tant que la valeur du paramètre PolicyName dans l’applet de commande. Pour afficher une liste d’instances disponibles de TeamsUpgradePolicy, exécutez Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Voir aussi

Move-CsUser
