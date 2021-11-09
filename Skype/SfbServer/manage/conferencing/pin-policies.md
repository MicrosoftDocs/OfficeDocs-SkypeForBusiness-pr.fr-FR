---
title: Gérer les stratégies de code confidentiel pour les conférences téléphoniques dans Skype Entreprise Server
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
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Résumé : Découvrez comment gérer les stratégies de code confidentiel pour les conférences téléphoniques dans Skype Entreprise Server.'
ms.openlocfilehash: bf78a565cefb38a9a6e747c2b22b74a640a9e706
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862471"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gérer les stratégies de code confidentiel pour les conférences téléphoniques dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer les stratégies de code confidentiel pour les conférences téléphoniques dans Skype Entreprise Server.
  
Skype Entreprise Server utilisateurs qui ont des informations d’identification des services de domaine Active Directory (AD DS) dans votre organisation peuvent participer à des conférences téléphoniques en tant qu’utilisateurs authentifiés à l’aide d’un code confidentiel. La stratégie de code confidentiel définit les règles de fonctionnement des code confidentiels des conférences téléphoniques.
  
 Si vous souhaitez utiliser la même stratégie de code confidentiel pour l’ensemble de votre organisation, vous pouvez utiliser la stratégie de code confidentiel globale et la modifier selon vos besoins. La stratégie d’authentification par code confidentiel globale définit les règles des codes confidentiels pour les conférences rendez-vous au niveau forêt. Vous pouvez modifier la stratégie de code confidentiel globale, mais vous ne pouvez pas la supprimer.
  
Vous pouvez créer une stratégie de code confidentiel si vous souhaitez qu’une stratégie spécifique s’applique à un site ou à un certain groupe d’utilisateurs.
  
Les stratégies de code confidentiel s’appliquent aux utilisateurs de l’étendue la plus étroite à l’étendue la plus large. Si vous affectez une stratégie de code confidentiel au niveau de l’utilisateur à un utilisateur, ces paramètres sont prioritaires. Si vous n’affectez pas de stratégie utilisateur, la stratégie de code confidentiel au niveau du site s’applique, si elle existe. Si aucune stratégie utilisateur ou site ne s’applique, la stratégie globale de code confidentiel fournit les paramètres par défaut.
  
## <a name="view-information-about-pin-policies"></a>Afficher des informations sur les stratégies de code confidentiel

Vous pouvez afficher des informations sur les stratégies de code confidentiel à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Afficher des informations sur les stratégies de code confidentiel à l’aide du Skype Entreprise Server de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de** code confidentiel, cliquez sur la stratégie de code confidentiel à afficher, cliquez sur **Modifier,** puis sur Afficher **les détails.**
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Afficher des informations sur les stratégies de code confidentiel à l’aide Skype Entreprise Server Management Shell

