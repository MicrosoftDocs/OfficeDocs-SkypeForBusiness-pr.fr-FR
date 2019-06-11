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

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="09918-102">Configuration de la page de participation à une réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09918-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09918-103">_**Dernière modification de la rubrique:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="09918-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="09918-104">Lorsqu’un utilisateur clique sur un lien de réunion dans une demande de réunion, la page de participation à une réunion détecte si un client 2013 Lync est déjà installé sur l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="09918-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="09918-105">Si un client est déjà installé, le client ouvre et joint la réunion.</span><span class="sxs-lookup"><span data-stu-id="09918-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="09918-106">Si un client n’est pas installé, la version 2013 de Lync Web App est ouverte par défaut.</span><span class="sxs-lookup"><span data-stu-id="09918-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="09918-107">Vous pouvez modifier le comportement de la page de participation à une réunion si vous voulez permettre aux utilisateurs de participer à des réunions avec Office Communicator 2007 R2 ou Lync 2010 attendant.</span><span class="sxs-lookup"><span data-stu-id="09918-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="09918-108">Ces options de configuration ont été supprimées du panneau de configuration de Lync Server 2013, mais vous avez configuré celles-ci à l’aide de l’applet de commande Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="09918-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="09918-109">Ensemble de pages de participation à une réunion-paramètres de CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="09918-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09918-110">Paramètre SET-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="09918-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="09918-111">Description</span><span class="sxs-lookup"><span data-stu-id="09918-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09918-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="09918-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="09918-113">Si elle est définie sur true, les utilisateurs qui rejoignent une réunion à l’aide d’une application client autre que Lync seront en mesure de rejoindre la réunion à l’aide d’Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="09918-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="09918-114">La valeur par défaut est False.</span><span class="sxs-lookup"><span data-stu-id="09918-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09918-115">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="09918-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="09918-116">Lorsque cette propriété est définie sur true, d’autres options permettant de participer à une conférence en ligne (comme Office Communicator 2007 R2) seront automatiquement développées et affichées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="09918-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="09918-117">Lorsque ce paramètre est défini sur false (valeur par défaut), ces options sont disponibles, mais l’utilisateur doit afficher la liste des options pour eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="09918-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="09918-118">Pour configurer la page de participation à une réunion à l’aide de Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="09918-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="09918-119">Démarrez Lync Server 2013 Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="09918-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="09918-120">Pour afficher les paramètres de configuration de service Web, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="09918-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="09918-121">Exécutez la commande suivante avec les paramètres définis sur true ou false, en fonction de votre préférence (pour plus d’informations sur les paramètres de cette applet de commande, voir [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) dans la documentation de Lync Server 2013 Management Shell):</span><span class="sxs-lookup"><span data-stu-id="09918-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09918-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09918-122">See Also</span></span>


[<span data-ttu-id="09918-123">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="09918-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

