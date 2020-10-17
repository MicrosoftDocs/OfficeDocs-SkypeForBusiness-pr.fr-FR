---
title: 'Lync Server 2013 : afficher les paramètres de configuration de réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9ad61f93cd7c65be04d30cf35638019ddc7ee58
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506331"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1695f-102">Afficher les paramètres de configuration de réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1695f-102">View meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1695f-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1695f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1695f-104">Dans le panneau de configuration Lync Server 2013, utilisez le paramètre configuration de la réunion pour contrôler la façon dont les réunions sont implémentées dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1695f-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="1695f-105">Cela inclut les configurations de réunion suivantes :</span><span class="sxs-lookup"><span data-stu-id="1695f-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="1695f-106">Une configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1695f-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="1695f-107">Des configurations facultatives aux niveaux du site et de l’utilisateur que vous pouvez créer et utiliser pour spécifier la façon dont les réunions sont implémentées pour des sites ou des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1695f-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="1695f-108">Pour afficher les paramètres de configuration de réunion :</span><span class="sxs-lookup"><span data-stu-id="1695f-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="1695f-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1695f-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1695f-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1695f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1695f-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1695f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1695f-112">Dans la barre de navigation gauche, cliquez sur **Conférence**, puis cliquez sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="1695f-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="1695f-113">Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="1695f-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="1695f-p103">Dans **Modifier le filtre de fichiers**, cochez la case **Afficher les détails…**</span><span class="sxs-lookup"><span data-stu-id="1695f-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="1695f-116">**Modifier la configuration de \<policy\> la réunion-** ouvre les paramètres de la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1695f-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="1695f-117">Pour plus d’informations sur la configuration des paramètres, voir [créer ou modifier une collection de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1695f-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1695f-118">Affichage des informations de configuration de réunion à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1695f-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1695f-119">Les paramètres de configuration de réunion peuvent être affichés à l’aide de Windows PowerShell et de l’applet de commande Get-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1695f-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="1695f-120">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1695f-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1695f-121">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1695f-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="1695f-122">Pour afficher les informations de configuration de réunion</span><span class="sxs-lookup"><span data-stu-id="1695f-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="1695f-123">Pour afficher des informations sur tous vos paramètres de configuration de réunion, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="1695f-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="1695f-124">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1695f-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="1695f-125">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1695f-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

