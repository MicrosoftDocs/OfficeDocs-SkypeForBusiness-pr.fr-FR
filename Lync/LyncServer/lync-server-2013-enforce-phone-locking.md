---
title: 'Lync Server 2013 : appliquer le verrouillage du téléphone'
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
ms.openlocfilehash: 61042ebd21786513c482f1286cd9120711d1cfb9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="aee6d-102">Appliquer le verrouillage du téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee6d-102">Enforce phone locking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aee6d-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="aee6d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="aee6d-104">Les appareils Lync Phone Edition peuvent être verrouillés à des fins de sécurité.</span><span class="sxs-lookup"><span data-stu-id="aee6d-104">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="aee6d-105">Si vous appliquez un verrou téléphonique, l’appareil exécutant Lync Phone Edition se bloque après un laps de temps que vous configurez.</span><span class="sxs-lookup"><span data-stu-id="aee6d-105">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="aee6d-106">Lorsqu’un téléphone est verrouillé, un utilisateur peut passer des appels mais ne peut pas accéder aux informations de calendrier et de contact, à la messagerie vocale, ni aux journaux d’appels ou utiliser la recherche.</span><span class="sxs-lookup"><span data-stu-id="aee6d-106">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="aee6d-107">Pour déverrouiller le téléphone, l’utilisateur entre un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="aee6d-107">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="aee6d-108">Pour appliquer un verrou téléphonique, activez-le et configurez-le à l’aide du panneau de configuration Lync Server ou des applets de commande Lync Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aee6d-108">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="aee6d-109">Vous pouvez appliquer un verrouillage téléphonique global ou uniquement au sein du site pour lequel il est configuré.</span><span class="sxs-lookup"><span data-stu-id="aee6d-109">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="aee6d-110">Pour configurer et appliquer le verrou téléphonique</span><span class="sxs-lookup"><span data-stu-id="aee6d-110">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="aee6d-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aee6d-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aee6d-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee6d-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aee6d-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aee6d-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aee6d-114">Cliquez sur **Clients**, puis sur **Configuration du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="aee6d-114">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="aee6d-115">Sous l’onglet **Configuration du périphérique**, dans la liste des configurations possibles, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de verrouillage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="aee6d-115">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="aee6d-116">Dans la boîte de dialogue **Modifier la configuration du périphérique**, vérifiez que la case à cocher **Appliquer le verrouillage de l’appareil** est activée.</span><span class="sxs-lookup"><span data-stu-id="aee6d-116">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="aee6d-117">Dans **longueur minimale du code confidentiel**, acceptez la valeur par défaut pour le nombre minimal de chiffres que le code confidentiel de déverrouillage doit contenir ou spécifiez une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="aee6d-117">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="aee6d-118">La plage de longueur du code confidentiel est comprise entre quatre et 15 chiffres, et la valeur par défaut est six.</span><span class="sxs-lookup"><span data-stu-id="aee6d-118">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="aee6d-119">Dans **délai d’expiration du verrouillage du téléphone**, acceptez la valeur par défaut pour la durée minimale avant le blocage du téléphone ou spécifiez une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="aee6d-119">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="aee6d-120">La plage du délai d’attente est comprise entre 0 et 60 minutes, et la valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="aee6d-120">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="aee6d-121">Le format de cette valeur est HH:MM:SS.</span><span class="sxs-lookup"><span data-stu-id="aee6d-121">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="aee6d-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="aee6d-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aee6d-123">Application du verrouillage de téléphone à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aee6d-123">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aee6d-124">Le verrouillage du téléphone peut être appliqué à l’aide de la cmdlet Set-CsUCPhoneConfiguration.</span><span class="sxs-lookup"><span data-stu-id="aee6d-124">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="aee6d-125">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aee6d-125">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aee6d-126">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="aee6d-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="aee6d-127">Pour activer le verrouillage du téléphone</span><span class="sxs-lookup"><span data-stu-id="aee6d-127">To enable phone locking</span></span>

  - <span data-ttu-id="aee6d-128">La commande suivante active le verrouillage du téléphone sur le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="aee6d-128">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="aee6d-129">Pour désactiver le verrouillage du téléphone, attribuez à la propriété EnforcePhoneLock la valeur Faux ($False).</span><span class="sxs-lookup"><span data-stu-id="aee6d-129">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="aee6d-130">Pour activer le verrouillage du téléphone et modifier le délai d’expiration du verrouillage du téléphone</span><span class="sxs-lookup"><span data-stu-id="aee6d-130">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="aee6d-131">Cette commande active le verrouillage du téléphone et définit également le délai d’expiration du verrouillage sur 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="aee6d-131">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="aee6d-132">Pour activer le verrouillage du téléphone au sein de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="aee6d-132">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="aee6d-133">Dans cet exemple, le verrouillage du téléphone est activé sur les paramètres de configuration de tous les téléphones UC utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="aee6d-133">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="aee6d-134">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="aee6d-134">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aee6d-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aee6d-135">See Also</span></span>


[<span data-ttu-id="aee6d-136">Gestion de l’authentification Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee6d-136">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="aee6d-137">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee6d-137">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

