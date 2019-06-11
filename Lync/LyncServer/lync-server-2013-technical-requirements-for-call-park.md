---
title: 'Lync Server 2013 : Configuration technique requise pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c03c3b99e911766d2c60eec2a5515b3750d29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Configuration technique requise pour le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Cette section décrit les exigences techniques suivantes en matière de stationnement d’appel:

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Configuration requise pour le fichier audio

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

La configuration matérielle requise pour l’application de parc d’appels est identique à celle des serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

La configuration requise pour les systèmes d’exploitation et les logiciels requis par le biais de l’application de parc d’appels est la même que celle des serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.

Tous les serveurs frontaux et les serveurs Standard Edition Server pour lesquels l’application de parc d’appels est déployée doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows. Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Windows Media audio (. WMA) pour lesquels le parc est lu pour la musique en attente.

</div>

<div>

## <a name="port-requirements"></a>Configuration requise pour les ports

L’application de parc d’appels utilise le port suivant:

  - **Port 5075**   utilisé pour les demandes d’écoute SIP.

<div>


> [!NOTE]  
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>. Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application de parc d’appels prend uniquement en charge les fichiers Windows Media audio (. WMA) pour la musique en attente. Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Expression Encoder 4, voir «Expression Encoder 4» à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843). Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé pour les fichiers de la musique de parc d’appels est l’audio multimédia 9, 44 kHz, 16 bits, mono, CBR, 32 kbps.

<div>


> [!NOTE]  
> Le fichier converti est lu sur le téléphone à seulement 16 kHz, même s’il a été enregistré à 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

