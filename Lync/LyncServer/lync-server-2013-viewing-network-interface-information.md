---
title: Affichage des informations d’une interface réseau
TOCTitle: Affichage des informations d’une interface réseau
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49891584
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’une interface réseau

 

_**Dernière rubrique modifiée :** 2013-02-23_

## Affichage d’informations d’interface réseau à l’aide des cmdlets Lync Server Management Shell

Vous pouvez voir les informations d’interface réseau à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsNetworkInterface**. Vous pouvez exécuter cette cmdlet à partir du Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour voir les informations d’interface réseau

  - Pour voir les informations d’interface réseau, tapez la commande suivante dans le Lync Server Management Shell et appuyez sur Entrée :
    
        Get-CsNetworkInterface
    
    Cette commande renvoie des informations comme celles-ci pour chaque interface réseau :
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :

Pour plus d’informations, voir [Get-CsNetworkInterface](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterface) (contenu éventuellement en anglais).

