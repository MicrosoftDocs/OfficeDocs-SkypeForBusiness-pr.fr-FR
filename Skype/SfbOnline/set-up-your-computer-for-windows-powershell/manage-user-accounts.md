---
title: Gérer les comptes d’utilisateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Utilisez l'Get-CsOnlineUser de la Windows PowerShell pour obtenir des informations sur les utilisateurs Skype Entreprise Online de votre organisation.
ms.openlocfilehash: 97d717d3472ae96dc66ad58ee5699f3f646a0f3b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706239"
---
# <a name="manage-user-accounts"></a>Gérer les comptes d’utilisateurs

## <a name="manage-user-accounts"></a>Gérer les comptes d’utilisateurs

Cette rubrique contient les sections suivantes :

- [Retourner des informations sur tous vos utilisateurs de Lync Online](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [Renvoyer les informations d’un utilisateur spécifique dans Skype Entreprise Online](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype Entreprise Online](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [Renvoyer une liste filtrée des utilisateurs dans Skype Entreprise Online](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> **L’cmdlet Set-CsUser** est également incluse dans l’ensemble des cmdlets disponibles pour les administrateurs Skype Entreprise Online. Toutefois, **Set-CsUser** ne peut actuellement pas être utilisé pour gérer Skype Entreprise Online, à l’exception de la définition du paramètre _AudioVideoDisabled._ Si vous essayez d’exécuter la cmdlet avec un autre paramètre, elle échouera avec un message d’erreur semblable à ce qui suivant : Impossible de définir « SipAddress ». Ce paramètre est restreint dans Remote Tenant PowerShell.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retourner des informations sur tous vos utilisateurs de Lync Online
<a name="BKMKReturnInfoAboutAllUsers"> </a>

Pour renvoyer des informations sur tous vos utilisateurs qui ont été activés pour Skype Entreprise Online, appelez l’cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans aucun paramètre supplémentaire.

```PowerShell
Get-CsOnlineUser
```

Pour renvoyer les informations d’un utilisateur sélectionné de façon aléatoire (par exemple, pour utiliser ce compte à des fins de test), appelez la cmdlet **Get-CsOnlineUser** et définissez le paramètre _ResultSize_ sur 1.

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

Ainsi, l’cmdlet **Get-CsOnlineUser** retourne les informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs de votre organisation. Pour renvoyer les informations de cinq utilisateurs, définissez la valeur du paramètre _ResultSize_ sur 5.

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Renvoyer les informations d’un utilisateur spécifique dans Skype Entreprise Online
<a name="BKMKReturnInfoSpecificUser"> </a>

Il existe plusieurs façons de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’cmdlet [Get-CsOnlineUser.](https://go.microsoft.com/fwlink/p/?linkid=849603) Vous pouvez utiliser le nom complet AD DS (Active Directory Domain Services) de l’utilisateur.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

Vous pouvez utiliser l’adresse SIP de l’utilisateur.

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Vous pouvez utiliser le nom d’utilisateur principal (UPN) de l’utilisateur.

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype Entreprise Online
<a name="BKMKReturninfoSpecificUsers"> </a>

Par défaut, la cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) renvoie une grande quantité d’informations pour chaque compte d’utilisateur Skype Entreprise Online. Si seul un sous-ensemble de ces informations vous intéresse, pipez les données renvoyées vers l’cmdlet **Select-Object.** Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise l’cmdlet **Select-Object** pour limiter les informations affichées à l’écran au nom d’affichage AD DS de Ken et au plan de numérotation.

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

La commande suivante renvoie le nom d’affichage et le plan de numérotation de tous vos utilisateurs.

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Pour rechercher les propriétés d’un compte d’utilisateur Skype Entreprise Online, utilisez la commande suivante.

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Renvoyer une liste filtrée des utilisateurs dans Skype Entreprise Online
<a name="BKMKReturnFilteredListofUsers"> </a>

En utilisant l’cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et les  paramètres du filtre ou du filtre _Ldap,_ vous pouvez facilement renvoyer des informations sur un ensemble ciblé d’utilisateurs. Par exemple, cette commande renvoie tous les utilisateurs qui travaillent dans le service Finances.

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Sujets associés
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


