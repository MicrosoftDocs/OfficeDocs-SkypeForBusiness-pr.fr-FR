---
title: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Vous ne pouvez pas supprimer complètement une stratégie globale. L’utilisation **de l’option** Supprimer sur la stratégie globale réinitialise uniquement la stratégie globale aux paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes.
ms.openlocfilehash: b3748ee6a2e8bcfde9cec58a45db48f73bbabcc3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765432"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Skype Entreprise Server 

Si vous avez créé ou configuré des stratégies d’accès des utilisateurs externes que vous ne souhaitez plus utiliser, vous pouvez utiliser les méthodes suivantes :

  - Supprimez toute stratégie utilisateur ou de site que vous avez créée.

  - Réinitialisez la stratégie globale à ses paramètres par défaut. Si vous appliquez les paramètres par défaut de la stratégie globale, l’accès des utilisateurs externes est refusé. La stratégie globale ne peut pas être supprimée.

Vous ne pouvez pas supprimer complètement une stratégie globale. **L’option** Supprimer de la stratégie globale réinitialise uniquement la stratégie globale aux paramètres par défaut, qui n’incluent pas la prise en charge des options d’accès des utilisateurs externes.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Pour réinitialiser la stratégie globale avec les paramètres par défaut

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, qui dispose de droits d’utilisateur équivalents, ou qui est affecté au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Supprimer**.

5.  À l’invite de confirmation de la suppression, cliquez sur **OK**. Un message s’affiche en haut de la page vous informant que la stratégie globale a été réinitialisée.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Réinitialisation de la stratégie d’accès externe globale à l’aide Windows PowerShell cmdlets

La stratégie d’accès externe globale peut être réinitialisée à l’Windows PowerShell l'Remove-CsExternalAccessPolicy cmdlet. Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Pour réinitialiser la stratégie d’accès externe globale

  - Cette commande redéfinit la stratégie d’accès externe globale :<br/><br/>Remove-CsExternalAccessPolicy -Identity « global »

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
