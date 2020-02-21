---
title: 'Lync Server 2013 : configuration technique requise pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467f4047754697322780373521cdd47fe1e1ba3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Configuration technique requise pour le parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Cette section décrit les exigences techniques suivantes pour le parcage d’appel :

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Conditions requises pour les fichiers audio

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

L’application de parcage d’appel présente les mêmes besoins en matière de matériel que les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

L’application de parcage d’appel présente les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Tous les serveurs frontaux et les serveurs Standard Edition Server sur lesquels l’application de parcage d’appel est déployée doivent avoir installé le module d’exécution du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows. Le runtime du format Windows Media ou Microsoft Media Foundation est requis pour les fichiers audio Windows Media (. WMA) que le parcage d’appel joue pour la musique en attente.

</div>

<div>

## <a name="port-requirements"></a>Configuration requise pour les ports

L’application de parcage d’appel utilise le port suivant :

  - **Port 5075**   utilisé pour les demandes d’écoute SIP.

<div>


> [!NOTE]  
> Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>. Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application de parcage d’appel ne prend en charge que les fichiers audio Windows Media (. WMA) pour l’attente musicale. Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4. Pour télécharger Expression Encoder 4, voir « Expression Encoder 4 » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843). Utilisez l’outil pour convertir le fichier au format .wma. Le format recommandé des fichiers d’attente musicale pour le parcage d’appel est Windows Media Audio 9,44 kHz, 16 bits, Mono, CBR, 32 Kbits/s.

<div>


> [!NOTE]  
> Le fichier converti est lu à 16 kHz sur le téléphone, même s’il a été enregistré à 44 kHz.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

