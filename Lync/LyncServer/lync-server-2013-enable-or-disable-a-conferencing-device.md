---
title: Activer ou désactiver un périphérique de conférence
TOCTitle: Activer ou désactiver un périphérique de conférence
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994070(v=OCS.15)
ms:contentKeyID: 53095535
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activer ou désactiver un périphérique de conférence

 

_**Dernière rubrique modifiée :** 2013-02-20_

Vous pouvez activer et désactiver un périphérique de conférence à l’aide des applets de commande **Enable-CsMeetingRoom** et **Disable-CsMeetingRoom**. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.


## Activation d’un périphérique de conférence

  - Pour activer un périphérique de conférence, utilisez l’applet de commande **Enable-CsMeetingRoom**. Lors de l’activation d’un périphérique de conférence, vous devez inclure a) l’identité du périphérique de conférence, b) le pool de serveurs d’inscription où sera hébergé le compte de la salle et c) l’adresse SIP à assigner à ce compte.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Désactivation d’un périphérique de conférence

  - Pour désactiver un périphérique de conférence, utilisez l’applet de commande **Disable-CsMeetingRoom**. Assurez-vous de spécifier l’identité du périphérique de conférence à désactiver :
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

Pour plus d’informations, voir les applets de commande New-CsNetworkSubnet et [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom) dans la documentation [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom).

