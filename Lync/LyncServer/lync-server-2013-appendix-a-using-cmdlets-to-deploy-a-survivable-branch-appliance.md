---
title: 'Lync Server 2013 : Annexe A : Utilisation d’applets de commande pour déployer un Survivable Branch Appliance'
TOCTitle: 'Annexe A : Utilisation d’applets de commande pour déployer un Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398598(v=OCS.15)
ms:contentKeyID: 49297797
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Annexe A : Utilisation d’applets de commande pour déployer un Survivable Branch Appliance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-07_

Cette rubrique explique comment déployer un Survivable Branch Appliance à l’aide de Lync Server Management Shell. Cette procédure doit être effectuée sur le site central.

## Pour déployer un Survivable Branch Appliance à distance

1.  Suivez la procédure indiquée dans [Ajout des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) pour ajouter un nouveau site de succursale.

2.  Joignez le site de succursale.

3.  Ajoutez le groupe RTCUniversalSBATechnicians au groupe Administrateurs local.

4.  Redémarrez le serveur et ouvrez une session dessus en tant que membre du groupe RTCUniversalSBATechnicians.

5.  Dans Lync Server Management Shell, tapez les commandes suivantes en remplaçant les espaces réservés par les informations appropriées à votre organisation :
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

