---
title: Supprimer une stratégie de code confidentiel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Résumé : Supprimez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: 97c8f6ce8ab2f86e1a44032e90b6d23f91e0552587f52d46ba89c84202576339
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336884"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Supprimer une stratégie de code confidentiel dans Skype Entreprise Server
 
**Résumé :** Supprimez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.
  
Suivez cette procédure pour supprimer une stratégie de code confidentiel (PIN).
  
> [!NOTE]
> Vous ne pouvez pas supprimer la stratégie de code confidentiel globale. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Pour supprimer une stratégie de code confidentiel dans Skype Entreprise Server de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, dans le champ de recherche, tapez entièrement ou partiellement le nom de la stratégie à supprimer.
    
5. Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’Windows PowerShell cmdlets

Vous pouvez supprimer des stratégies de code confidentiel à l’Windows PowerShell la cmdlet Remove-CsPinPolicy de code confidentiel. Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, voir l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Pour supprimer une stratégie de code confidentiel spécifique

- Cette commande supprime la stratégie de code confidentiel avec l’identité RedmondPinPolicy :
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Pour supprimer toutes les stratégies de code confidentiel appliquées à l’étendue Site

- Cette commande supprime toutes les stratégies de code confidentiel configurées au niveau du site :
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Pour supprimer toutes les stratégies de code confidentiel qui autorisent l’utilisation de modèles courants

- Cette commande supprime toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs : G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
