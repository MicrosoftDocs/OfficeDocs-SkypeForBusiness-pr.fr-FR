---
title: Get-CsWebServiceConfiguration pour la gestion des carnets d’adresses
TOCTitle: Get-CsWebServiceConfiguration pour la gestion des carnets d’adresses
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429692(v=OCS.15)
ms:contentKeyID: 49296206
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsWebServiceConfiguration pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Get-CsWebServiceConfiguration : RTCUniversalUserAdmins, RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

Get-CsWebServiceConfiguration retourne les informations de la configuration des services web actuellement appliquée dans votre organisation. Ce qui est important pour les services de carnet d’adresses est l’état de la fonction Distribution List Expansion. Si la valeur de l’attribut EnableGroupExpansion est True, votre organisation autorise le développement des groupes.

Par exemple :

    Get-CsWebServiceConfiguration -Identity site:Redmond

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Get-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWebServiceConfiguration)

