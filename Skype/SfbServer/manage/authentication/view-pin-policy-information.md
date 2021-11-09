---
title: Afficher les informations de stratégie de code confidentiel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Résumé : Affichez les informations de stratégie de code confidentiel d’un utilisateur Skype Entreprise Server.'
ms.openlocfilehash: 0a0e67d45a89e2c03f45017bfddb1ffaa9bec285
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862481"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Afficher les informations de stratégie de code confidentiel dans Skype Entreprise Server
 
**Résumé :** Afficher les informations de stratégie de code confidentiel d’un Skype Entreprise Server.
  
Vous pouvez  utiliser l’onglet Stratégie de code confidentiel pour afficher l’authentification par code confidentiel des utilisateurs qui se connectent à Skype Entreprise avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.
  
Suivez ces étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une stratégie de code confidentiel dans le Skype Entreprise Server de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Affichage des stratégies de code confidentiel à l’Windows PowerShell cmdlets

Vous pouvez également afficher les stratégies de code confidentiel à l’Windows PowerShell et la cmdlet Get-CsPinPolicy code confidentiel. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-view-pin-policies"></a>Pour afficher les stratégies de code confidentiel

Pour afficher des informations sur toutes vos stratégies de code confidentiel, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Cette action a pour effet de renvoyer des informations similaires à ce qui suit :

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Voir aussi

[Créer une stratégie de code confidentiel dans Skype Entreprise Server](create-a-new-pin-policy.md)