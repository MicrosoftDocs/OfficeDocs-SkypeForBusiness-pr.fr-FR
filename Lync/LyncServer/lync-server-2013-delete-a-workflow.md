---
title: 'Lync Server 2013 : suppression d’un flux de travail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b46f3b9bd89df2594c7ca8a3b382839437e40eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516291"
---
# <a name="delete-a-workflow-in-lync-server-2013"></a>Supprimer un flux de travail dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour supprimer un flux de travail, effectuez l’une des procédures suivantes.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Pour utiliser le panneau de configuration Lync Server supprimer un flux de travail

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Flux de travail**.

4.  Sur la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.

5.  Dans le champ de recherche **Sélectionner un service**, tapez l’intégralité ou le début du nom du service **ApplicationServer** qui héberge le flux de travail que vous voulez supprimer.

6.  Dans la liste des services, cliquez sur le service voulu, puis sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > La page Web de l’outil de configuration Response Group s’ouvre. Vous pouvez également ouvrir la page Web de l’outil de configuration Response Group directement à partir d’un navigateur Web en vous connectant à <STRONG>https:// &lt; webpoolfqdn représente &gt; /RgsConfig</STRONG>.

    
    </div>

7.  Sous **Gérer un flux de travail existant**, recherchez le flux de travail que vous souhaitez supprimer, puis sous **Action**, cliquez sur **Supprimer**.

8.  Cliquez sur **Oui**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Pour utiliser Windows PowerShell afin de supprimer un flux de travail

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Par exemple :
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

