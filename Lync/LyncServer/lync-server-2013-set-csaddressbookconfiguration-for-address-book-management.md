---
title: Set-CsAddressBookConfiguration pour la gestion des carnets d’adresses
TOCTitle: Set-CsAddressBookConfiguration pour la gestion des carnets d’adresses
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429700(v=OCS.15)
ms:contentKeyID: 49296930
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAddressBookConfiguration pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Set-CsAddressBookConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

Set-CsAddressBookConfiguration est similaire à l’applet de commande New-CsAddressBookConfiguration, à la seule différence qu’elle sert à modifier une configuration existante.

Par exemple :

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Set-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAddressBookConfiguration)

