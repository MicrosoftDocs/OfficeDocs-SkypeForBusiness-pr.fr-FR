---
title: New-CsClientPolicy pour la gestion du carnet d’adresses
TOCTitle: New-CsClientPolicy pour la gestion du carnet d’adresses
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429726(v=OCS.15)
ms:contentKeyID: 49299261
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsClientPolicy pour la gestion du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette cmdlet : par défaut, les membres des groupes suivants sont autorisés à exécuter localement la cmdlet New-CsClientPolicy : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette cmdlet a été attribuée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

La cmdlet New-CsClientPolicy définit un grand nombre de paramètres pour fournir aux clients des fonctions disponibles dans Lync Server 2013. Pour le service de carnet d’adresses, le paramètre AddressBookAvailability est intéressant. Ce paramètre, qui a un impact direct sur les options proposées aux clients, compte trois options possibles :

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

Une fois défini, il détermine comment les clients ont accès au carnet d’adresses. Si vous définissez ce paramètre, vous devez définir une des options. Si vous ne modifiez pas ce paramètre, la valeur par défaut WebSearchAndFileDownload reste en vigueur.

Par exemple :

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

## Voir aussi

#### Autres ressources

[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)

