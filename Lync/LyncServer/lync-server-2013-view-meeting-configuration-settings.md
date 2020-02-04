---
title: 'Lync Server 2013 : afficher les paramètres de configuration de la réunion'
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
ms.openlocfilehash: 5737fbba63915501bea80105ef3509511d8cb436
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3e4c5-102">Afficher les paramètres de configuration de la réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e4c5-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e4c5-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3e4c5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3e4c5-104">Dans Lync Server 2013 panneau de configuration, vous utilisez le paramètre de configuration de la réunion pour contrôler l’implémentation des réunions dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="3e4c5-105">Cela inclut les configurations de réunion suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e4c5-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="3e4c5-106">Configuration globale créée par défaut lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="3e4c5-107">Configurations facultatives de niveau de site et de niveau utilisateur que vous pouvez créer et utiliser pour spécifier le mode d’implémentation des réunions pour des sites ou des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="3e4c5-108">Pour afficher les paramètres de configuration de la réunion</span><span class="sxs-lookup"><span data-stu-id="3e4c5-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="3e4c5-109">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e4c5-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e4c5-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e4c5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e4c5-112">Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur Configuration de la **réunion**.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="3e4c5-113">Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion à afficher.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="3e4c5-114">Dans **modifier le filtre de fichier**, sélectionnez l’option **afficher les détails...**</span><span class="sxs-lookup"><span data-stu-id="3e4c5-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="3e4c5-115">case à cocher.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-115">check box.</span></span>
    
    <span data-ttu-id="3e4c5-116">**Modifier la configuration de \<la\> réunion : une stratégie** s’ouvre et affiche les paramètres de la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="3e4c5-117">Pour plus d’informations sur la configuration des paramètres, voir [créer ou modifier un ensemble de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3e4c5-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3e4c5-118">Affichage des informations de configuration de la réunion à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e4c5-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3e4c5-119">Les paramètres de configuration de réunion peuvent être affichés à l’aide de Windows PowerShell et de l’applet de passe Get-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="3e4c5-120">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e4c5-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3e4c5-121">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="3e4c5-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="3e4c5-122">Pour afficher les informations de configuration de la réunion</span><span class="sxs-lookup"><span data-stu-id="3e4c5-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="3e4c5-123">Pour afficher des informations sur l’ensemble des paramètres de configuration de la réunion, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="3e4c5-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="3e4c5-124">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="3e4c5-124">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="3e4c5-125">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3e4c5-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

