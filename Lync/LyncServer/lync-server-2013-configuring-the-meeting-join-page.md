---
title: 'Lync Server 2013 : Configuration de la page de participation à une réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984386eb15aac3c3d2d46c9d7aaab53457915b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Configuration de la page de participation à une réunion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-12-14_

Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détecte si un client 2013 Lync est déjà installé sur l’ordinateur de l’utilisateur. Si un client est déjà installé, le client ouvre et joint la réunion. Si un client n’est pas installé, la version 2013 de Lync Web App est ouverte par défaut.

Vous pouvez modifier le comportement de la page de participation à une réunion si vous voulez permettre aux utilisateurs de participer à des réunions avec Office Communicator 2007 R2 ou Lync 2010 attendant. Ces options de configuration ont été supprimées du panneau de configuration de Lync Server 2013, mais vous avez configuré celles-ci à l’aide de l’applet de commande Set-CsWebServiceConfiguration.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Ensemble de pages de participation à une réunion-paramètres de CsWebServiceConfiguration

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre SET-CsWebServiceConfiguration</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>Si elle est définie sur true, les utilisateurs qui rejoignent une réunion à l’aide d’une application client autre que Lync seront en mesure de rejoindre la réunion à l’aide d’Office Communicator 2007 R2. La valeur par défaut est False.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>Lorsque cette propriété est définie sur true, d’autres options permettant de participer à une conférence en ligne (comme Office Communicator 2007 R2) seront automatiquement développées et affichées aux utilisateurs. Lorsque ce paramètre est défini sur false (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Pour configurer la page de participation à une réunion à l’aide de Lync Server 2013 Management Shell

1.  Démarrez Lync Server 2013 Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Pour afficher les paramètres de configuration de service Web, exécutez l’applet de commande suivante:
    
        Get-CsWebServiceConfiguration

3.  Exécutez la commande suivante avec les paramètres définis sur true ou false, en fonction de votre préférence (pour plus d’informations sur les paramètres de cette applet de commande, voir [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) dans la documentation de Lync Server 2013 Management Shell):
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

