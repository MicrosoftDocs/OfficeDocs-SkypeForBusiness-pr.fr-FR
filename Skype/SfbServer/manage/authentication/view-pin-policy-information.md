---
title: Afficher les informations de stratégie de code confidentiel dans Skype Entreprise Server
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Résumé : Affichez les informations de stratégie de code confidentiel d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806524"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Afficher les informations de stratégie de code confidentiel dans Skype Entreprise Server
 
**Résumé :** Afficher les informations de stratégie de code confidentiel d’un utilisateur pour Skype Entreprise Server.
  
Vous pouvez  utiliser l’onglet Stratégie de code confidentiel pour afficher l’authentification par code confidentiel des utilisateurs qui se connectent à Skype Entreprise avec des téléphones IP. Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.
  
Suivez ces étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une stratégie de code confidentiel dans le Panneau de contrôle Skype Entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Affichage des stratégies de code confidentiel à l’Windows PowerShell cmdlets

Vous pouvez également afficher les stratégies de code confidentiel à l’Windows PowerShell la cmdlet Get-CsPinPolicy code confidentiel. Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-view-pin-policies"></a>Pour afficher les stratégies de code confidentiel

Pour afficher des informations sur toutes vos stratégies de code confidentiel, tapez la commande suivante dans l’environnement de ligne de commande Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
    
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

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Get-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Voir aussi

[Créer une stratégie de code confidentiel dans Skype Entreprise Server](create-a-new-pin-policy.md)
