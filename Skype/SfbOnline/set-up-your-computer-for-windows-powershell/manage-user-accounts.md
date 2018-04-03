---
title: Gérer les comptes d’utilisateur
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Pour obtenir des informations sur Skype votre société pour les utilisateurs professionnels en ligne, utilisez l’applet de commande Get-CsOnlineUser dans Windows PowerShell.
ms.openlocfilehash: b4647fae1baf84a2cc59a30c9291df196b56a88e
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="manage-user-accounts"></a>Gérer les comptes d’utilisateur

## <a name="manage-user-accounts"></a>Gérer les comptes d’utilisateur

Cette rubrique contient les sections suivantes :
  
- [Renvoyer des informations sur tous vos Skype pour les utilisateurs professionnels en ligne](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)
    
- [Renvoyer des informations pour un utilisateur spécifique dans Skype pour professionnels en ligne](manage-user-accounts.md#BKMKReturnInfoSpecificUser)
    
- [Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype pour professionnels en ligne](manage-user-accounts.md#BKMKReturninfoSpecificUsers)
    
- [Retourne une liste filtrée des utilisateurs dans Skype pour professionnels en ligne](manage-user-accounts.md#BKMKReturnFilteredListofUsers)
    
> [!NOTE]
> L’applet de commande **Set-CsUser** est également inclus dans le jeu d’applets de commande disponible à Skype pour les administrateurs de l’entreprise en ligne. Toutefois, **Ensemble-CsUser** ne peut pas actuellement être permet de gérer Skype pour Business Online, à l’exception de la définition du paramètre _AudioVideoDisabled_ . Si vous essayez d’exécuter l’applet de commande avec un autre paramètre, elle échoue avec un message d’erreur semblable à celui-ci : Impossible de définir la « SipAddress ». Ce paramètre est limité dans PowerShell de clients à distance.
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retourner des informations sur tous vos utilisateurs de Lync Online
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Pour retourner des informations sur tous les utilisateurs qui ont été activées pour Skype pour entreprise en ligne, appelez l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans paramètres supplémentaires.
  
```
Get-CsOnlineUser
```

Pour renvoyer les informations d’un utilisateur unique, sélectionné de façon aléatoire (par exemple, pour utiliser ce compte à des fins de test), appeler l’applet de commande **Get-CsOnlineUser** et 1 la valeur du paramètre _ResultSize_ .
  
```
Get-CsOnlineUser -ResultSize 1
```

L’applet de commande **Get-CsOnlineUser** renvoyer des informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs dans votre organisation à l’origine. Pour renvoyer les informations de cinq utilisateurs, définissez la valeur du paramètre _ResultSize_ sur 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Renvoyer des informations pour un utilisateur spécifique dans Skype pour professionnels en ligne
<a name="BKMKReturnInfoSpecificUser"> </a>

Il existe plusieurs façons de faire référence à un compte d’utilisateur spécifique lors de l’appel de l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Vous pouvez utiliser le nom complet de Services de domaine Active Directory (AD DS) de l’utilisateur.
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Vous pouvez utiliser l’adresse SIP de l’utilisateur.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Vous pouvez utiliser le nom principal de l’utilisateur de l’utilisateur (UPN).
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype pour professionnels en ligne
<a name="BKMKReturninfoSpecificUsers"> </a>

Par défaut, l’applet de commande [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) retourne une grande quantité d’informations pour chaque Skype pour le compte d’utilisateur Business Online. Si vous vous intéressez uniquement un sous-ensemble de ces informations, les données retournées à la cmdlet **Select-Object** de tuyau. Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise l’applet de commande **Select-Object** pour limiter les informations affichée à l’écran pour le nom d’affichage de Ken AD DS et le plan de numérotation.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

La commande suivant renvoie le nom complet et l’accès à planifier pour tous vos utilisateurs.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Pour rechercher les propriétés d’un Skype pour le compte d’utilisateur Business Online, utilisez la commande suivante.
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Retourne une liste filtrée des utilisateurs dans Skype pour professionnels en ligne
<a name="BKMKReturnFilteredListofUsers"> </a>

À l’aide de l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et les paramètres _FiltreLDAP_ ou de _filtre_ , vous pouvez facilement retourne des informations sur un ensemble ciblé d’utilisateurs. Par exemple, cette commande retourne tous les utilisateurs qui travaillent dans le département des finances.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 