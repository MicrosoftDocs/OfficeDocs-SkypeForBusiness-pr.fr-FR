---
title: 'Lync Server 2013 : installation de Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de45679983221d80171dde8dd37397a8b3a965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534781"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Installation de Windows PowerShell 3,0 pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-27_

Pour déployer Lync Server 2013 avec succès, vous aurez besoin de Windows PowerShell 3,0 sur chaque ordinateur qui fait partie de votre topologie Lync Server.

À présent, pour les systèmes exécutant Windows Server 2012 ou Windows Server 2012 R2, vous n’avez rien à faire, et vous pouvez passer à l’étape suivante du déploiement, car PowerShell 3,0 est inclus dans ces systèmes d’exploitation.

<div>


> [!IMPORTANT]  
> Toutefois, pour les systèmes exécutant Windows Server 2008 R2 SP1, vous devez installer PowerShell 3,0 comme condition préalable avant d’installer Lync Server 2013, sinon les choses ne fonctionneront pas. Pour installer PowerShell 3,0, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Il s’agit d’un lien direct vers la page de téléchargement de PowerShell 3,0, ainsi que des informations relatives à son installation.



</div>

Une fois que vous avez terminé l’installation de ou si vous souhaitez simplement vérifier et vous assurer avant de poursuivre le déploiement de Lync Server, il est facile de vérifier que PowerShell 3,0 se trouve sur un serveur si vous procédez comme suit :

1.  Sur le serveur que vous souhaitez vérifier, cliquez sur **Démarrer**, **tous les programmes**, **accessoires**, **Windows PowerShell**, puis sur **Windows PowerShell**.

2.  Dans la console Windows PowerShell, tapez la commande suivante à l’invite de commandes, puis appuyez sur entrée :
    
        Get-Host | Select-Object Version

3.  Si Windows PowerShell 3,0 est installé, la sortie ressemblera à ceci :
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

