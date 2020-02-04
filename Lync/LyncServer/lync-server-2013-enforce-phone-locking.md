---
title: 'Lync Server 2013 : renforcer le verrouillage du téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="1487a-102">Renforcer le verrouillage du téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1487a-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1487a-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1487a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1487a-104">Les appareils Lync Phone Edition peuvent être verrouillés pour des raisons de sécurité.</span><span class="sxs-lookup"><span data-stu-id="1487a-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="1487a-105">Si vous appliquez le verrouillage du téléphone, l’appareil exécutant Lync Phone Edition se verrouille après un certain temps que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="1487a-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="1487a-106">Lorsque le téléphone est verrouillé, un utilisateur peut passer des appels mais ne peut pas accéder aux informations de calendrier et de contact, à la messagerie vocale et aux journaux d’appels ou utiliser la recherche.</span><span class="sxs-lookup"><span data-stu-id="1487a-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="1487a-107">Pour déverrouiller le téléphone, l’utilisateur entre un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="1487a-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="1487a-108">Pour appliquer le verrouillage du téléphone, activez et configurez-le à l’aide du panneau de configuration de Lync Server ou des applets de commande PowerShell Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1487a-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="1487a-109">Vous pouvez mettre en place le verrouillage du téléphone globalement ou uniquement dans le site pour lequel il est configuré.</span><span class="sxs-lookup"><span data-stu-id="1487a-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="1487a-110">Pour configurer et appliquer le verrouillage du téléphone</span><span class="sxs-lookup"><span data-stu-id="1487a-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="1487a-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1487a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1487a-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1487a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1487a-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1487a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1487a-114">Cliquez sur **clients**, puis sur **configuration**de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="1487a-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="1487a-115">Dans l’onglet Configuration de l' **appareil** , dans la liste des configurations d’appareils, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de verrouillage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="1487a-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="1487a-116">Dans la boîte de dialogue **modifier la configuration** de l’appareil, vérifiez que la case à cocher appliquer le **verrouillage du périphérique** est activée.</span><span class="sxs-lookup"><span data-stu-id="1487a-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="1487a-117">Dans **longueur du code confidentiel minimum**, acceptez la valeur par défaut du nombre minimal de chiffres que le code confidentiel doit contenir ou spécifiez une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="1487a-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="1487a-118">La plage de la longueur du code confidentiel doit être comprise entre 4 et 15 chiffres, et la valeur par défaut est six.</span><span class="sxs-lookup"><span data-stu-id="1487a-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="1487a-119">Dans **délai de verrouillage du téléphone**, acceptez la valeur par défaut pour la durée minimale avant que le téléphone ne se verrouille ou en spécifiant une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="1487a-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="1487a-120">La plage du délai d’expiration est comprise entre 0 et 60 minutes, et la valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="1487a-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="1487a-121">Le format de cette valeur est HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="1487a-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="1487a-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1487a-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1487a-123">Application du verrouillage du téléphone à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1487a-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1487a-124">Le verrouillage du téléphone peut être appliqué à l’aide de l’applet de passe Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="1487a-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="1487a-125">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1487a-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1487a-126">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="1487a-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="1487a-127">Pour activer le verrouillage du téléphone</span><span class="sxs-lookup"><span data-stu-id="1487a-127">To enable phone locking</span></span>

  - <span data-ttu-id="1487a-128">La commande suivante permet de verrouiller le téléphone pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="1487a-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="1487a-129">Pour désactiver le verrouillage du téléphone, définissez la propriété EnforcePhoneLock sur false ($False).</span><span class="sxs-lookup"><span data-stu-id="1487a-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="1487a-130">Pour activer le verrouillage du téléphone et modifier le délai de verrouillage du téléphone</span><span class="sxs-lookup"><span data-stu-id="1487a-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="1487a-131">Cette commande active le verrouillage du téléphone et définit également le délai de verrouillage du téléphone sur 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="1487a-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="1487a-132">Pour activer le verrouillage du téléphone dans l’ensemble de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="1487a-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="1487a-133">Dans cet exemple, le verrouillage du téléphone est activé sur l’ensemble des paramètres de configuration de téléphone de UC utilisés au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="1487a-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="1487a-134">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1487a-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1487a-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1487a-135">See Also</span></span>


[<span data-ttu-id="1487a-136">Gestion de l’authentification Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1487a-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="1487a-137">Gestion des appareils, des téléphones et des applications client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1487a-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

