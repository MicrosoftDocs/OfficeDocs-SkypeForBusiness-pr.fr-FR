---
title: 'Lync Server 2013 : suppression d’un numéro d’accès à une conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f24565056aac396afd78fb944ae97feec37c905f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="b7a1c-102">Suppression d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7a1c-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7a1c-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b7a1c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b7a1c-104">Procédez comme suit pour supprimer un numéro d’accès de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="b7a1c-105">Pour supprimer un numéro d’accès à une conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="b7a1c-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="b7a1c-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b7a1c-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b7a1c-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b7a1c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b7a1c-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="b7a1c-110">Sur la page, cliquez sur le numéro d’accès que vous souhaitez supprimer dans la liste, cliquez sur **modifier**, puis sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="b7a1c-111">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b7a1c-112">Suppression des numéros d’accès aux conférences rendez-vous à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7a1c-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b7a1c-113">Les numéros d’accès aux conférences rendez-vous peuvent être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet csdialinconferencingaccessnumber** .</span><span class="sxs-lookup"><span data-stu-id="b7a1c-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="b7a1c-114">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b7a1c-115">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="b7a1c-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="b7a1c-116">Pour supprimer un numéro d’accès à une conférence rendez-vous spécifique</span><span class="sxs-lookup"><span data-stu-id="b7a1c-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="b7a1c-117">Cette commande supprime le numéro d’accès à la Conférence rendez-vous avec l’identité sip :RedmondDialInAccess@litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="b7a1c-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="b7a1c-118">Pour supprimer tous les numéros d’accès de conférence rendez-vous affectés à une région spécifique</span><span class="sxs-lookup"><span data-stu-id="b7a1c-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="b7a1c-119">Cette commande supprime tous les numéros d’accès de conférence rendez-vous associés à la région Nord-Ouest :</span><span class="sxs-lookup"><span data-stu-id="b7a1c-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="b7a1c-120">Pour supprimer les numéros d’accès de conférence rendez-vous en fonction de la langue principale</span><span class="sxs-lookup"><span data-stu-id="b7a1c-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="b7a1c-121">Cette commande supprime tous les numéros d’accès aux conférences rendez-vous où l’italien est la langue principale :</span><span class="sxs-lookup"><span data-stu-id="b7a1c-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="b7a1c-122">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="b7a1c-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

