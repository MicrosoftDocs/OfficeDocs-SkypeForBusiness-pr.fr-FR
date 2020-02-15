---
title: Réinitialiser la stratégie globale pour l’accès des utilisateurs externes
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Il est impossible de supprimer totalement une stratégie globale. L’utilisation de l’option **Supprimer** sur la stratégie globale la réinitialise uniquement avec les paramètres par défaut, c’est-à-dire sans prise en charge des options d’accès des utilisateurs externes.
ms.openlocfilehash: acb275ac924dbb5b7e9ad377ab4d287a0734f752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043656"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Skype entreprise Server 

Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez procéder comme suit :

  - Supprimez toute stratégie utilisateur ou de site que vous avez créée.

  - Réinitialisez la stratégie globale à ses paramètres par défaut. Si vous appliquez les paramètres par défaut de la stratégie globale, l’accès des utilisateurs externes est refusé. La stratégie globale ne peut pas être supprimée.

Il est impossible de supprimer totalement une stratégie globale. L’utilisation de l’option **Supprimer** sur la stratégie globale la réinitialise uniquement avec les paramètres par défaut, c’est-à-dire sans prise en charge des options d’accès des utilisateurs externes.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Pour réinitialiser la stratégie globale avec les paramètres par défaut

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Supprimer**.

5.  À l’invite de confirmation de la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Réinitialisation de la stratégie d’accès externe globale à l’aide des applets de commande Windows PowerShell

La stratégie d’accès externe globale peut être réinitialisée à l’aide de Windows PowerShell et de l’applet de commande Remove-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Pour réinitialiser la stratégie d’accès externe globale

  - Cette commande redéfinit la stratégie d’accès externe globale :
    
        Remove-CsExternalAccessPolicy -Identity "global"

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .


