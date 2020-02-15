---
title: 'Lync Server 2013 : modifier les paramètres des fichiers journaux de mise à jour des périphériques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770682cfed17d9b029688275469351c1cfdf9f4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modifier les paramètres des fichiers journaux de mise à jour des périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez modifier les paramètres relatifs à la journalisation des informations de mise à jour des périphériques dans votre organisation à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell. Le tableau suivant indique les paramètres modifiables et les outils que vous utilisez pour modifier les paramètres.

Les paramètres de journal peuvent être modifiés et appliqués globalement, ou par site.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pour modifier</th>
<th>Utilisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taille maximale (en octets) d’un fichier journal</p></td>
<td><p>Panneau de commande Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Quantité maximale d’informations (en octets) pouvant être conservées dans le cache</p></td>
<td><p>Panneau de commande Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Fréquence (en minutes) d’écriture des informations mises en cache dans le fichier journal</p></td>
<td><p>Panneau de commande Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Durée (en jours) pendant laquelle les fichiers journaux sont conservés</p></td>
<td><p>Panneau de commande Lync Server</p>
<p>- ou -</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Lorsque (heure de la journée) pour vérifier les fichiers expirés qui doivent être supprimés</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Les extensions de fichiers journaux à autoriser</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Types de fichiers journaux à conserver</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Pour modifier les paramètres de journalisation à l’aide du panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur **configuration du journal du périphérique**.

3.  Sur la page **configuration du journal du périphérique** , double-cliquez sur la configuration que vous souhaitez modifier.

4.  Dans la boîte de dialogue **modifier le paramètre du journal** , modifiez l’un des paramètres suivants :
    
      - **Taille maximale du fichier (octets)**   indique la taille maximale qu’un fichier journal peut prendre avant d’être purgé. La valeur par défaut est 1 024 000 octets (1 Mo).
    
      - **Taille maximale du cache (octets)**   spécifie la quantité maximale d’informations (en octets) pouvant être conservées dans le cache du fichier journal avant que ce cache ne soit effacé et que les données soient écrites dans un fichier journal. La valeur par défaut est 512 000 octets (0,5 Mo).
    
      - **Le nombre de minutes de vidage du cache (1-60)**   indique la fréquence à laquelle les informations stockées dans le cache du fichier journal sont écrites dans le fichier journal réel. Une fois que les données sont journalisées, le cache est effacé. La valeur par défaut est de cinq minutes.
    
      - **Nombre de jours de conservation des fichiers journaux (1-365)**   indique le nombre de jours pendant lesquels les fichiers journaux sont conservés avant d’être purgés. La valeur par défaut est 10 jours.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Modification des paramètres de journalisation à l’aide des applets de commande Windows PowerShell

Les paramètres du fichier journal de mise à jour des appareils peuvent être modifiés à l’aide de Windows PowerShell et de l’applet de commande **Set-CsDeviceUpdateConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.



</div>

Les exemples suivants illustrent deux façons d’utiliser **Set-CsDeviceUpdateConfiguration** pour modifier les paramètres.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Pour modifier la taille maximale du fichier journal et l’intervalle de nettoyage des journaux

  - La commande suivante modifie les paramètres du journal de mise à jour des appareils appliqués au site Redmond. Dans cet exemple, la taille maximale du fichier journal est fixée à 204800 octets et l’intervalle de nettoyage du journal est de 14 jours.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Pour modifier l’heure de nettoyage du journal de jour

  - Cette commande définit le temps de nettoyage du journal pour le site de Redmond sur 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

