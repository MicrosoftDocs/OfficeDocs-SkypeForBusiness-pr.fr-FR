---
title: 'Lync Server 2013 : configuration de la page de participation aux réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c191bbc8927790345e7f969c38e4bf1a74ec3bdb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532321"
---
# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="31177-102">Configuration de la page de participation aux réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31177-102">Configuring the meeting join page in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31177-103">_**Dernière modification de la rubrique :** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="31177-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="31177-104">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation aux réunions détecte si un client Lync 2013 est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31177-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="31177-105">Si c’est le cas, ce client s’ouvre et se joint à la réunion.</span><span class="sxs-lookup"><span data-stu-id="31177-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="31177-106">Si un client n’est pas installé, la version 2013 de Lync Web App par défaut s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="31177-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="31177-107">Vous pouvez modifier le comportement de la page de participation à la réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions avec Office Communicator 2007 R2 ou Lync 2010 attendant.</span><span class="sxs-lookup"><span data-stu-id="31177-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="31177-108">Ces options de configuration ont été supprimées du panneau de configuration Lync Server 2013, mais vous les configurez à l’aide de l’applet de commande Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="31177-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="31177-109">Paramètres Set-CsWebServiceConfiguration de la page de participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="31177-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31177-110">Paramètre Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="31177-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="31177-111">Description</span><span class="sxs-lookup"><span data-stu-id="31177-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31177-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="31177-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="31177-113">Si la valeur est true, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync auront la possibilité de participer à la réunion à l’aide d’Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="31177-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="31177-114">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="31177-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31177-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="31177-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="31177-p104">Quand la valeur est True, les autres options pour rejoindre une conférence en ligne (comme Office Communicator 2007 R2) seront automatiquement développées et montrées aux utilisateurs. Quand la valeur est False (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options.</span><span class="sxs-lookup"><span data-stu-id="31177-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="31177-118">Pour configurer la page de participation aux réunions à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="31177-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="31177-119">Démarrez Lync Server 2013 Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="31177-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="31177-120">Pour afficher les paramètres de configuration du service web, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="31177-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="31177-121">Exécutez la commande suivante, avec les paramètres définis sur true ou false, en fonction de vos préférences (pour plus d’informations sur les paramètres de cette cmdlet, voir [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) dans la documentation de Lync Server 2013 Management Shell) :</span><span class="sxs-lookup"><span data-stu-id="31177-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31177-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31177-122">See Also</span></span>


[<span data-ttu-id="31177-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="31177-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

