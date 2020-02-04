---
title: 'Lync Server 2013 : Configuration technique requise pour Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Configuration technique requise pour Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Cette section décrit les exigences techniques suivantes pour l’application Response Group :

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Configuration requise pour le fichier audio

  - Configuration requise pour l’outil de configuration de Response Group

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

L’application de Response Group a les mêmes exigences matérielles que les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

Comme serveur frontal, l’application de Response Group a les mêmes exigences relatives au système d’exploitation et aux configurations logicielles requises. Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.

Si vous utilisez des fichiers Windows Media audio (. WMA) pour la musique et les annonces du groupe réponse, tous les serveurs frontaux ou les éditions standard qui exécutent l’application Response Group doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows.

Pour plus d’informations sur la configuration audio requise, voir « exigences relatives au fichier audio » plus loin dans cette section.

</div>

<div>

## <a name="port-requirements"></a>Configuration requise pour les ports

L’application Response Group utilise les ports suivants :

  - **Port 5071**   utilisé pour les demandes d’écoute SIP

  - **Port 8404**   utilisé pour les communications entre les serveurs
    
    <div>
    

    > [!NOTE]  
    > Ce port est utilisé pour le service de mise en correspondance et est requis lors du déploiement de l’application Response Group dans un pool qui comporte plusieurs serveurs front-end.

    
    </div>

<div>


> [!NOTE]  
> Ces ports sont les paramètres par défaut que vous pouvez modifier à l’aide de l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>. Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application Response Group prend en charge le format de fichier Wave (. wav) et le format de fichier Windows Media audio (. WMA) pour les messages de groupe de réponse, la musique en attente ou les questions de réponse vocale interactive.

Le format de fichier audio Windows Media nécessite que le runtime du format Windows Media soit installé sur les serveurs frontaux exécutant Windows Server 2008 R2 et Windows Server 2008. Pour plus d’informations, reportez-vous à « Configuration logicielle requise » plus haut dans cette section.

<div>

## <a name="supported-wave-file-formats"></a>Formats de fichiers Wave pris en charge

Tous les fichiers Wave doivent répondre aux conditions suivantes :

  - fichier 8 bits ou 16 bits ;

  - format LPCM (Linear Pulse Code Modulation), A-Law ou mu-Law ;

  - mono ou stéréo ;

  - 4 Mo ou moins.

Pour des performances de fichiers Wave optimales, nous vous recommandons d’utiliser un fichier Wave correspondant au profil suivant : 16 kHz, Mono, 16 bits.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Formats de fichiers audio Windows Media pris en charge

Si vous utilisez un fichier audio Windows Media, prévoyez d’utiliser de faibles vitesses de transmission et vérifiez les performances de votre système quand il est surchargé.

Vous pouvez utiliser Microsoft Expression Encoder 4 pour convertir un fichier au format audio Windows Media. Pour télécharger Expression Encoder 4 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843), voir.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Conditions requises pour l’outil de configuration Response Group

L’outil de configuration de Response Group prend en charge les combinaisons de systèmes d’exploitation et de navigateurs Web décrits dans le tableau ci-dessous.

<div>


> [!NOTE]  
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Systèmes d’exploitation et navigateurs web pris en charge

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Système d’exploitation</th>
<th>Navigateur web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista avec Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 avec Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Console des agents Response Group

La console des agents prend en charge les combinaisons de systèmes d’exploitation et de navigateurs indiquées dans le tableau suivant.

<div>


> [!NOTE]  
> Les versions 32 bits ou 64 bits des systèmes d’exploitation sont prises en charge. Seules les versions 32 bits d’Internet Explorer sont prises en charge.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Systèmes d’exploitation et navigateurs web pris en charge

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Système d’exploitation</th>
<th>Navigateur web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista avec Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 avec Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 avec Service Pack 1</p></td>
<td><p>Internet Explorer 8 (mode natif)</p>
<p>Internet Explorer 9 (mode natif)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

