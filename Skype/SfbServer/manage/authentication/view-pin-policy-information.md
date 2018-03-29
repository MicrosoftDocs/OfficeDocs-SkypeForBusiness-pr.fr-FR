---
title: Affichage des informations de stratégie de code confidentiel dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Résumé : Afficher les informations de stratégie de code PIN d’un utilisateur pour Skype pour Business Server 2015.'
ms.openlocfilehash: 3b62dae5cbd29c4622e30c6369a498eb48e126c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-pin-policy-information-in-skype-for-business-server-2015"></a>Affichage des informations de stratégie de code confidentiel dans Skype Entreprise Server 2015
 
**Résumé :** Permet d’afficher les informations de stratégie code PIN d’un utilisateur pour Skype pour Business Server 2015.
  
Vous pouvez utiliser l’onglet **Stratégie de code PIN** à vue identification personnel numéro (code PIN) l’authentification des utilisateurs qui se connectent à Skype pour les entreprises avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.
  
Suivez cette procédure étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une stratégie de code PIN dans Skype pour le panneau de configuration de Business Server

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Affichage des stratégies de code PIN à l’aide des applets de commande Windows PowerShell

Vous pouvez également afficher les stratégies de code PIN à l’aide de Windows PowerShell et l’applet de commande Get-CsPinPolicy. Cette applet de commande peut être exécuté à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-view-pin-policies"></a>Pour afficher les stratégies de code confidentiel

Pour afficher des informations sur toutes les stratégies de votre code PIN, tapez la commande suivante dans la Skype pour Business Server Management Shell et puis appuyez sur ENTRÉE :
    
  ```
  Get-CsPinPolicy
  ```

Vous obtiendrez des indications semblables à ceci :

  ```
  Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

#### 

[Créer une nouvelle stratégie de code PIN dans Skype pour Business Server 2015](create-a-new-pin-policy.md)

