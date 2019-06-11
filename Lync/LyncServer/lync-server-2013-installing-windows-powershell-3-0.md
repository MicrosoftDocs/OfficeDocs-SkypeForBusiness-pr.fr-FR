---
title: 'Lync Server 2013 : Installation de Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Installation de Windows PowerShell 3.0 pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-27_

Pour déployer Lync Server 2013 avec succès, vous avez besoin de Windows PowerShell 3,0 sur chaque ordinateur qui fait partie de la topologie de votre serveur Lync.

Pour le moment, pour les systèmes exécutant Windows Server 2012 ou Windows Server 2012 R2, vous n’avez pas besoin d’effectuer cette opération et vous pouvez passer à l’étape suivante du déploiement, car PowerShell 3,0 est inclus avec ces systèmes d’exploitation.

<div>


> [!IMPORTANT]  
> Toutefois, pour les systèmes exécutant Windows Server 2008 R2 SP1, vous devez installer PowerShell 3,0 en tant que composant requis avant d’installer Lync Server 2013 ou les éléments ne fonctionneront pas. Pour installer PowerShell 3,0, voir <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Il s’agit d’un lien direct vers la page de téléchargement 3,0 PowerShell, ainsi que des informations relatives à son installation réussie.



</div>

Une fois l’installation terminée, ou si vous souhaitez simplement vérifier et être sûr d’avoir suivi le déploiement de Lync Server, il est très simple de vérifier que PowerShell 3,0 est sur un serveur si vous procédez comme suit:

1.  Sur le serveur que vous voulez vérifier, cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **accessoires**, sur **Windows PowerShell**, puis sur **Windows PowerShell**.

2.  Dans la console Windows PowerShell, tapez la commande suivante à l’invite de commandes, puis appuyez sur entrée:
    
        Get-Host | Select-Object Version

3.  Si Windows PowerShell 3,0 est installé, une sortie semblable à la suivante apparaît:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

