---
title: Déplacer des utilisateurs du nuage vers l’organisation locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Découvrez comment déplacer des utilisateurs de Skype entreprise Online vers un site local.
ms.openlocfilehash: 16e4419bfd8ea073c04d0b3c4a402455097e4ad5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160501"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Déplacer des utilisateurs du nuage vers l’organisation locale 

Si nécessaire, vous pouvez déplacer un utilisateur qui a été précédemment migré de local vers le Cloud (en utilisant Skype entreprise Online ou teams uniquement) sur site local. Pour déplacer les utilisateurs de Skype entreprise Online ou TeamsOnly vers un déploiement local de Skype entreprise Server, utilisez l’applet de commande Move-CsUser ou le panneau de configuration Skype entreprise Server, qui sont tous deux des outils locaux. Lorsque vous redéplacez un utilisateur vers un déploiement local, vous devez choisir le pool vers lequel déplacer l’utilisateur.

> [!Important]
> Si l’utilisateur était précédemment en mode TeamsOnly et que vous utilisez une version antérieure à Skype entreprise Server 2015 avec CU8, vous devez également supprimer l’attribution du mode TeamsOnly de TeamsUpgradePolicy pour cet utilisateur. Les utilisateurs locaux ne doivent pas avoir le mode = TeamsOnly.  Les versions ultérieures de Skype entreprise Server suppriment automatiquement cette attribution. Pour plus d’informations, consultez la rubrique [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Conditions préalables

- La configuration d’Azure AD Connect doit être correctement configurée pour l’organisation et la synchronisation de tous les attributs pertinents pour l’utilisateur, comme décrit dans [configure Azure ad Connect](configure-azure-ad-connect.md).
- L’utilisateur déplacé de la mise en ligne vers l’organisation locale doit déjà exister dans l’environnement Active Directory local.
- Skype entreprise hybride doit être configuré, comme décrit dans [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Déplacement des utilisateurs vers l’organisation locale

Une fois que vous avez déplacé un utilisateur du nuage vers l’organisation locale:

- L’utilisateur interagit avec votre déploiement Skype entreprise Server pour ses fonctionnalités. 
- Tous les contacts qui existaient dans Skype entreprise Online ou teams sont migrés vers Skype entreprise Server. Les deux ensembles de contacts sont fusionnés, puis migrés vers l’organisation locale.  En outre, les contacts qui sont pré-existants dans teams restent dans Teams.
- Si l’utilisateur utilise également Teams, il ne pourra pas interagir avec les utilisateurs de Skype entreprise et ne sera pas en mesure de communiquer avec des utilisateurs dans des organisations fédérées.
- Les réunions dans Skype entreprise Online ne sont *pas* automatiquement migrées vers l’environnement local. Les utilisateurs doivent replanifier leurs réunions ou, si vous le souhaitez, utiliser l' [outil de migration de réunion](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Déplacer des utilisateurs à l’aide de Move-CsUser

Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype entreprise Management Shell locale. Vous devez disposer de privilèges suffisants à la fois dans l’environnement local et dans le client Office 365, comme décrit [](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)dans la rubrique required Credentials Requirements. Vous pouvez utiliser un compte unique qui dispose de privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre locale de Skype entreprise Server Management Shell avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier des informations d’identification pour un Office 365 compte avec le rôle d’administrateur Office 365 nécessaire.

Pour déplacer un utilisateur vers l’organisation locale à l’aide de Move-CsUser:

- Spécifier l’utilisateur à déplacer à l’aide du paramètre Identity.
- Spécifiez le paramètre-Target avec le nom de domaine complet du pool local souhaité qui hébergera l’utilisateur.
- Si vous ne disposez pas d’un compte avec des autorisations suffisantes dans local et Office 365, utilisez le paramètre-Credential pour fournir un compte avec des autorisations suffisantes dans Office 365.
- Si le compte avec des autorisations dans Office 365 ne se termine pas par «on.microsoft.com», vous devez spécifier le paramètre-HostedMigrationOverrideUrl, avec la valeur correcte [](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)comme décrit dans required Credentials Requirements.

La séquence d’applets de commande suivante peut être utilisée pour déplacer un utilisateur vers Skype entreprise Server et suppose que les informations d’identification Office 365 sont un compte distinct et fourni comme entrée pour l’invite Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Déplacer des utilisateurs à l’aide du panneau de configuration de Skype entreprise Server

1. Ouvrez l’application du panneau de configuration de Skype entreprise Server.
2. Dans le volet de navigation de gauche, choisissez **utilisateurs**.
3. Utilisez **Rechercher** pour localiser le ou les utilisateurs que vous souhaitez déplacer vers l’emplacement local.
4. Sélectionnez le ou les utilisateurs, puis, dans la liste déroulante **action** située au-dessus de la liste, sélectionnez **déplacer les utilisateurs sélectionnés vers**l’organisation locale.
5. Dans l’Assistant, sélectionnez le pool d’utilisateurs qui hébergera l’utilisateur et cliquez sur **suivant**.
6. Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et qui dispose des autorisations suffisantes.
7. Cliquez sur **suivant**, puis une **nouvelle** fois pour déplacer l’utilisateur.
8. Notez que les messages d’État concernant la réussite ou l’échec sont fournis en haut de l’application principale du panneau de configuration, et non dans l’Assistant.

### <a name="removing-teamsonly-mode"></a>Suppression du mode TeamsOnly

Si vous utilisez une version antérieure à Skype entreprise 2015 avec CU8 et que l’utilisateur est déplacé de nouveau en mode TeamsOnly, vous devez supprimer l’instance UpgradeToTeams avant de `TeamsUpgradePolicy` déplacer l’utilisateur en local. Vous pouvez soit explicitement accorder une stratégie avec un mode différent, soit simplement supprimer l’attribution de stratégie existante pour qu’il utilise la stratégie globale (à condition que la stratégie globale de votre client ne soit pas UpgradeToTeams).

Pour supprimer l’attribution de TeamsUpgradePolicy de l’utilisateur, exécutez l’applet de commande suivante à partir d’une fenêtre PowerShell de Skype entreprise Online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

Par ailleurs, pour affecter une autre instance de TeamsUpgradePolicy sans mode = TeamsOnly, vous pouvez spécifier le nom de l’instance souhaitée en tant que valeur du paramètre PolicyName dans l’applet de commande. Pour afficher la liste des instances disponibles de TeamsUpgradePolicy, exécutez Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Voir aussi

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
