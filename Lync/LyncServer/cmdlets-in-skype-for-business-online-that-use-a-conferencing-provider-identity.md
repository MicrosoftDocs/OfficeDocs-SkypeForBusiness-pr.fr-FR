---
title: Applets de commande utilisant une identité de fournisseur de services de conférence
TOCTitle: Applets de commande utilisant une identité de fournisseur de services de conférence
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56269647
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Applets de commande utilisant une identité de fournisseur de services de conférence

 

_**Dernière rubrique modifiée :** 2015-06-22_

Pour retourner des informations sur tous les fournisseurs de services d’audioconférence avec lesquels votre organisation a mis en place des contrats, vous pouvez simplement appeler l’applet de commande [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider) sans paramètre :

    Get-CsAudioConferencingProvider

Si vous voulez limiter les données retournées à un seul fournisseur (dans cet exemple, le fournisseur Services audio Contoso), utilisez le paramètre Identity :

    Get-CsAudioConferencingProvider -Identity "Services audio Contoso"

Seule une applet de commande Skype Entreprise Online accepte un ID de fournisseur de services d’audioconférence :

  - [Get-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsAudioConferencingProvider)

## Voir aussi

#### Concepts

[Identités, étendues et clients](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

