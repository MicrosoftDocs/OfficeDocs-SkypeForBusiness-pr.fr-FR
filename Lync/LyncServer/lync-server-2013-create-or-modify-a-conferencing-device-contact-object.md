---
title: Créer ou modifier un objet contact de dispositif de conférence
TOCTitle: Créer ou modifier un objet contact de dispositif de conférence
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994035(v=OCS.15)
ms:contentKeyID: 53095437
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer ou modifier un objet contact de dispositif de conférence

 

_**Dernière rubrique modifiée :** 2013-10-02_

Pour créer un objet de salle de conférence, commencez par créer un compte d’utilisateur Active Directory représentant le dispositif. Ensuite, utilisez l’applet de commande **Enable-CsMeetingRoom** pour activer ce compte afin qu’il fasse office de dispositif de conférence. Si vous devez modifier les propriétés d’un dispositif de conférence existant, utilisez l’applet de commande **Set-CsMeetingRoom**.

Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.


## Création d’un dispositif de conférence

  - Après avoir créé le compte d’utilisateur Active Directory représentant le nouveau dispositif de conférence, activez-le à l’aide de l’applet de commande **Enable-CsMeetingRoom**. Veillez à inclure a) l’identité du dispositif de conférence, b) le pool de serveurs d’inscriptions destiné à héberger le compte de la salle et c) l’adresse SIP à affecter à ce compte. Exemple :
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## Modification d’un dispositif de conférence

  - Pour modifier les valeurs des propriétés d’un dispositif de conférence existant, utilisez l’applet de commande **Set-CsMeetingRoom**. Par exemple, la commande suivante met à jour le numéro de téléphone (LineUri) associé à un dispositif de conférence :
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

Pour plus d’informations, recherchez les rubriques d’aide relatives aux applets de commande [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) et [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom).

