---
title: Test-CsAddressBookWebQuery pour la gestion des carnets d’adresses
TOCTitle: Test-CsAddressBookWebQuery pour la gestion des carnets d’adresses
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429716(v=OCS.15)
ms:contentKeyID: 49298180
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookWebQuery pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : par défaut, les membres des groupes qui suivent sont autorisés à exécuter l’applet de commande Test-CsAddressBookWebQuery : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Similaire à la transaction synthétique Test-CsAddressBookService, l’applet de commande Test-CsAddressBookWebQuery lance une requête au service Address Book Web Query pour vérifier son fonctionnement correct. L’applet de commande se connecte au service d’authentification de ticket web et soumet les informations d’identification spécifiées dans –UserCredential. En cas d’authentification, l’applet de commande présente ensuite les informations –TargetSipAddress. L’applet de commande réussit si elle a pu récupérer les informations sur le contact.

Par exemple :

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Test-CsAddressBookWebQuery](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookWebQuery)

