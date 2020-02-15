---
title: 'Lync Server 2013 : suppression des fichiers journaux de mise à jour des périphériques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f5b8ed6d087bb7b80ba93aead7c3ab530c82000
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Supprimer les fichiers journaux de mise à jour des périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Le service Web de mise à jour des périphériques conserve une collection complète de fichiers journaux. Cette collection comprend les deux journaux d’audit effectués par le service lui-même et les fichiers journaux téléchargés à partir des appareils clients. Pour empêcher le serveur de saturer les journaux du service Web de mise à jour des périphériques, vous souhaiterez probablement l’effacer des fichiers journaux qui ont été mis en place pendant un certain nombre de jours. Définissez ce nombre de jours en fonction de l’activité de mise à jour et du nombre d’appareils clients au sein de votre organisation, et à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Pour effacer le journal de mise à jour des périphériques à l’aide du panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur **configuration du journal du périphérique**.

3.  Sur la page **configuration du journal du périphérique** , double-cliquez sur la configuration que vous souhaitez modifier.

4.  Dans la boîte de dialogue **modifier le paramètre du journal** , en **nombre de jours de conservation des fichiers journaux (1-365)**, spécifiez un nombre de jours.

5.  Cliquez sur **Valider**. Tous les fichiers qui se trouvent sur le serveur pendant une durée supérieure au nombre de jours spécifié sont supprimés. Ce paramètre s’applique à cette configuration jusqu’à ce que vous le modifiiez.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Effacement du journal de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell

Vous pouvez effacer les journaux de mise à jour des périphériques à l’aide de Windows PowerShell et de l’applet **de commande Clear-CsDeviceUpdateLog** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Pour effacer les journaux de mise à jour des appareils sur un serveur

  - La commande suivante efface le journal de mise à jour des périphériques sur le serveur Web atl-cs-001.litwareinc.com. Toutes les entrées de journal datant de plus de 10 jours (la valeur spécifiée par le paramètre DaysBack) seront supprimées du journal.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Pour effacer tous les journaux de mise à jour des appareils

  - Cette commande supprime les entrées obsolètes (dans cet exemple, entrées plus de 10 jours) de tous les journaux de mise à jour des appareils actuellement utilisés dans votre organisation.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

