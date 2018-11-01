---
title: "Déplacer un disp. de conf. vers un nouveau pool de serveurs d’inscriptions"
TOCtitle: "Déplacer un disp. de conf. vers un nouveau pool de serveurs d’inscriptions"
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994025(v=OCS.15)
ms:contentKeyID: 53095384
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacer un dispositif de conférence vers un nouveau pool de serveurs d’inscriptions

 

_**Dernière rubrique modifiée :** 2013-02-20_

Déplacez un dispositif de conférence depuis un pool de serveurs d’inscriptions vers un autre à l’aide de l’applet de commande **Move-CsMeetingRoom**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.


## Déplacement d’un dispositif de conférence vers un nouveau pool de serveurs d’inscriptions

  - Pour déplacer un dispositif de conférence, vous devez spécifier l’identité de la salle à déplacer, puis définir le paramètre Target sur le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions vers lequel le dispositif sera déplacé. Exemple :
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Move-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsMeetingRoom).

