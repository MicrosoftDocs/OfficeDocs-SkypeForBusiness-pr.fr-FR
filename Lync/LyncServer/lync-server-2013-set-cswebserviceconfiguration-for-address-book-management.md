---
title: Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses
TOCTitle: Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429709(v=OCS.15)
ms:contentKeyID: 49297804
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande Set-CsWebServiceConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

L’applet de commande Set-CsWebServiceConfiguration permet à l’administrateur de redéfinir un attribut existant dans la configuration des services web.

Par exemple :

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

