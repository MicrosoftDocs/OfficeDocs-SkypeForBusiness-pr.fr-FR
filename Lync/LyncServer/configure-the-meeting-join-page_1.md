---
title: Configurer la page de participation aux réunions
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 491f920931fae5b64cf629aebae007ca4b4e998e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="4edea-102">Configurer la page de participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="4edea-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4edea-103">_**Dernière modification de la rubrique :** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="4edea-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="4edea-104">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation aux réunions détecte si un client Lync 2013 est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4edea-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="4edea-105">Si c’est le cas, ce client s’ouvre et se joint à la réunion.</span><span class="sxs-lookup"><span data-stu-id="4edea-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="4edea-106">Si un client n’est pas installé, la version 2013 de Microsoft Lync Web App est ouverte par défaut.</span><span class="sxs-lookup"><span data-stu-id="4edea-106">If a client is not installed, by default the 2013 version of Microsoft Lync Web App opens.</span></span>

<span data-ttu-id="4edea-107">Vous pouvez modifier le comportement de la page de participation à la réunion si vous souhaitez autoriser les utilisateurs à participer à des réunions avec Office Communicator 2007 R2 ou Lync 2010 attendant.</span><span class="sxs-lookup"><span data-stu-id="4edea-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="4edea-108">Ces options de configuration ont été supprimées du panneau de configuration Lync Server 2013, mais vous les configurez à l’aide de l’applet de commande CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4edea-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="4edea-109">Paramètres CsWebServiceConfiguration de la page de participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="4edea-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4edea-110">Paramètre CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4edea-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="4edea-111">Description</span><span class="sxs-lookup"><span data-stu-id="4edea-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4edea-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="4edea-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="4edea-113">Si la valeur est true, les utilisateurs qui rejoignent une réunion à l’aide d’une application cliente autre que Lync auront la possibilité de participer à la réunion à l’aide d’Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4edea-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="4edea-114">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="4edea-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4edea-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="4edea-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="4edea-p104">Quand la valeur est True, les autres options pour rejoindre une conférence en ligne (comme Office Communicator 2007 R2) seront automatiquement développées et montrées aux utilisateurs. Quand la valeur est False (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options.</span><span class="sxs-lookup"><span data-stu-id="4edea-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="4edea-118">Pour configurer la page de participation aux réunions à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="4edea-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="4edea-119">Démarrez Lync Server 2013 Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4edea-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4edea-120">Exécutez la cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="4edea-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="4edea-121">Cette applet de commande renvoie les paramètres de configuration du service Web.</span><span class="sxs-lookup"><span data-stu-id="4edea-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="4edea-122">Exécutez la commande suivante, avec les paramètres définis sur true ou false, en fonction de vos préférences (pour plus d’informations sur les paramètres de cette cmdlet, voir la documentation de Lync Server 2013 Management Shell) :</span><span class="sxs-lookup"><span data-stu-id="4edea-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

