---
title: Remove-CsAddressBookConfiguration pour la gestion du carnet d’adresses
TOCTitle: Remove-CsAddressBookConfiguration pour la gestion du carnet d’adresses
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429705(v=OCS.15)
ms:contentKeyID: 49297347
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsAddressBookConfiguration pour la gestion du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Remove-CsAddressBookConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

Comme son nom l’indique, Remove-CsAddressBookConfiguration supprimera la configuration basée sur l’identité de site définie.

Par exemple :

    Remove-CsAddressBookConfiguration -Identity site:Redmond

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Remove-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAddressBookConfiguration)

