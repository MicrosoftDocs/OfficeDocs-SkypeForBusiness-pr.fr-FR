---
title: Test-CsAddressBookService pour la gestion des carnets d’adresses
TOCTitle: Test-CsAddressBookService pour la gestion des carnets d’adresses
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429720(v=OCS.15)
ms:contentKeyID: 49298649
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAddressBookService pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter l’applet de commande Test-CsAddressBookService : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 contient de nombreuses applets de commande qui permettent d’exécuter des commandes synthétiques dans le but de vérifier si une fonctionnalité ou une fonction précise fonctionne comme il se doit. Test-CsAddressBookService confirme qu’un utilisateur défini peut se connecter et demander les fichiers locaux au service web du carnet d’adresses.

Par exemple :

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

## Voir aussi

#### Autres ressources

[Test-CsAddressBookService](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookService)

