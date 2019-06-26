---
title: Gérer les comptes d’utilisateurs à l’aide du connecteur en ligne
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
f1keywords: None
ms.custom:
- PowerShell
description: Utilisez l’applet de connexion Get-CsOnlineUser dans Windows PowerShell pour obtenir des informations sur les utilisateurs de Skype entreprise Online de votre organisation.
ms.openlocfilehash: 02f3aa50f2256cd0d58f4c53cfa607c011bfa565
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221772"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Gérer les comptes d’utilisateurs à l’aide du connecteur en ligne

## <a name="manage-user-accounts"></a>Gérer les comptes d’utilisateurs

Cette rubrique contient les sections suivantes :

- [Retourner des informations sur tous vos utilisateurs de Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Renvoyer des informations pour un utilisateur spécifique dans Skype entreprise Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Renvoi d’informations spécifiques à des utilisateurs spécifiques dans Skype entreprise Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Renvoi d’une liste d’utilisateurs filtrés dans Skype entreprise Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> L’applet de connexion **Set-Csuser** est également incluse dans l’ensemble des applets de connexion accessibles aux administrateurs de Skype entreprise online. Toutefois, **Set-Csuser** ne peut pas être utilisé pour gérer Skype entreprise Online, à l’exception de la définition du paramètre _AudioVideoDisabled_ . Si vous essayez d’exécuter l’applet de requête avec n’importe quel autre paramètre, le message d’erreur similaire à ce qui suit s’affiche: impossible de définir «SipAddress». Ce paramètre est limité dans PowerShell client distant.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retourner des informations sur tous vos utilisateurs de Lync Online
<a name="BKAllUsers"> </a>

Pour renvoyer des informations sur tous les utilisateurs qui ont été activés pour Skype entreprise Online, appelez l’applet [de contrôle Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans aucun paramètre supplémentaire.

```
Get-CsOnlineUser
```

Pour renvoyer des informations pour un seul utilisateur sélectionné de manière aléatoire (par exemple, pour utiliser ce compte à des fins de test), appelez l’applet de requête **Get-CsOnlineUser** et définissez le paramètre de _résultats_ sur 1.

```
Get-CsOnlineUser -ResultSize 1
```

Cela amène l’applet de demande **Get-CsOnlineUser** à renvoyer des informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs de votre organisation. Pour renvoyer des informations pour cinq utilisateurs, définissez la valeur du paramètre _result_ sur 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Renvoyer des informations pour un utilisateur spécifique dans Skype entreprise Online
<a name="BKSpecificUser"> </a>

Il existe plusieurs façons de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’applet [de cmdlet Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Vous pouvez utiliser le nom complet des services de domaine Active Directory (AD DS) de l’utilisateur.

```
Get-CsOnlineUser -Identity "Ken Myer"
```

Vous pouvez utiliser l’adresse SIP de l’utilisateur.

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Vous pouvez utiliser le nom d’utilisateur principal (UPN) de l’utilisateur.

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Renvoi d’informations spécifiques à des utilisateurs spécifiques dans Skype entreprise Online
<a name="BKSpecificUsers"> </a>

Par défaut, l’applet [de connexion Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) renvoie une quantité considérable d’informations pour chaque compte d’utilisateur Skype entreprise online. Si vous êtes intéressé uniquement par un sous-ensemble de ces informations, canalisez les données renvoyées vers l’applet de cmdlet **Select-Object** . Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise l’applet de commande **Select-Object** pour limiter les informations affichées à l’écran avec le nom d’affichage et le plan de numérotation de Ken.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

La commande suivante renvoie le nom d’affichage et le plan de numérotation de tous vos utilisateurs.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Pour accéder aux propriétés d’un compte d’utilisateur Skype entreprise Online, utilisez la commande suivante.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Renvoi d’une liste d’utilisateurs filtrés dans Skype entreprise Online
<a name="BKListofUsers"> </a>

À l’aide de l’applet de requête [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et des paramètres _LdapFilter_ ou de _filtre_ , vous pouvez facilement renvoyer des informations sur un ensemble ciblé d’utilisateurs. Par exemple, cette commande renvoie tous les utilisateurs qui travaillent dans le service Finances.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Voir aussi
[Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


