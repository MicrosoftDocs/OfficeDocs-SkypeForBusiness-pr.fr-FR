---
title: 'Lync Server 2013 : suppression d’une collection existante de paramètres de configuration CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77abb8ff4d50ec19b5d689193f909b0ddc4a475e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration CDR dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.

Lorsque vous installez Microsoft Lync Server 2013, une seule collection globale de paramètres de configuration CDR est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par défaut, les paramètres configurés au niveau du site ont priorité sur les paramètres configurés au niveau global. Si vous supprimez les paramètres au niveau du site, l’enregistrement des détails des appels sera géré dans ce site à l’aide des paramètres globaux.

Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, le vidage est, par défaut, activé dans une collection de paramètres de configuration CDR. Si vous modifiez la collection globale afin que le vidage soit désactivé, et que vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que le vidage sera de nouveau activé.

Vous pouvez supprimer les paramètres de configuration CDR à l’aide du panneau de configuration Lync Server ou de la cmdlet [Remove-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Pour supprimer les paramètres de configuration CDR avec le panneau de configuration Lync Server

1.  Dans le panneau de configuration Lync Server, cliquez sur **surveillance et archivage**.

2.  Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.

3.  Cliquez sur **Modifier**, puis sur **Supprimer**.

4.  Dans la boîte de dialogue Lync Server, panneau de configuration, cliquez sur **OK**.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration CDR à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration de l’enregistrement des détails des appels à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet cscdrconfiguration** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Pour supprimer une collection spécifique de paramètres de configuration CDR

  - Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration CDR appliqués à l’étendue site

  - Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Pour supprimer tous les paramètres de configuration CDR qui désactivent l’enregistrement des détails des appels

  - Cette commande supprime tous les paramètres de configuration CDR pour lesquels l’enregistrement des détails des appels a été désactivé :
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

