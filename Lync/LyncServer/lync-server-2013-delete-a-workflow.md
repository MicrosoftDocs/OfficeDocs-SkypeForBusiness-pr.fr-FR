---
title: 'Lync Server 2013 : supprimer un flux de travail'
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
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Supprimer un flux de travail dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Pour supprimer un flux de travail, utilisez l’une des procédures suivantes.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Pour utiliser le panneau de configuration de Lync Server pour supprimer un flux de travail

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **Flux de travail**.

4.  Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.

5.  Dans le champ de recherche **Sélectionner un service** , tapez tout ou partie du nom du service **ApplicationServer** qui héberge le flux de travail que vous voulez supprimer.

6.  Dans la liste de services, cliquez sur le service que vous souhaitez utiliser, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > La page Web de l’outil de configuration de Response Group s’ouvre. Vous pouvez également accéder à la page Web de l’outil de configuration du groupe de réponse directement à partir d’un navigateur Web en vous connectant à <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.

    
    </div>

7.  Sous **gérer un flux de travail existant**, recherchez le flux de travail que vous voulez supprimer, puis sous **action**, cliquez sur **supprimer**.

8.  Cliquez sur **Oui**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Pour utiliser Windows PowerShell pour supprimer un flux de travail

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans la ligne de commande, exécutez la commande suivante :
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Par exemple :
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

