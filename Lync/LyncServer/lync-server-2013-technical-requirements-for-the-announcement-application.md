---
title: 'Lync Server 2013 : Configuration technique requise pour l’application Annonces'
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
ms.openlocfilehash: 8812dca81d656e68fc506c4a87c3c80481040bf6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Configuration technique requise pour l’application Annonces dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Cette section décrit les exigences techniques suivantes pour l’application d’annonce :

  - Configuration matérielle requise

  - Configuration logicielle requise

  - Conditions requises en matière de ports

  - Configuration requise pour le fichier audio

<div>

## <a name="hardware-requirements"></a>Configuration matérielle requise

La configuration matérielle requise pour l’application d’annonce est identique à celle des serveurs frontaux. Pour plus d’informations sur la configuration matérielle requise, voir [plates-formes matérielles pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) dans la documentation relative à la prise en charge.

</div>

<div>

## <a name="software-requirements"></a>Configuration logicielle requise

La configuration requise pour le système d’exploitation et les composants logiciels requis par le biais de l’application d’annonce sont les mêmes. Pour plus d’informations sur la configuration logicielle requise, voir [prise en charge du système d’exploitation serveur et outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) dans la documentation relative à la prise en charge.

Tous les serveurs front-end ou les serveurs Standard Edition qui exécutent l’application d’annonce doivent avoir installé le runtime du format Windows Media pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2. Pour Windows Server 2008 R2, le runtime Windows Media Format Runtime est installé dans le cadre de l’expérience de bureau Windows. Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Windows Media audio (. WMA) que l’application d’annonce exécute pour les annonces et la musique.

</div>

<div>

## <a name="port-requirements"></a>Configuration requise pour les ports

L’application d’annonce utilise le port suivant :

  - **Port 5071**   utilisé pour les demandes d’écoute SIP

<div>


> [!NOTE]  
> Ce port est le paramètre par défaut, que vous pouvez modifier en utilisant l’applet de commande <STRONG>Set-CsApplicationServer</STRONG>. Pour plus d’informations sur cette applet de connexion, consultez la documentation Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Conditions requises pour les fichiers audio

L’application d’annonce prend en charge le format de fichier Wave (. wav) et le format de fichier Windows Media audio (. WMA) pour la musique et les annonces. La configuration requise pour le fichier audio pour l’application d’annonce est identique à celle de l’application Response Group. Pour plus d’informations, voir [configuration technique requise pour Response Group dans Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

