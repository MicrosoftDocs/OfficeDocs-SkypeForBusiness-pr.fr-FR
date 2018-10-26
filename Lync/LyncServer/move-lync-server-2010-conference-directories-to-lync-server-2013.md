---
title: "Déplacement des annuaires de conf. Lync Server 2010 vers Lync Server 2013"
TOCTitle: Déplacement des annuaires de conférences
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62388688
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement des annuaires de conférences

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avant de désaffecter un pool, vous devez suivre la procédure ci-après pour chaque annuaire de conférences de votre pool Lync Server 2010.

## Pour déplacer un annuaire de conférences vers Lync Server 2013

1.  Ouvrez Lync Server Management Shell.

2.  Pour obtenir l’identité des annuaires de conférences de votre organisation, exécutez la commande suivante :
    
        Get-CsConferenceDirectory
    
    La command précédente renvoie tous les annuaires de conférences de votre organisation. Cest pourquoi vous souhaiterez peut-être limiter les résultats au pool en cours de désaffection. Par exemple, si vous désaffectez le pool avec le nom de domaine complet (FQDN) pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférences de ce pool:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Cette commande ne renvoie que les annuaires de conférences où la propriété ServiceID contient le FQDN pool01.contoso.net.

3.  Pour déplacer des annuaires de conférences, exécutez la commande suivante pour chaque annuaire de conférence du pool :
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Par exemple, pour déplacer l’annuaire de conférences 3, utilisez la commande suivante et indiquez un pool Lync Server 2013 en tant que TargetPool :
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Pour déplacer tous les annuaires de conférences d’un pool, utilisez une commande semblable à la syntaxe suivante :
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Reportez-vous au document «Désinstallation de Lync Server 2010 et suppression des rôles serveur » (téléchargeable depuis [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) pour obtenir des instructions pas à pas complètes sur la désaffection des pools Lync 2010.

Lorsque vous déplacez des annuaires de conférences, vous risquez de recevoir le message d’erreur suivant :

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

En général, ce message d’erreur s’affiche lorsque le Lync Server Management Shell exige des autorisations Active Directory mises à jour afin de réaliser une opération. Pour résoudre ce problème, fermez l’instance active de Management Shell, ouvrez une nouvelle instance du shell, puis réexécutez la commande pour déplacer l’annuaire de conférences.

