---
title: 'Lync Server 2013: supprimer les fichiers journaux de mise à jour de l’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Supprimer des fichiers journaux de mise à jour de périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Le service Web de mise à jour des appareils conserve une collection complète de fichiers journaux. Cette collection inclut les journaux d’audit effectués par le service proprement dit, ainsi que les fichiers journaux téléchargés à partir des appareils clients. Pour empêcher le serveur de saturer les journaux de service Web de mise à jour de l’appareil, vous souhaiterez probablement effacer les fichiers journaux qui se trouvent dans un certain nombre de jours. Définissez le nombre de jours en fonction de l’activité de mise à jour et du nombre d’appareils clients au sein de votre organisation, et à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Pour vider le journal des mises à jour de l’appareil à l’aide du panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur **configuration du journal de périphériques**.

3.  Dans la page **configuration du journal des appareils** , double-cliquez sur la configuration que vous voulez modifier.

4.  Dans la boîte de dialogue **modifier les paramètres du journal** , en **nombre de jours pour conserver les fichiers journaux (1-365)**, spécifiez un nombre de jours.

5.  Cliquez sur **Valider**. Tous les fichiers qui se trouvent sur le serveur pour plus d’informations sur le nombre de jours spécifié sont supprimés. Ce paramètre sera appliqué à cette configuration tant que vous ne la modifiez pas.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Effacement du journal de mise à jour de l’appareil à l’aide des cmdlets Windows PowerShell

Vous pouvez effacer les journaux de mise à jour de l’appareil à l’aide de Windows PowerShell et de l’applet **de connexion Clear-CsDeviceUpdateLog** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Pour effacer les journaux de mise à jour de l’appareil sur un serveur

  - La commande suivante efface le journal de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com. Toutes les entrées du journal de plus de 10 jours (la valeur spécifiée par le paramètre DaysBack) sera supprimée du journal.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Pour effacer tous les journaux de mise à jour de l’appareil

  - Cette commande supprime les entrées obsolètes (dans cet exemple, les entrées de plus de 10 jours) de tous les journaux de mise à jour d’appareils actuellement utilisés au sein de votre organisation.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

