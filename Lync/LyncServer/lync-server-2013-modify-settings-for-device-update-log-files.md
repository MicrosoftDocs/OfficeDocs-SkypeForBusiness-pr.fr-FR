---
title: 'Lync Server 2013 : modifier les paramètres des fichiers journaux de mise à jour de l’appareil'
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
ms.openlocfilehash: 88d75086f0532205c2897f7e86d49f50072aaa89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modifier les paramètres des fichiers journaux de mise à jour de l’appareil dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez modifier les paramètres d’enregistrement des informations de mise à jour de l’appareil dans votre organisation à l’aide du panneau de configuration de Lync Server ou de Lync Server Management Shell. Le tableau suivant indique quels paramètres peuvent être modifiés et quels outils vous utilisez pour modifier les paramètres.

Les paramètres du journal peuvent être modifiés et appliqués globalement ou par site.


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
<td><p>Taille maximale (en octets) pour un fichier journal</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>ou</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Le volume maximal d’informations (en octets) pouvant être tenu dans le cache</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>ou</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Intervalle de temps (en minutes) pour écrire les informations mises en cache dans le fichier journal</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>ou</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Durée (en jours) de conservation des fichiers journaux</p></td>
<td><p>Panneau de configuration Lync Server</p>
<p>ou</p>
<p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Lorsque (heure de la journée) pour vérifier les fichiers expirés qui doivent être supprimés</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="even">
<td><p>Extensions de fichier journal à autoriser</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
<tr class="odd">
<td><p>Types de fichiers journaux à conserver</p></td>
<td><p>Lync Server Management Shell</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Pour modifier les paramètres de journalisation en utilisant le panneau de configuration de Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur **configuration du journal de périphériques**.

3.  Dans la page **configuration du journal des appareils** , double-cliquez sur la configuration que vous voulez modifier.

4.  Dans la boîte de dialogue **modifier les paramètres du journal** , modifiez les paramètres suivants :
    
      - **Taille maximale du fichier (octets)**   spécifie la taille maximale qu’un fichier journal peut prendre avant qu’il soit purgé. La valeur par défaut est 1 024 000 octets (1 Mo).
    
      - **Taille maximale du cache (octets)**   spécifie le volume maximal d’informations (en octets) qui peuvent être maintenues dans le cache du fichier journal avant que ce cache ne soit supprimé et les données soient écrites dans un fichier journal. La valeur par défaut est 512 000 octets (0,5 Mo).
    
      - **Nombre de minutes pour vider le cache (1-60)**   indique la fréquence à laquelle les informations stockées dans le cache du fichier journal sont écrites dans le fichier journal réel. Lorsque les données sont enregistrées, le cache est vidé. La valeur par défaut est 5 minutes.
    
      - **Nombre de jours de conservation des fichiers journaux (1-365)**   spécifie le nombre de jours pendant lequel les fichiers journaux sont conservés avant d’être supprimés. La valeur par défaut est 10 jours.

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Modification des paramètres d’enregistrement à l’aide des cmdlets Windows PowerShell

Vous pouvez modifier les paramètres du fichier journal des mises à jour de l’appareil à l’aide de Windows PowerShell et de l’applet **de connexion Set-CsDeviceUpdateConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».



</div>

Les exemples suivants vous montrent quelques méthodes qui vous permettent d’utiliser la commande **Set-CsDeviceUpdateConfiguration** pour modifier les paramètres.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Pour modifier la taille maximale du fichier journal et l’intervalle de nettoyage du journal

  - La commande suivante modifie les paramètres du journal de mise à jour de l’appareil appliqués au site de Redmond. Dans cet exemple, la taille maximale du fichier journal est définie sur 204800 octets et l’intervalle de nettoyage du journal est défini sur 14 jours.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Pour modifier l’heure de nettoyage du journal de la journée

  - Cette commande définit la durée de nettoyage du journal de Redmond site sur 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

