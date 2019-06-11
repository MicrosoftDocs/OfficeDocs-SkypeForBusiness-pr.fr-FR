---
title: 'Lync Server 2013: afficher les informations sur les paramètres de configuration de Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="ad5ef-102">Afficher les informations sur les paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad5ef-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad5ef-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ad5ef-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ad5ef-104">Vous pouvez consulter les informations de configuration des appareils exécutant Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="ad5ef-105">Les informations sont organisées en collections.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-105">The information is organized into collections.</span></span> <span data-ttu-id="ad5ef-106">Lorsque vous installez Lync Server, vous obtenez un ensemble de paramètres Lync Phone Edition qui s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="ad5ef-107">Vous pouvez également créer de nouvelles collections de paramètres pour un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="ad5ef-108">Les paramètres de site sont prioritaires par rapport aux paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="ad5ef-109">Chaque collection de paramètres est composée d’un nom, d’une étendue (globale ou d’un site), d’un paramètre de sécurité SIP, d’un niveau de journalisation de la qualité de service (QoS), d’un paramètre de verrouillage du téléphone et de détails du verrou téléphonique, c’est-à-dire de la longueur minimale de déverrouillage de l’identification personnelle. nombre (code confidentiel) et temps avant que le téléphone se verrouille.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="ad5ef-110">Pour afficher des informations de configuration sur les appareils exécutant Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ad5ef-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="ad5ef-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ad5ef-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ad5ef-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ad5ef-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ad5ef-114">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de **configuration d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="ad5ef-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="ad5ef-115">Dans la page **Configuration des appareils** , cliquez sur l’ensemble de paramètres pour lesquels vous souhaitez afficher les informations.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="ad5ef-116">Le nom, l’étendue, le paramètre de sécurité SIP, le niveau de qualité de la voix et les paramètres de verrouillage du téléphone apparaissent dans la page principale.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="ad5ef-117">Pour afficher le niveau de journalisation et les détails de verrouillage du téléphone, cliquez sur le menu **modifier** , puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ad5ef-118">Affichage des informations de configuration de Lync Phone Edition à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad5ef-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ad5ef-119">Vous pouvez afficher les paramètres de configuration de Lync Phone Edition à l’aide de Lync Server Management Shell et de l’applet **de passe Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ad5ef-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="ad5ef-120">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad5ef-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ad5ef-121">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="ad5ef-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="ad5ef-122">Pour afficher les informations de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ad5ef-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="ad5ef-123">Pour afficher des informations sur les paramètres de configuration de Lync Phone Edition, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="ad5ef-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="ad5ef-124">La commande renvoie des informations similaires à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="ad5ef-124">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="ad5ef-125">Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ad5ef-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad5ef-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad5ef-126">See Also</span></span>


[<span data-ttu-id="ad5ef-127">Créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad5ef-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="ad5ef-128">Supprimer une collection existante de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad5ef-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="ad5ef-129">Configurer les paramètres de sécurité de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad5ef-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="ad5ef-130">Renforcer le verrouillage du téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad5ef-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

