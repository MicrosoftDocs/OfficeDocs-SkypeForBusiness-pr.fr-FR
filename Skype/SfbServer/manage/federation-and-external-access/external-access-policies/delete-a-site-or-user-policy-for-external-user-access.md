---
title: Suppression d’une stratégie utilisateur ou d’un site pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur répertoriée dans le Panneau de contrôle Skype Entreprise Server dans la page Stratégie d’accès externe.
ms.openlocfilehash: 79858592b8ba7dbcee692807bba3d2a472a8579cbc843ddeb96c25c811cc6df7
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848679"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Suppression d’une stratégie utilisateur ou d’un site pour l’accès des utilisateurs externes

Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez utiliser la méthode suivante :

  - Supprimez toute stratégie utilisateur ou de site que vous avez créée.

  - Réinitialisez la stratégie globale à ses paramètres par défaut. Si vous appliquez les paramètres par défaut de la stratégie globale, l’accès des utilisateurs externes est refusé. La stratégie globale ne peut pas être supprimée.


Vous pouvez supprimer n’importe quelle stratégie de site ou d’utilisateur répertoriée dans le Panneau de contrôle Skype Entreprise Server dans la page Stratégie **d’accès externe.** La suppression de la stratégie globale ne la supprime pas réellement, mais la réinitialise uniquement aux paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes. Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes.](reset-the-global-policy-for-external-user-access.md)


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Pour supprimer une stratégie de site ou d’utilisateur pour l’accès des utilisateurs externes

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 

3.  Cliquez sur **Accès des utilisateurs externes,** cliquez **sur Stratégie d’accès externe.**

4.  Sous **l’onglet Stratégie d’accès** externe, cliquez sur le site ou la stratégie utilisateur que vous souhaitez supprimer, cliquez sur **Modifier,** puis cliquez sur **Supprimer.**

5.  À l’invite de confirmation de la suppression, cliquez sur **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’Windows PowerShell cmdlets

Les stratégies d’accès externe peuvent être supprimées à l’aide Windows PowerShell et de la cmdlet Remove-CsExternalAccessPolicy externe. Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Pour supprimer une stratégie d’accès externe spécifique

  - Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :<br/><br/>Remove-CsExternalAccessPolicy -Identity « site:Redmond »


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue Utilisateur

  - Cette commande supprime toutes les stratégies d’accès externe configurées au niveau de l’étendue Utilisateur :<br/><br/>Get-CsExternalAccessPolicy -Filter « tag:* » | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Pour supprimer toutes les stratégies d’accès externe lorsque l’accès des utilisateurs externes est désactivé

  - Cette commande supprime toutes les stratégies d’accès externe lorsque l’accès des utilisateurs externes a été désactivé :<br/><br/>Get-CsExternalAccessPolicy | Where-Object {$_. EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
