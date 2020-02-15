---
title: Supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez supprimer n’importe quelle stratégie d’utilisateur ou de site figurant dans le panneau de configuration de Skype entreprise Server sur la page stratégie d’accès externe.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041233"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes

Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit :

  - Supprimez toute stratégie utilisateur ou de site que vous avez créée.

  - Réinitialisez la stratégie globale à ses paramètres par défaut. Si vous appliquez les paramètres par défaut de la stratégie globale, l’accès des utilisateurs externes est refusé. La stratégie globale ne peut pas être supprimée.


Vous pouvez supprimer n’importe quelle stratégie d’utilisateur ou de site figurant dans le panneau de configuration de Skype entreprise Server sur la page **stratégie d’accès externe** . La suppression de la stratégie globale ne la supprime pas, mais la rétablit uniquement aux paramètres par défaut, qui ne prennent pas en charge les options d’accès des utilisateurs externes. Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Pour supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server. 

3.  Cliquez sur **accès des utilisateurs externes**, puis sur **stratégie d’accès externe**.

4.  Sous l’onglet **stratégie d’accès externe** , cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.

5.  À l’invite de confirmation de la suppression, cliquez sur **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell

Les stratégies d’accès externe peuvent être supprimées à l’aide de Windows PowerShell et de l’applet de commande Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Pour supprimer une stratégie d’accès externe spécifique

  - Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue par utilisateur

  - Cette commande permet de supprimer toutes les stratégies d’accès externe configurées au niveau de l’étendue utilisateur :
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Pour supprimer toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs externes est désactivé

  - Cette commande supprime toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs extérieurs a été désactivé :
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .
