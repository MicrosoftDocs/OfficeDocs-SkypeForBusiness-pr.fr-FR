---
title: "Gérer Skype pour les organisations entreprise Online à l'aide de la Skype pour Business Connector en ligne"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
description: "Use Windows PowerShell and the Get-CsTenant and Get-CsTenantLicensingConfiguration cmdlets to get information about your Skype for Business Online tenant."
---

# Gérer Skype pour les organisations entreprise Online à l'aide de la Skype pour Business Connector en ligne

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a). 
  
Vous trouverez des informations à propos de votre client Skype Entreprise Online en utilisant les applets de commande **Get-CsTenant** et **Get-CsTenantLicensingConfiguration**.
  
## Gérer les Skype pour les clients entreprise Online

Pour renvoyer des informations sur votre client Skype Entreprise Online, appelez l'applet de commande [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) sans paramètres supplémentaires.
  
```
Get-CsTenant
```

Pour renvoyer simplement le client nom et l'ID, utilisez cette commande.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

La valeur du paramètre  _TenantID_ est nécessaire lors de l'exécution des applets de commande tels que[Définir CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) et[Jeu CsTenantFederationConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849602).
  
Pour rechercher des informations sur les informations relatives aux licences pour le client spécifié sont disponibles dans le centre d'administration Skype Entreprise Online, utilisez l'applet de commande [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

