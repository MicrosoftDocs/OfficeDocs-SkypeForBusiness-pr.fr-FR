---
title: "Gérer les comptes d'utilisateur à l'aide de la Skype pour Business Connector en ligne"
ms.author: tonysmit
author: tonysmit
ms.date: 5/23/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
description: "Use the Get-CsOnlineUser cmdlet in Windows PowerShell to get information about your organization's Skype for Business Online users."
---

# Gérer les comptes d'utilisateur à l'aide de la Skype pour Business Connector en ligne

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/a226b0d4-6359-42b8-808d-4b8ab3736d3b). 
  
## Gérer les comptes d'utilisateur

Cette rubrique contient les sections suivantes :
  
- [Renvoyer des informations sur tous vos Skype pour les utilisateurs professionnels en ligne](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoAboutAllUsers)
    
- [Renvoyer des informations pour un utilisateur spécifique dans Skype entreprise Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnInfoSpecificUser)
    
- [Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype entreprise Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturninfoSpecificUsers)
    
- [Renvoyer une liste filtrée des utilisateurs dans Skype entreprise Online](a226b0d4-6359-42b8-808d-4b8ab3736d3b.md#BKMK_ReturnFilteredListofUsers)
    
> [!NOTE]
> L'applet de commande **Set-CsUser** est également inclus dans l'ensemble des applets de commande accessibles aux administrateurs Skype Entreprise Online. Toutefois, **Set-CsUser** ne peut pas actuellement servir à gérer Skype Entreprise Online, à l'exception de la définition du paramètre _AudioVideoDisabled_. Si vous essayez d'exécuter l'applet de commande avec tous les autres paramètres, elle échouera avec un message d'erreur semblable à celui-ci : Impossible de définir « SipAddress ». Ce paramètre est restreint au sein de la session PowerShell distante client.
  
### Renvoyer des informations sur tous vos Skype pour les utilisateurs professionnels en ligne
<a name="BKMK_ReturnInfoAboutAllUsers"> </a>

Pour renvoyer des informations sur tous les utilisateurs qui ont été activés pour Skype Entreprise Online, appelez l'applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sans paramètres supplémentaires.
  
```
Get-CsOnlineUser
```

Pour renvoyer des informations pour un utilisateur unique, sélectionné de manière aléatoire (par exemple, pour utiliser ce compte à des fins de test), l'applet de commande **Get-CsOnlineUser** d'appel et définissez le paramètre _ResultSize_ sur 1.
  
```
Get-CsOnlineUser -ResultSize 1
```

L'applet de commande **Get-CsOnlineUser** renvoyer des informations pour un seul utilisateur, quel que soit le nombre d'utilisateurs que vous avez dans votre organisation à l'origine. Pour renvoyer des informations pour les cinq utilisateurs, définissez la valeur du paramètre _ResultSize_ 5.
  
```
Get-CsOnlineUser -ResultSize 5
```

### Renvoyer des informations pour un utilisateur spécifique dans Skype entreprise Online
<a name="BKMK_ReturnInfoSpecificUser"> </a>

Il existe plusieurs moyens de référence à un compte d'utilisateur spécifique lors de l'appel de l'applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) . Vous pouvez utiliser le nom d'affichage de l'utilisateur services de domaine Active Directory.
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

Vous pouvez utiliser l'adresse SIP de l'utilisateur.
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

Vous pouvez utiliser le nom principal d'utilisateur de l'utilisateur (UPN).
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### Renvoyer des informations spécifiques pour des utilisateurs spécifiques dans Skype entreprise Online
<a name="BKMK_ReturninfoSpecificUsers"> </a>

Par défaut, l'applet de commande [Get-CsOnlineUser](https://support.office.com/article/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) renvoie une grande quantité d'informations pour chaque compte d'utilisateur Skype Entreprise Online. Si vous êtes intéressé uniquement un sous-ensemble de ces informations, canal les données renvoyées à l'applet de commande **Select-Object**. Par exemple, cette commande renvoie toutes les données de l'utilisateur Ken Myer, puis utilise l'applet de commande **Select-Object** pour limiter les données affichée à l'écran pour nom d'affichage de Ken AD DS et plan de numérotation.
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

La commande suivante renvoie le nom d'affichage et d'accès à planifier pour tous vos utilisateurs.
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

Pour rechercher les propriétés d'un compte d'utilisateur Skype Entreprise Online, utilisez la commande suivante.
  
```
Get-CsOnlineUser | Get-Member
```

### Renvoyer une liste filtrée des utilisateurs dans Skype entreprise Online
<a name="BKMK_ReturnFilteredListofUsers"> </a>

En utilisant l'applet de commande [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) et les paramètres _LdapFilter_ ou _Filter_, vous pouvez facilement renvoyer des informations sur un ensemble ciblé d'utilisateurs. Par exemple, cette commande renvoie tous les utilisateurs qui travaillent dans le service Finances.
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