Pour afficher des informations sur les stratégies de code confidentiel, utilisez l’cmdlet **Get-CsPinPolicy.** Par exemple, la commande suivante retourne des informations sur une stratégie de code confidentiel unique dont l’identité est site:Redmond :
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Pour plus d’informations, notamment une description complète de la syntaxe et la liste des paramètres, voir [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modifier la stratégie de code confidentiel globale

Vous pouvez modifier la stratégie de code confidentiel globale à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modifier la stratégie globale de code confidentiel des conférences téléphoniques à l’aide du Skype Entreprise Server de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur la stratégie **Globale**, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de code confidentiel**, dans **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous voulez autoriser. La longueur minimale par défaut est de cinq chiffres.
    
6. Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.
    
7. Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.
    
8. Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.
    
9. Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.
    
10. Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.
    
11. Pour autoriser les modèles courants de codes confidentiels, tels que les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, Microsoft recommande de ne pas autoriser les modèles courants. 
  
12. Cliquez sur **Valider**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modifier la stratégie globale de code confidentiel des conférences téléphoniques à l’aide Skype Entreprise Server Management Shell

Pour modifier la stratégie globale de code confidentiel de conférence téléphonique, utilisez l’cmdlet **Set-CsPinPolicy.**
  
La commande suivante modifie la valeur de MinPasswordLength pour toutes les stratégies de code confidentiel configurées pour être utilisés dans l’organisation. Pour ce faire, la commande appelle d’abord l’cmdlet **Get-CsPinPolicy** sans paramètre afin de récupérer une collection de toutes les stratégies de code confidentiel existantes. Cette collection est ensuite canalée vers l’cmdlet **Set-CsPinPolicy,** qui modifie la valeur de la propriété MinPasswordLength pour chaque stratégie de la collection :
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, voir [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Créer une stratégie de code confidentiel d’utilisateur ou de site

Vous pouvez créer une stratégie de code confidentiel d’utilisateur ou de site à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Créer une stratégie de code confidentiel d’utilisateur ou de site à l’aide Skype Entreprise Server Panneau de contrôle

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
   - Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.
    
   - Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.
    
5. Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.
    
6. Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.
    
7. Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.
    
8. Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.
    
9. Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.
    
10. Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.
    
11. Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.
    
12. Pour autoriser les modèles courants de codes confidentiels, tels que les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, Microsoft recommande de ne pas autoriser les modèles courants. 
  
13. Cliquez sur **Valider**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Créer une stratégie de code confidentiel d’utilisateur ou de site à l’aide Skype Entreprise Server Management Shell

Pour créer une stratégie de code confidentiel d’utilisateur ou de site, utilisez l’cmdlet **New-CsPinPolicy.**
  
La commande suivante crée une stratégie de code confidentiel avec l’identité site:Redmond. Cette commande inclut un seul paramètre facultatif, MinPasswordLength, qui est utilisé pour définir la propriété MinPasswordLength sur 7. Toutes les propriétés de stratégie restantes seront configurées au moyen des valeurs par défaut.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, voir [New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modifier une stratégie de code confidentiel d’utilisateur ou de site

Vous pouvez modifier une stratégie de code confidentiel d’utilisateur ou de site à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modifier une stratégie de code confidentiel d’utilisateur ou de site à l’aide Skype Entreprise Server Panneau de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de code confidentiel**, modifiez tous les paramètres de la stratégie (à l’exception de son nom qui ne peut être modifié).
    
6. Cliquez sur **Valider**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modifier une stratégie de code confidentiel d’utilisateur ou de site à l’aide Skype Entreprise Server Management Shell

Pour modifier la stratégie de code confidentiel des conférences téléphoniques, utilisez l’cmdlet **Set-CsPinPolicy.**
  
La commande suivante modifie la stratégie de code confidentiel attribuée au site Redmond. Dans ce cas, la commande modifie la valeur de la propriété MinPasswordLength sur 10 ; Cela signifie que les nouveaux pin-ins devront contenir au moins 10 chiffres :
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, voir [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Supprimer une stratégie de code confidentiel d’utilisateur ou de site

Vous pouvez supprimer une stratégie de code confidentiel d’utilisateur ou de site à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Supprimer une stratégie de code confidentiel d’utilisateur ou de site à l’aide Skype Entreprise Server Panneau de contrôle

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.
    
4. Dans la page **Stratégie de** code confidentiel, cliquez sur la stratégie de code confidentiel à modifier, cliquez sur **Modifier,** puis sur **Supprimer.**
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Supprimer une stratégie de code confidentiel d’utilisateur ou de site à l’aide Skype Entreprise Server Management Shell

Pour supprimer une stratégie de code confidentiel d’utilisateur ou de site, utilisez l’cmdlet **Remove-CsPinPolicy.**
  
La commande suivante supprime toutes les stratégies de code confidentiel qui ont été configurées au niveau de l’étendue Site. Pour ce faire, utilisez l’cmdlet **Get-CsPinPolicy,** ainsi que le paramètre Filter, pour retourner une collection de toutes les stratégies dont l’identité commence par les caractères « site: ». Cette collection est ensuite canalée vers l’cmdlet **Remove-CsPinPolicy,** qui supprime chaque stratégie de la collection :
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, voir [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
