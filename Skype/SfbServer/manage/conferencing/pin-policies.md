---
title: Gérer les stratégies de PIN pour les conférences rendez-vous dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Résumé: Découvrez comment gérer les stratégies de code confidentiel pour les conférences rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: a8db6fc0398d2f577afe54ab2289c3122adcb197
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280354"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gérer les stratégies de PIN pour les conférences rendez-vous dans Skype entreprise Server
 
**Résumé:** Apprenez à gérer les stratégies de code confidentiel pour la Conférence rendez-vous dans Skype entreprise Server.
  
Les utilisateurs de Skype entreprise Server qui disposent des informations d’identification AD DS (Active Directory Domain Services) de votre organisation peuvent participer à des conférences rendez-vous en utilisant un code confidentiel (PIN) pour les utilisateurs authentifiés. La stratégie de code confidentiel définit le fonctionnement des codes confidentiels d’accès aux conférences rendez-vous.
  
 Si vous voulez utiliser la même stratégie de code confidentiel au sein de toute votre organisation, vous pouvez utiliser la stratégie de code confidentiel globale et la modifier, au besoin. La stratégie d’authentification par code confidentiel globale définit les règles des codes confidentiels pour les conférences rendez-vous au niveau forêt. Vous pouvez modifier la stratégie de code confidentiel globale, mais vous ne pouvez pas la supprimer.
  
Vous pouvez en créer une si vous voulez qu’une stratégie spécifique s’applique à un site ou à un groupe d’utilisateurs spécifique.
  
Les stratégies de code confidentiel s’appliquent aux utilisateurs, de l’étendue la plus petite à l’étendue la plus grande. Si vous affectez une stratégie de code confidentiel au niveau utilisateur, ces paramètres prévalent. Si vous n’affectez pas de stratégie au niveau utilisateur, la stratégie de code confidentiel de niveau site s’applique, le cas échéant. En l’absence de stratégie de niveau utilisateur ou site, les paramètres par défaut de la stratégie de code confidentiel globale sont appliqués.
  
## <a name="view-information-about-pin-policies"></a>Affichage des informations sur vos stratégies de code confidentiel

Vous pouvez afficher des informations sur les stratégies de code confidentiel en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Afficher des informations sur les stratégies de code confidentiel en utilisant le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à afficher, sur **Modifier**, puis sur **Afficher les détails**.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Afficher des informations sur les stratégies de code confidentiel à l’aide de Skype entreprise Server Management Shell

Pour afficher des informations sur les stratégies de code confidentiel, utilisez l’applet de commande **Get-CsPinPolicy**. Par exemple, la commande suivante retourne les informations relatives à une seule stratégie de code confidentiel dont l’identité est site:Redmond:.
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modification de la stratégie de code confidentiel globale

Vous pouvez modifier la stratégie de code confidentiel global à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modification de la stratégie de code confidentiel de conférence rendez-vous globale à l’aide du panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur la stratégie **Globale**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de code confidentiel**, dans **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel à autoriser. La longueur minimale par défaut est de cinq chiffres.
    
6. Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est déterminé automatiquement en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est déterminé automatiquement.
    
7. Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion à autoriser.
    
8. Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.
    
9. Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.
    
10. Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant de pouvoir réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.
    
11. Pour autoriser les modèles courants de codes confidentiels, comme les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, Microsoft vous recommande de ne pas autoriser les modèles courants. 
  
12. Cliquez sur **Valider**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modification de la stratégie de code confidentiel de conférence rendez-vous globale à l’aide de Skype entreprise Server Management Shell

Pour modifier la stratégie globale de code confidentiel de conférence rendez-vous, utilisez l’applet de commande **Set-CsPinPolicy**.
  
La commande suivante retourne la valeur de MinPasswordLength de toutes les stratégies de code confidentiel configurées pour être utilisées dans l’organisation. Pour y parvenir, la commande appelle d’abord l’applet de commande **Get-CsPinPolicy**, sans aucun paramètre, afin de récupérer une collection de toutes les stratégies de code confidentiel existantes. Cette collection est ensuite redirigée vers l’applet de commande **Set-CsPinPolicy** qui modifie la valeur de la propriété MinPasswordLength pour chaque stratégie de la collection.
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Création d’une stratégie de code confidentiel au niveau utilisateur ou site

Vous pouvez créer une stratégie d’utilisateur ou de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Création d’une stratégie d’utilisateur ou de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
   - Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.
    
   - Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.
    
5. Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.
    
6. Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.
    
7. Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est déterminé automatiquement en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est déterminé automatiquement.
    
8. Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion à autoriser.
    
9. Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.
    
10. Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.
    
11. Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant de pouvoir réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.
    
12. Pour autoriser les modèles courants de codes confidentiels, comme les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, Microsoft vous recommande de ne pas autoriser les modèles courants. 
  
13. Cliquez sur **Valider**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Création d’une stratégie d’utilisateur ou de code confidentiel de site à l’aide de Skype entreprise Server Management Shell

Pour créer une stratégie de code confidentiel au niveau utilisateur ou site, utilisez l’applet de commande **New-CsPinPolicy**
  
La commande ci-dessous crée une stratégie de code confidentiel dont l’identité est site:Redmond. Cette commande inclut un seul paramètre facultatif, MinPasswordLength, qui permet de définir la propriété MinPasswordLength sur 7. Toutes les propriétés de stratégie restantes seront configurées au moyen des valeurs par défaut.
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Pour plus d’informations, y compris une description de syntaxe complète et une liste de paramètres, voir [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modification d’une stratégie de code confidentiel au niveau utilisateur ou site

Vous pouvez modifier une stratégie d’un utilisateur ou d’un site Web à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modification d’une stratégie de code confidentiel d’utilisateur ou de site à l’aide du panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de code confidentiel**, modifiez tous les paramètres de la stratégie (à l’exception de son nom qui ne peut être modifié).
    
6. Cliquez sur **Valider**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modifier une stratégie d’un utilisateur ou d’un code confidentiel de site à l’aide de Skype entreprise Server Management Shell

Pour modifier la stratégie de code confidentiel de conférence rendez-vous, utilisez l’applet de commande **Set-CsPinPolicy**.
  
La commande ci-dessous modifie la stratégie de code confidentiel affectée au site de Redmond. Dans ce cas, la commande modifie la valeur de la propriété MinPasswordLength sur 10, ce qui signifie que les nouveaux codes confidentiels devront contenir au moins 10 chiffres.
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Suppression d’une stratégie de code confidentiel au niveau utilisateur ou site

Vous pouvez supprimer une stratégie d’utilisateur ou de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Supprimer un utilisateur ou une stratégie de code confidentiel de site à l’aide du panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Supprimer**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Supprimer un utilisateur ou une stratégie de code confidentiel de site à l’aide de Skype entreprise Server Management Shell

Pour supprimer une stratégie de code confidentiel au niveau utilisateur ou site, utilisez l’applet de commande **New-CsPinPolicy**
  
La commande ci-dessous supprime toutes les stratégies de code confidentiel configurées dans l’étendue de site. Pour ce faire, utilisez l’applet de commande **Get-CsPinPolicy** avec le paramètre Filter pour renvoyer une collection de toutes les stratégies ayant une identité qui commence par les caractères « site: ». Cette collection est ensuite redirigée vers l’applet de commande **Remove-CsPinPolicy** qui supprime chaque stratégie de la collection :
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  

