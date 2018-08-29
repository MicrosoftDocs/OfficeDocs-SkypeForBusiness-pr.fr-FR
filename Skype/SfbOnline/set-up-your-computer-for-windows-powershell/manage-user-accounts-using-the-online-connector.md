---
title: Gérer les comptes d’utilisateur à l’aide du connecteur en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: Utilisez l’applet de commande Get-CsOnlineUser dans Windows PowerShell pour obtenir des informations sur Skype de votre organisation pour les utilisateurs professionnels en ligne.
ms.openlocfilehash: 96f4025b062e13086bcc878fd9166ced9325fbee
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250193"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>Gérer les comptes d’utilisateur à l’aide du connecteur en ligne

## <a name="manage-user-accounts"></a>Gérer les comptes utilisateur

Cette rubrique contient les sections suivantes :

- [Retourner des informations sur tous vos utilisateurs de Lync Online](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [Retourner des informations pour un utilisateur spécifique Skype pour Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [Retourner des informations spécifiques pour des utilisateurs spécifiques Skype pour Business Online](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [Renvoyer la liste filtrée des utilisateurs dans Skype pour Business Online](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> L’applet de commande **Set-CsUser** est également inclus dans l’ensemble des applets de commande disponibles pour Skype pour les administrateurs d’entreprise en ligne. Toutefois, **Set-CsUser** ne peut pas être utilisé actuellement gestion Skype pour Business Online, à l’exception de la définition du paramètre _AudioVideoDisabled_ . Si vous essayez d’exécuter l’applet de commande avec aucun autre paramètre, l’opération échoue et un message d’erreur semblable à ceci : Impossible de définir « SipAddress ». Ce paramètre est limité à distance PowerShell client.

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>Retourner des informations sur tous vos utilisateurs de Lync Online
<a name="BKAllUsers"> </a>

Pour retourner des informations sur tous les utilisateurs qui ont été activés pour Skype pour Business Online, appelez la cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans aucun paramètre supplémentaire.

```
Get-CsOnlineUser
```

Pour retourner des informations pour un utilisateur unique, sélectionnée aléatoirement (par exemple, pour utiliser ce compte à des fins de test), appelez la cmdlet **Get-CsOnlineUser** et définissez le paramètre _ResultSize_ 1.

```
Get-CsOnlineUser -ResultSize 1
```

L’applet de commande **Get-CsOnlineUser** renvoyer des informations pour un seul utilisateur, quel que soit le nombre d’utilisateurs dans votre organisation à l’origine. Pour retourner des informations pour les utilisateurs de cinq, définissez la valeur du paramètre _ResultSize_ à 5.

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>Retourner des informations pour un utilisateur spécifique Skype pour Business Online
<a name="BKSpecificUser"> </a>

Il existe plusieurs manières de faire référence à un compte d’utilisateur spécifique lorsque vous appelez l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Vous pouvez utiliser le nom complet de Services de domaine Active Directory (AD DS) de l’utilisateur.

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

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>Retourner des informations spécifiques pour des utilisateurs spécifiques Skype pour Business Online
<a name="BKSpecificUsers"> </a>

Par défaut, l’applet de commande [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) renvoie une grande quantité d’informations pour chaque Skype Business en ligne compte d’utilisateur. Si vous êtes intéressé par uniquement un sous-ensemble de ces informations, redirigez les données retournées à la cmdlet **Select-Object** . Par exemple, cette commande renvoie toutes les données de l’utilisateur Ken Myer, puis utilise la cmdlet **Select-Object** pour limiter les informations affichée à l’écran pour le nom complet de domaine Active Directory de Ken et le plan de numérotation.

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

La commande suivante renvoie le nom complet et la numérotation planifier pour tous vos utilisateurs.

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Pour rechercher les propriétés d’un Skype Business en ligne compte d’utilisateur, utilisez la commande suivante.

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>Renvoyer la liste filtrée des utilisateurs dans Skype pour Business Online
<a name="BKListofUsers"> </a>

À l’aide de l’applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et les paramètres _LdapFilter_ ou de _filtre_ , vous pouvez facilement revenir plus d’informations sur un ensemble d’utilisateurs ciblé. Par exemple, cette commande retourne tous les utilisateurs qui travaillent dans le service Finance.

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)


