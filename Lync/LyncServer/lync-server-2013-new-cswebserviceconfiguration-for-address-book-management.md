---
title: New-CsWebServiceConfiguration pour la gestion du carnet d’adresses
TOCTitle: New-CsWebServiceConfiguration pour la gestion du carnet d’adresses
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429703(v=OCS.15)
ms:contentKeyID: 49297112
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsWebServiceConfiguration pour la gestion du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande New-CsWebServiceConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

L’applet de commande New-CsWebServiceConfiguration définit une nouvelle configuration pour les services web de votre organisation. L’étendue de la configuration des services web ne peut être qu’au niveau du site ou du service. Elle ne peut pas créer une nouvelle configuration des services web au niveau global. L’attribut EnableGroupExpansion est particulièrement intéressant pour le carnet d’adresses. S’il est défini sur True, les services web peuvent répondre aux demandes de développement de groupes.

Par exemple :

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[New-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsWebServiceConfiguration)

