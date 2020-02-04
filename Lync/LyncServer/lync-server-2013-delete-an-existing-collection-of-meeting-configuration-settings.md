---
title: Supprimer une collection existante de paramètres de configuration de réunion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe774830a8efc6f0cc88a2dd929b3126335b51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="eae75-102">Supprimer une collection existante de paramètres de configuration de réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae75-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae75-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eae75-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eae75-104">Vous pouvez supprimer une configuration de site ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eae75-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="eae75-105">La configuration globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="eae75-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="eae75-106">Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.</span><span class="sxs-lookup"><span data-stu-id="eae75-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="eae75-107">Pour supprimer une configuration de réunion de site ou d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="eae75-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="eae75-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="eae75-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eae75-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eae75-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eae75-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eae75-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eae75-111">Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur Configuration de la **réunion**.</span><span class="sxs-lookup"><span data-stu-id="eae75-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="eae75-112">Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="eae75-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eae75-113">Supprimer les paramètres de configuration de la réunion à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eae75-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eae75-114">Vous pouvez supprimer les paramètres de la réunion à l’aide de Windows PowerShell et de l’applet de passe Remove-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="eae75-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="eae75-115">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eae75-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eae75-116">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="eae75-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="eae75-117">Pour supprimer une collection de paramètres de configuration de réunion spécifiée</span><span class="sxs-lookup"><span data-stu-id="eae75-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="eae75-118">Cette commande supprime les paramètres de configuration de la réunion appliqués au site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="eae75-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="eae75-119">Pour supprimer tous les paramètres de configuration de réunion appliqués à l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="eae75-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="eae75-120">Cette commande supprime tous les paramètres de configuration de réunion appliqués à l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="eae75-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="eae75-121">Pour supprimer tous les paramètres de configuration de réunion qui autorisent les utilisateurs anonymes par défaut</span><span class="sxs-lookup"><span data-stu-id="eae75-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="eae75-122">Par défaut, cette option supprime tous les paramètres qui autorisent les utilisateurs anonymes à être admis par défaut :</span><span class="sxs-lookup"><span data-stu-id="eae75-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="eae75-123">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="eae75-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

