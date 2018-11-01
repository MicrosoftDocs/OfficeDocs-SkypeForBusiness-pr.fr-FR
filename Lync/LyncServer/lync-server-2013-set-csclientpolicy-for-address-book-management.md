---
title: Set-CsClientPolicy pour la gestion du carnet d’adresses
TOCTitle: Set-CsClientPolicy pour la gestion du carnet d’adresses
ms:assetid: e7788bea-606f-481a-a3a4-1855ac028493
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429723(v=OCS.15)
ms:contentKeyID: 49299173
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientPolicy pour la gestion du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette cmdlet : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement la cmdlet Set-CsClientPolicy : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette cmdlet a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClientPolicy"}

Comme la cmdlet New-CsClientPolicy, la cmdlet Set-CsClientPolicy vous permet de modifier les paramètres du client déjà en place.

Par exemple :

    Set-CsClientPolicy -Identity RedmondClientPolicy -WebServicePollInterval "00:15:00" -AddressBookAvailability "WebSearchAndFileDownload"

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy)

