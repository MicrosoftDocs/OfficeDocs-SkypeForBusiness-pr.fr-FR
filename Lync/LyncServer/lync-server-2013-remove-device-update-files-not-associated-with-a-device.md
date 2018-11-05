---
title: "Supp. fichiers de màj de périph. plus associés à aucun périphérique"
TOCtitle: "Supp. fichiers de màj de périph. plus associés à aucun périphérique"
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994084(v=OCS.15)
ms:contentKeyID: 53095557
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer les fichiers de mise à jour de périphériques qui ne sont pas plus associés à aucun périphérique

 

_**Dernière rubrique modifiée :** 2013-02-20_

Dès que de nouvelles mises à jour des périphériques sont téléchargées sur le système, une règle de mise correspondante est créée. Par défaut, ces nouvelles règles de mise à jour de périphériques ont l’état En attente. Cela signifie que les règles peuvent être téléchargées et installés sur des périphériques de test, mais pas sur des périphériques de production, ce qui vous permet de tester les mises à jour avant de les rendre disponibles aux utilisateurs. En fonction de ces tests, vous acceptez et déployez ou rejetez et supprimez la mise à jour. Quand vous rejetez une mise à jour, la mise à jour du périphérique est dissociée de sa règle de mise à jour de périphérique


Les fichiers de mise à jour de périphérique qui ne sont plus associés à un périphérique peuvent être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Clear-CsDeviceUpdateFile**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.


  - Par exemple, la commande suivante supprime les règles de mise à jour des périphériques sur le serveur web atl-cs-001.litwareinc.com qui ne sont plus associées à un périphérique :
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateFile).

