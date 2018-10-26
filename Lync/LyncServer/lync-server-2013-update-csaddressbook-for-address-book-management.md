---
title: Update-CsAddressBook pour la gestion des carnets d’adresses
TOCTitle: Update-CsAddressBook pour la gestion des carnets d’adresses
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429695(v=OCS.15)
ms:contentKeyID: 49296275
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Update-CsAddressBook pour la gestion des carnets d’adresses

 

_**Dernière rubrique modifiée :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Update-CsAddressBook : RTCUniversalUserAdmins, RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

L’applet de commande Update-CsAddressBook remplace la commande **abserver.exe –syncNow** d’Office Communications Server. Cette applet de commande sert à lancer une synchronisation immédiatement au lieu d’attendre qu’elle s’effectue à l’heure initialement prévue. Dans le premier exemple, la commande met à jour tous les carnets d’adresses dans l’organisation. Dans le second exemple, elle met uniquement à jour le carnet d’adresses associé au serveur défini.

> [!NOTE]  
> Dans Lync Server 2013, le réplicateur d’utilisateurs Lync Server sélectionne les modifications dans Active Directory et met à jour la base de données d’utilisateurs Lync Server en fonction de l’intervalle configuré. Le réplicateur d’utilisateurs Lync Server propage par ailleurs rapidement les modifications dans la base de données RTCab sans que l’administrateur n’ait à exécuter Update-CSAddressBook. L’administrateur doit simplement exécuter Update -CSAddressBook si le téléchargement des fichiers du Carnet d’adresses est activé.

Par exemple :

```
Update-CsAddressBook
```
```
Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
```

Pour une description détaillée de la commande complète, reportez-vous aux ressources suivantes dans la référence principale des RTCCmdlets Windows PowerShell pour Lync Server.

## Voir aussi

#### Autres ressources

[Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook)

