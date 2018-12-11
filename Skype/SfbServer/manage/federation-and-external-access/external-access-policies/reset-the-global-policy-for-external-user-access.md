---
title: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous ne pouvez pas supprimer complètement une stratégie globale. À l’aide de l’option **Supprimer** de la stratégie globale réinitialise uniquement la stratégie globale pour les paramètres par défaut, qui ne comportent pas de prise en charge pour les options d’accès utilisateur externe.
ms.openlocfilehash: e3296167aa6d9a0a4fc6452c3505a068a69c3b78
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222799"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Skype pour Business Server 

Si vous avez créé ou configuré des stratégies d’accès utilisateur externe que vous ne souhaitez plus utiliser, procédez comme suit :

  - Supprimer une stratégie de site ou d’utilisateur que vous avez créé.

  - Réinitialiser la stratégie globale pour les paramètres par défaut. Les paramètres de stratégie globale par défaut refuser tout accès des utilisateurs externes. Impossible de supprimer la stratégie globale.

Vous ne pouvez pas supprimer complètement une stratégie globale. À l’aide de l’option **Supprimer** de la stratégie globale réinitialise uniquement la stratégie globale pour les paramètres par défaut, qui ne comportent pas de prise en charge pour les options d’accès utilisateur externe.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Pour réinitialiser la stratégie globale pour les paramètres par défaut

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, cliquez sur **Stratégie d’accès externe**.

4.  Sous l’onglet **Stratégie d’accès externe** , cliquez sur la stratégie globale, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.

5.  Lorsque vous y êtes invité à confirmer la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page pour vous informer que la stratégie globale a été réinitialisée.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redéfinition de la stratégie d’accès externe globale à l’aide des applets de commande Windows PowerShell

La stratégie d’accès externe globale peut être réinitialisée à l’aide de Windows PowerShell et l’applet de commande Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session Windows PowerShell à distance. 

## <a name="to-reset-the-global-external-access-policy"></a>Pour réinitialiser la stratégie d’accès externe globale

  - Cette commande réinitialise la stratégie d’accès externe globale :
    
        Remove-CsExternalAccessPolicy -Identity "global"

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


