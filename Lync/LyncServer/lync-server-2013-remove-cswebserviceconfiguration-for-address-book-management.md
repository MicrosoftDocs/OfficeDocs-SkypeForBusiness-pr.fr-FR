---
title: Remove-CsWebServiceConfiguration pour la gestion des carnets d’adresses
TOCTitle: Remove-CsWebServiceConfiguration pour la gestion des carnets d’adresses
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429713(v=OCS.15)
ms:contentKeyID: 49298086
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsWebServiceConfiguration pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande Remove-CsWebServiceConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

L’applet de commande Remove-CsWebServiceConfiguration permet à un administrateur de supprimer une configuration des services web créée précédemment. L’applet de commande ne peut pas supprimer la configuration globale des services web.

Par exemple :

    Remove-CsWebServiceConfiguration -Identity site:Redmond

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)

