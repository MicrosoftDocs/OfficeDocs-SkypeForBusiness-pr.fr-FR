---
title: 'Lync Server 2013 : Configuration logicielle requise pour les outils d’administration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95dfed4d6cf69950a0e17ab6826d79ee7e7a68cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Configuration logicielle requise pour les outils d’administration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Cette rubrique décrit les logiciels requis pour installer et utiliser les outils d’administration de Lync Server 2013 en plus de la configuration requise du système d’exploitation.

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

L’édition 64 bits de Microsoft .NET Framework 4,5 est requise pour Lync Server 2013.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3,0 est requis pour l’exécution de tous les composants de Microsoft Lync Server 2013. Pour plus d’informations, voir [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer version 4,5

Lync Server 2013 utilise la technologie Windows Installer pour installer, désinstaller et gérer divers rôles de serveur. La version 4,5 de Windows Installer est disponible en tant que composant redistribuable pour le système d’exploitation Windows Server. Windows Installer 4,5 est fourni avec Windows Server 2012 R2, Windows Server 2012 et Windows Server 2008 R2, ce qui signifie que vous n’avez pas besoin de télécharger l’utilitaire pour les ordinateurs exécutant Lync Server 2013. (Lync Server 2013 ne peut être installé que sur les ordinateurs exécutant Windows Server 2012 R2, Windows Server 2012 ou Windows Server 2008 R2.)

Toutefois, si vous voulez installer Lync Server Management Shell ou le générateur de topologie de Lync Server sur une station de travail administrateur, vous devrez peut-être télécharger le programme d’installation 4,5. Cet utilitaire est fourni avec Windows 7 et Windows 2008 R2, mais pas pour les versions antérieures du système d’exploitation Windows. Vous pouvez télécharger Windows Installer 4,5 à partir du centre de téléchargement <http://go.microsoft.com/fwlink/p/?linkid=197395>Microsoft à l’adresse.

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Plug-in de navigateur Microsoft Silverlight 5

Le panneau de configuration de Lync Server 2013 est un outil Web qui nécessite l’installation de la dernière version du plug-in de navigateur Microsoft Silverlight 5. Lorsque vous démarrez le panneau de configuration de Lync Server 2013, si ce logiciel n’est pas installé ou si vous avez installé une version antérieure, le panneau de configuration de Lync Server 2013 vous invite à installer la version requise.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Exigences d’infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

