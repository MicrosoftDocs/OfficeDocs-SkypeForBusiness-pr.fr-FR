---
title: New-CsAddressBookConfiguration pour la gestion du carnet d’adresses
TOCTitle: New-CsAddressBookConfiguration pour la gestion du carnet d’adresses
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429718(v=OCS.15)
ms:contentKeyID: 49298413
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAddressBookConfiguration pour la gestion du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande New-CsAddressBookConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

L’applet de commande New-CsAddressBookConfiguration crée une nouvelle configuration pour gérer le comportement du carnet d’adresses. Cette applet de commande est caractérisée par son aptitude à définir si le service de carnet d’adresses crée les fichiers à télécharger du client, comment et si des règles de normalisation sont utilisées, combien de temps retenir les fichiers delta et delta compacts, la taille des fichiers delta avant l’incorporation d’un nouveau fichier complet créé, l’heure de la journée à laquelle le fichier complet carnet d’adresses est créé et ce que devrait être l’interne pour synchroniser les informations dans la base de données utilisateur.

Par exemple :

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[New-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAddressBookConfiguration)

