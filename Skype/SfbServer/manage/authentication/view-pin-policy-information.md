---
title: Afficher les informations de stratégie de code confidentiel dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Résumé : Affichez les informations de stratégie de code confidentiel d’un utilisateur pour Skype entreprise Server.'
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818696"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Afficher les informations de stratégie de code confidentiel dans Skype entreprise Server
 
**Résumé :** Afficher les informations de stratégie de code confidentiel d’un utilisateur pour Skype entreprise Server.
  
Vous pouvez utiliser l’onglet **stratégie de code confidentiel** pour afficher l’authentification par code confidentiel (pin) des utilisateurs qui se connectent à Skype entreprise avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.
  
Suivez cette procédure pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une stratégie de code confidentiel dans le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Affichage de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez également afficher les stratégies de code confidentiel à l’aide de Windows PowerShell et de l’applet de cmdlet Get-CsPinPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
### <a name="to-view-pin-policies"></a>Pour afficher les stratégies de code confidentiel

Pour afficher des informations sur toutes les stratégies de code confidentiel, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Vous obtiendrez des indications semblables à ceci :

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

[Créer une nouvelle stratégie de code confidentiel dans Skype entreprise Server](create-a-new-pin-policy.md)
