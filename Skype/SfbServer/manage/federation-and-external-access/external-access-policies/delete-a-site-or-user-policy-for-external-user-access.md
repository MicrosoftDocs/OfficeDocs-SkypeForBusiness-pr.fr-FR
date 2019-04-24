---
title: Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez supprimer toute stratégie de site ou d’utilisateur qui est répertorié dans la Skype pour Business Server Control Panel dans la page Stratégie d’accès externe.
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197743"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes

Si vous avez créé ou configuré des stratégies d’accès utilisateur externe que vous ne souhaitez plus utiliser, procédez comme suit :

  - Supprimer une stratégie de site ou d’utilisateur que vous avez créé.

  - Réinitialiser la stratégie globale pour les paramètres par défaut. Les paramètres de stratégie globale par défaut refuser tout accès des utilisateurs externes. Impossible de supprimer la stratégie globale.


Vous pouvez supprimer toute stratégie de site ou d’utilisateur qui est répertorié dans la Skype pour Business Server Control Panel dans la page **Stratégie d’accès externe** . Suppression de la stratégie globale n’est pas réellement supprimé, mais uniquement rétablit les paramètres par défaut, qui ne comportent pas de prise en charge pour les options d’accès utilisateur externe. Pour plus d’informations sur la réinitialisation de la stratégie globale, consultez la rubrique [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Cliquez sur **Accès des utilisateurs externes**, cliquez sur **Stratégie d’accès externe**.

4.  Sous l’onglet **Stratégie d’accès externe** , cliquez sur la stratégie de site ou utilisateur que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.

5.  Lorsque vous y êtes invité à confirmer la suppression, cliquez sur **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression des stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell

Stratégies d’accès externe peuvent être supprimés à l’aide de Windows PowerShell et l’applet de commande Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Pour supprimer une stratégie d’accès externe spécifique

  - Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Pour supprimer toutes les stratégies appliquées à l’étendue utilisateur accéder à externe

  - Cette commande supprime toutes les stratégies d’accès externe configurées dans l’étendue par utilisateur :
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Pour supprimer toutes les stratégies d’accès externe dont l’accès des utilisateurs extérieurs est désactivé

  - Cette commande supprime toutes les stratégies d’accès externe dont l’accès a été désactivé en dehors de l’utilisateur :
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
