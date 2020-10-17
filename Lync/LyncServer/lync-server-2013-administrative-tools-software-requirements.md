---
title: 'Lync Server 2013 : configuration logicielle requise pour les outils d’administration'
description: 'Lync Server 2013 : configuration logicielle requise pour les outils d’administration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c723d56cbda0c171fab206e3bcd3b2da0cc5b4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552960"
---
# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Configuration logicielle requise pour les outils d’administration dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Cette rubrique décrit les logiciels requis pour installer et utiliser les outils d’administration Lync Server 2013 en plus de la configuration requise pour le système d’exploitation.

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

L’édition 64 bits de Microsoft .NET Framework 4,5 est requise pour Lync Server 2013.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3,0 est requis pour l’exécution de n’importe quel composant de Microsoft Lync Server 2013. Pour plus d’informations, consultez la rubrique [installation de Windows PowerShell 3,0 pour Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Windows Installer version 4.5

Lync Server 2013 utilise la technologie Windows Installer pour installer, désinstaller et gérer différents rôles serveur. Windows Installer version 4.5 est disponible sous forme de composant redistribuable pour le système d’exploitation Windows Server. Windows Installer 4,5 est fourni avec Windows Server 2012 R2, Windows Server 2012 et Windows Server 2008 R2, ce qui signifie que vous n’avez pas besoin de télécharger l’utilitaire pour un ordinateur exécutant Lync Server 2013. (Lync Server 2013 ne peut être installé que sur des ordinateurs exécutant Windows Server 2012 R2, Windows Server 2012 ou Windows Server 2008 R2.)

Toutefois, si vous souhaitez installer Lync Server Management Shell ou le générateur de topologie Lync Server sur une station de travail administrateur, vous devrez peut-être Télécharger Windows Installer 4,5. Cet utilitaire est fourni avec Windows 7 et Windows 2008 R2, mais pas avec les versions précédentes du système d’exploitation Windows. Vous pouvez télécharger Windows Installer 4,5 à partir du centre de téléchargement Microsoft à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=197395> .

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Plug-in de navigateur Microsoft Silverlight 5

Le panneau de configuration Lync Server 2013 est un outil Web qui nécessite l’installation de la dernière version du plug-in de navigateur Microsoft Silverlight 5. Lorsque vous démarrez le panneau de configuration Lync Server 2013, si ce logiciel n’est pas installé ou si une version antérieure est installée, le panneau de configuration Lync Server 2013 vous invite à installer la version requise.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Configuration requise pour l’infrastructure des outils d’administration dans Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Droits et autorisations d’administrateur requis pour la configuration et l’administration de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

