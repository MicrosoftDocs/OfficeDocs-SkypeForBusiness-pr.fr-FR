---
title: Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes
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
description: Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur figurant dans le panneau de configuration Skype entreprise Server sur la page de stratégie d’accès externe.
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818285"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Suppression d’une stratégie utilisateur ou de site pour l’accès des utilisateurs externes

Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit :

  - Supprimez les stratégies de site ou d’utilisateur que vous avez créées.

  - Rétablir les paramètres par défaut de la stratégie globale. Les paramètres de stratégie globale par défaut refusent tout accès utilisateur externe. La stratégie globale ne peut pas être supprimée.


Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur figurant dans le panneau de configuration Skype entreprise Server sur la page de **stratégie d’accès externe** . La suppression de la stratégie globale n’entraîne pas la suppression effective de celle-ci, mais elle permet de rétablir les paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes. Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans l’onglet **stratégie d’accès externe** , cliquez sur le site ou la stratégie d’utilisateur à supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.

5.  Lorsque vous êtes invité à confirmer la suppression, cliquez sur **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell

Les stratégies d’accès externe peuvent être supprimées à l’aide de Windows PowerShell et de l’applet de passe Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Pour supprimer une stratégie d’accès externe spécifique

  - Cette commande supprime la stratégie d’accès externe appliquée au site de Redmond :
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue par utilisateur

  - Cette commande supprime toutes les stratégies d’accès externe configurées pour l’étendue par utilisateur :
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Pour supprimer toutes les stratégies d’accès externes pour lesquelles l’accès des utilisateurs externes est désactivé

  - Cette commande supprime toutes les stratégies d’accès externe dont l’accès à l’utilisateur extérieur a été désactivé :
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
