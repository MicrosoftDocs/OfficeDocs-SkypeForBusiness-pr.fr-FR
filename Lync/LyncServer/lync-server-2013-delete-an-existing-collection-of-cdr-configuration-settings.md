---
title: "Supp. d’une coll. existante de par. de conf. de l’enr. des détails des appels"
TOCtitle: "Supp. d’une coll. existante de par. de conf. de l’enr. des détails des appels"
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49891440
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une collection existante de paramètres de configuration de l’enregistrement des détails des appels

 

_**Dernière rubrique modifiée :** 2013-02-23_

L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.

Quand vous installez Microsoft Lync Server 2013, une unique collection globale de paramètres de configuration CDR est automatiquement créée. Les administrateurs peuvent également créer des collections de paramètres personnalisées qui peuvent être appliquées à des sites spécifiques. Par défaut, les paramètres configurés au niveau du site ont priorité sur les paramètres configurés au niveau global. Si vous supprimez les paramètres au niveau du site, l’enregistrement des détails des appels sera géré dans ce site à l’aide des paramètres globaux.

Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, le vidage est, par défaut, activé dans une collection de paramètres de configuration CDR. Si vous modifiez la collection globale afin que le vidage soit désactivé, et que vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que le vidage sera de nouveau activé.

Vous pouvez supprimer les paramètres de configuration CDR à l’aide du Panneau de configuration Lync Server ou de l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration).

## Pour supprimer les paramètres de configuration CDR avec le Panneau de configuration Lync Server

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Surveillance et archivage**.

2.  Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.

3.  Cliquez sur **Modifier**, puis sur **Supprimer**.

4.  Dans la boîte de dialogue Panneau de configuration Lync Server, cliquez sur **OK**.

## Pour supprimer les paramètres de configuration CDR avec les applets de commande Lync Server Management Shell

Vous pouvez supprimer les paramètres de configuration d’enregistrement des détails des appels avec Windows PowerShell et l’applet de commande **Remove-CsCdrConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une collection spécifique de paramètres de configuration CDR

  - Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

## Pour supprimer tous les paramètres de configuration CDR appliqués au niveau du site

  - Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

## Pour supprimer tous les paramètres de configuration CDR qui désactivent l’enregistrement des détails des appels

  - Cette commande supprime tous les paramètres de configuration CDR pour lesquels l’enregistrement des détails des appels a été désactivé :
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration).

