---
title: 'Lync Server 2013 : configuration technique requise pour l’application d’annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54371acb29bcc7d9b6581cbfd26199888dcfe893
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536101"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Configuration technique requise pour l’application d’annonce dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Cette section décrit les exigences techniques suivantes pour l’application d’annonce :

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Conditions requises pour les fichiers audio

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

L’application d’annonce a les mêmes besoins en matière de matériel que les serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [Server Hardware Platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation de prise en charge.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

L’application d’annonce présente les mêmes exigences en matière de système d’exploitation et de logiciels que les serveurs frontaux. Pour plus d’informations sur la configuration logicielle requise, voir [serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation de prise en charge.

Tous les serveurs frontaux ou les serveurs Standard Edition qui exécutent l’application d’annonce doivent avoir installé le module d’exécution du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime du format Windows Media est installé dans le cadre de l’expérience Bureau Windows. Le module d’exécution du format Windows Media ou Microsoft Media Foundation est requis pour les fichiers audio Windows Media (. WMA) que l’application d’annonce joue pour les annonces et la musique.

</div>

<div>

## <a name="port-requirements"></a>Configuration requise pour les ports

L’application d’annonce utilise le port suivant :

  - **Port 5071**     Utilisé pour les demandes d’écoute SIP

<div>


> [!NOTE]  
> Ce port est le paramètre par défaut, que vous pouvez modifier en utilisant la cmdlet <STRONG>Set-CsApplicationServer</STRONG>. Pour plus d’informations sur cette applet de commande, voir la documentation de Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application annonce prend en charge le format de fichier Wave (. wav) et le format de fichier audio Windows Media (. WMA) pour la musique et les annonces. Les exigences en matière de fichiers audio pour l’application d’annonce sont les mêmes que pour l’application Response Group. Pour plus d’informations, voir [Technical Requirements for Response Group dans Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

