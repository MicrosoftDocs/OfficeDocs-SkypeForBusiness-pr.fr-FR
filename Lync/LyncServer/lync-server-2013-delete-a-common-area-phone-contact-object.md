---
title: Supprimer un objet contact téléphonique de partie commune
TOCTitle: Supprimer un objet contact téléphonique de partie commune
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994087(v=OCS.15)
ms:contentKeyID: 53095569
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer un objet contact téléphonique de partie commune

 

_**Dernière rubrique modifiée :** 2013-02-20_

Il vous arrivera parfois de vouloir supprimer l’objet contact associé à un téléphone de partie commune. Par exemple, si vous supprimez le téléphone dans un espace réservé aux employés, il n’est pas utile qu’un objet contact soit associé à ce téléphone. L’applet de commande **Remove-CsCommonAreaPhone** vous offre un moyen de supprimer les comptes de téléphone de partie commune. Lorsque vous exécutez cette applet de commande, le téléphone sera supprimé de la liste des téléphones de partie commune retournée par **Get-CsCommonAreaPhone**. En outre, l’objet contact associé avec ce téléphone sera supprimé des services de domaine Active Directory.

Utilisez **Remove-CsCommonAreaPhone** pour supprimer un téléphone de partie commune ou tous les téléphones de partie commune qui ont un élément commun, par exemple un nom d’affichage ou un code de pays ou un indicatif. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une sessions à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Suppression d’un téléphone de partie commune spécifique

  - La commande suivante supprime le téléphone de partie commune avec l’adresse SIP sip:mainlobby@litwareinc.com :
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

## Suppression de téléphones de partie commune en fonction de leur nom d’affichage

  - Cette commande supprime tous les téléphones de partie commune quand leur nom d’affichage comporte la chaîne « Building 14 » :
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

## Suppression de téléphones de partie commune en fonction des codes de pays ou d’indicatif

  - Cette commande supprime tous les téléphones de partie commune pour les États-Unis (code de pays 1) et l’indicatif 425 :
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCommonAreaPhone).

## Voir aussi

#### Autres ressources

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

