---
title: "Supp. une coll. de param. de conf. de la mise à jour des périphériques"
TOCtitle: "Supp. une coll. de param. de conf. de la mise à jour des périphériques"
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994019(v=OCS.15)
ms:contentKeyID: 53095369
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une collection de paramètres de configuration de la mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-20_

Il est également possible de supprimer les paramètres de configuration de mise à jour des périphériques à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsdeviceUpdateConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Pour supprimer une collection spécifique de paramètres de configuration de mise à jour des périphériques

  - Cette commande permet de supprimer les paramètres de configuration de mise à jour des périphériques appliqués au site Redmond :
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

## Pour supprimer tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue Site

  - Cette commande permet de supprimer tous les paramètres de configuration de mise à jour des périphériques appliqués au niveau du site :
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

## Pour supprimer des paramètres de configuration de mise à jour des périphériques en fonction de la valeur de la propriété LogCleanUpInterval

  - La commande suivante supprime tous les paramètres de configuration de mise à jour des périphériques dont l’intervalle de nettoyage du journal est supérieur à 10 jours (10.00:00:00) :
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateConfiguration).

