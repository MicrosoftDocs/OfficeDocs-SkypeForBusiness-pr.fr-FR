---
title: Déplacement des annuaires de conférences
TOCTitle: Déplacement des annuaires de conférences
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204994(v=OCS.15)
ms:contentKeyID: 49297658
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement des annuaires de conférences

 

_**Dernière rubrique modifiée :** 2012-10-04_

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférence dans votre pool Office Communications Server 2007 R2.

## Pour déplacer un annuaire des conférences vers Lync Server 2013

1.  Ouvrez Lync Server Management Shell.

2.  Pour obtenir l’identité des annuaires de conférence dans votre organisation, exécutez les commandes suivantes :
    
        Get-CsConferenceDirectory
    
    Étant donné que l’applet de commande renvoie tous les annuaires des conférences dans votre organisation, vous pouvez limiter les résultats au seul pool que vous voulez désaffecter. Par exemple, si vous souhaitez désaffecter un pool avec le nom de domaine complet (FQDN) pool01.contoso.net :
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Cette applet de commande renvoie tous les annuaires des conférences où l’ID de service contient le FQDN pool01.contoso.net.

3.  Pour déplacer les annuaires des conférences, exécutez ce qui suit pour chaque annuaire des conférences dans le pool :
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Exemple :
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

> [!NOTE]  
> Vous risquez de rencontrer une erreur, illustrée ci-dessous, due au fait que Lync Server Management Shell requiert un ensemble mis à jour d’autorisations provenant d’Active Directory. Pour résoudre cette erreur, fermez la fenêtre actuelle, ouvrez de nouveau Lync Server Management Shell et réexécutez la commande.

![Sortie d’erreur Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Sortie d’erreur Move-CsConferenceDirectory")

