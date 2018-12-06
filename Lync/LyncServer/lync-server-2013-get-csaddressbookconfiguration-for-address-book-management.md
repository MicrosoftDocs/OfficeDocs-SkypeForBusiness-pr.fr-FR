---
title: Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses
TOCTitle: Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429721(v=OCS.15)
ms:contentKeyID: 49298697
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande Get-CsAddressBookConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

L’applet de commande Get-CsAddressBookConfiguration retourne des informations sur une configuration qui existe déjà.

Par exemple :

    Get-CsAddressBookConfiguration -Identity site:Redmond

L’association fonctionnelle des applets de commande Get-CsAddressBookConfiguration et Set-CsAddressBookConfiguration permet à l’administrateur de définir les configurations à modifier, puis d’apporter les modifications. Par exemple, la combinaison suivante :

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Retourne toutes les configurations dans tous les sites et applique la propriété RunTimeOfDay définie sur 23:00 aux configurations.

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Get-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAddressBookConfiguration)

