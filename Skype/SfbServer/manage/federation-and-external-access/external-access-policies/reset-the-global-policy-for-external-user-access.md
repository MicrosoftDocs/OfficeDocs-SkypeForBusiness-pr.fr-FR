---
title: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous ne pouvez pas supprimer complètement une stratégie globale. L’utilisation de l’option **supprimer** dans la stratégie globale rétablit uniquement les paramètres par défaut de la stratégie globale, qui ne prennent pas en charge les options d’accès des utilisateurs externes.
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280144"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes dans Skype entreprise Server 

Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit:

  - Supprimez les stratégies de site ou d’utilisateur que vous avez créées.

  - Rétablir les paramètres par défaut de la stratégie globale. Les paramètres de stratégie globale par défaut refusent tout accès utilisateur externe. La stratégie globale ne peut pas être supprimée.

Vous ne pouvez pas supprimer complètement une stratégie globale. L’utilisation de l’option **supprimer** dans la stratégie globale rétablit uniquement les paramètres par défaut de la stratégie globale, qui ne prennent pas en charge les options d’accès des utilisateurs externes.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Pour rétablir les paramètres par défaut de la stratégie globale

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans l’onglet **stratégie d’accès externe** , cliquez sur politique globale, cliquez sur **modifier**, puis cliquez sur **supprimer**.

5.  Lorsque vous êtes invité à confirmer la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Réinitialisation de la stratégie d’accès externe globale à l’aide des cmdlets Windows PowerShell

La stratégie d’accès externe globale peut être réinitialisée à l’aide de Windows PowerShell et de l’applet de passe Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou d’une session distante Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Pour réinitialiser la stratégie d’accès externe globale

  - Cette commande réinitialise la stratégie globale d’accès externe:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


