---
title: 'Lync Server 2013 : affichage des informations des paramètres de configuration de Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b613a8cd890b3c31028715a6eaac98462295602
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535741"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="4fdf6-102">Afficher les informations des paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf6-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fdf6-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4fdf6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4fdf6-104">Vous pouvez afficher des informations de configuration sur les appareils exécutant Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="4fdf6-105">Les informations sont classées dans des collections.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-105">The information is organized into collections.</span></span> <span data-ttu-id="4fdf6-106">Lorsque vous installez Lync Server, vous obtenez une collection de paramètres Lync Phone Edition qui s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="4fdf6-107">Vous pouvez également créer de nouvelles collections de paramètres pour un site en particulier.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="4fdf6-108">Les paramètres du site ont priorité sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="4fdf6-109">Chaque collection de paramètres se compose d’un nom, de l’étendue (globale ou de site), du paramètre de sécurité SIP, du niveau de journalisation, du niveau de qualité de service de la voix (QoS), du paramètre de verrouillage du téléphone et des détails de verrouillage du téléphone, c’est-à-dire la longueur minimale du code confidentiel de déverrouillage et le délai avant le verrouillage automatique du téléphone.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="4fdf6-110">Pour afficher les informations de configuration des appareils exécutant Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4fdf6-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="4fdf6-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4fdf6-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4fdf6-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4fdf6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4fdf6-114">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4fdf6-p103">Dans la page **Configuration du périphérique**, cliquez sur la collection de paramètres sur laquelle vous souhaitez afficher des informations. Le nom, l’étendue, le paramètre de sécurité SIP, le niveau de qualité de service de la voix et le paramètre de verrouillage du téléphone sont répertoriés dans la page principale. Pour afficher le niveau de journalisation et les détails de verrouillage du téléphone, cliquez sur le menu **Edition**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4fdf6-118">Affichage des informations de configuration de Lync Phone Edition à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fdf6-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4fdf6-119">Vous pouvez afficher les paramètres de configuration de Lync Phone Edition à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4fdf6-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="4fdf6-120">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fdf6-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4fdf6-121">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="4fdf6-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="4fdf6-122">Pour afficher les informations de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4fdf6-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="4fdf6-123">Pour afficher des informations sur tous les paramètres de configuration de Lync Phone Edition, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="4fdf6-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="4fdf6-124">La commande renvoie les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4fdf6-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="4fdf6-125">Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4fdf6-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fdf6-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fdf6-126">See Also</span></span>


[<span data-ttu-id="4fdf6-127">Création ou modification d’une collection de paramètres de configuration Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf6-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="4fdf6-128">Supprimer une collection existante de paramètres de configuration Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf6-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="4fdf6-129">Configurer les paramètres de sécurité pour Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf6-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="4fdf6-130">Appliquer le verrouillage du téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdf6-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

