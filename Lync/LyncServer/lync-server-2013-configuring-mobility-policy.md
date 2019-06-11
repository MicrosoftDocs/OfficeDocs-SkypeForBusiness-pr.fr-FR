---
title: 'Lync Server 2013 : Configuration de la stratégie de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="48c5a-102">Configuration de la stratégie de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c5a-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c5a-103">_**Dernière modification de la rubrique:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="48c5a-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="48c5a-104">Lync Server 2013 fournit des stratégies de mobilité qui déterminent qui peut utiliser les fonctionnalités de mobilité, les appels via le bureau, la voix sur IP (VoIP) ou la vidéo, et si l’accès WiFi est requis pour les appels VoIP ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="48c5a-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="48c5a-105">La fonction d’appel via le bureau permet à un utilisateur mobile de passer et de recevoir des appels sur un téléphone mobile en utilisant un numéro de téléphone professionnel à la place du numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="48c5a-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="48c5a-106">Cette fonctionnalité empêche la partie appelée de voir le numéro de téléphone mobile de l’appelant et permet à un utilisateur d’éviter les frais d’appel sortants.</span><span class="sxs-lookup"><span data-stu-id="48c5a-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="48c5a-107">La configuration de VoIP et de la vidéo permet aux utilisateurs de recevoir et de passer des appels et de la vidéo VoIP.</span><span class="sxs-lookup"><span data-stu-id="48c5a-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="48c5a-108">Paramètres de l’utilisation WiFi définit si l’appareil d’un utilisateur est tenu d’utiliser un réseau WiFi sur un réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="48c5a-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="48c5a-109">Par défaut, la mobilité, les appels via le bureau et les fonctions VoIP et vidéo sont activées.</span><span class="sxs-lookup"><span data-stu-id="48c5a-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="48c5a-110">Les paramètres permettant d’exiger le Wi-Fi pour les appels voix et vidéo sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="48c5a-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="48c5a-111">Les administrateurs peuvent déterminer qui a accès à ces fonctionnalités en exécutant une cmdlet.</span><span class="sxs-lookup"><span data-stu-id="48c5a-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="48c5a-112">Vous pouvez désactiver les options dans le monde entier, par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48c5a-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="48c5a-113">Pour pouvoir utiliser les fonctionnalités de mobilité et l’appel via le bureau, les utilisateurs doivent respecter les conditions préalables suivantes:</span><span class="sxs-lookup"><span data-stu-id="48c5a-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="48c5a-114">Les utilisateurs doivent être activés pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48c5a-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="48c5a-115">Les utilisateurs doivent être activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="48c5a-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="48c5a-116">Une stratégie de mobilité doit être affectée aux utilisateurs et l’option **EnableMobility** est définie sur true.</span><span class="sxs-lookup"><span data-stu-id="48c5a-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="48c5a-117">Pour que les utilisateurs puissent utiliser un appel via le bureau, ils doivent respecter les deux conditions préalables supplémentaires suivantes:</span><span class="sxs-lookup"><span data-stu-id="48c5a-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="48c5a-118">Les utilisateurs doivent être disposant d’une politique vocale dont l’option **activer la sonnerie simultanée des téléphones** est activée.</span><span class="sxs-lookup"><span data-stu-id="48c5a-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="48c5a-119">Une stratégie de mobilité doit être affectée aux utilisateurs et l’option **EnableOutsideVoice** est définie sur true.</span><span class="sxs-lookup"><span data-stu-id="48c5a-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48c5a-120">Les utilisateurs qui ne sont pas activés pour voix entreprise peuvent utiliser leurs appareils mobiles pour passer des appels voix sur IP (VoIP) Lync vers Lync ou participer à des conférences à l’aide du lien Cliquer pour rejoindre sur leurs appareils mobiles, si vous attribuez ces utilisateurs aux options appropriées pour la politique vocale.</span><span class="sxs-lookup"><span data-stu-id="48c5a-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="48c5a-121">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-defining-your-mobility-requirements.md">définition de vos exigences de mobilité pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48c5a-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="48c5a-122">Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, voir [désactiver ou réactiver un compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="48c5a-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="48c5a-123">Pour plus d’informations sur l’activation des utilisateurs pour Enterprise Voice, voir [activer les utilisateurs d’Enterprise Voice dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="48c5a-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="48c5a-124">Pour plus d’informations sur la configuration des options de stratégie vocale, voir [modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="48c5a-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="48c5a-125">Pour modifier la stratégie de mobilité globale</span><span class="sxs-lookup"><span data-stu-id="48c5a-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="48c5a-126">Ouvrez une session sur n’importe quel ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48c5a-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="48c5a-127">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48c5a-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="48c5a-128">Désactivez l’accès à la mobilité et aux appels via votre bureau.</span><span class="sxs-lookup"><span data-stu-id="48c5a-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="48c5a-129">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="48c5a-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48c5a-130">Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="48c5a-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="48c5a-131">Toutefois, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="48c5a-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="48c5a-132">Pour modifier la stratégie de mobilité par site</span><span class="sxs-lookup"><span data-stu-id="48c5a-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="48c5a-133">Ouvrez une session sur n’importe quel ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48c5a-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="48c5a-134">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48c5a-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="48c5a-135">Créez une stratégie de niveau de site, puis désactivez VoIP et la vidéo, et activez l’option exiger une connexion audio et vidéo par site.</span><span class="sxs-lookup"><span data-stu-id="48c5a-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="48c5a-136">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="48c5a-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="48c5a-137">Pour modifier la stratégie de mobilité par utilisateur</span><span class="sxs-lookup"><span data-stu-id="48c5a-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="48c5a-138">Ouvrez une session sur n’importe quel ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48c5a-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="48c5a-139">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48c5a-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="48c5a-140">Créez des stratégies de mobilité au niveau utilisateur, puis désactivez la mobilité et les appels via votre bureau.</span><span class="sxs-lookup"><span data-stu-id="48c5a-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="48c5a-141">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="48c5a-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="48c5a-142">Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité.</span><span class="sxs-lookup"><span data-stu-id="48c5a-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="48c5a-143">Toutefois, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="48c5a-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="48c5a-144">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="48c5a-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48c5a-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48c5a-145">See Also</span></span>


[<span data-ttu-id="48c5a-146">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c5a-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="48c5a-147">Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c5a-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="48c5a-148">Modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c5a-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="48c5a-149">Définition de la configuration requise pour la mobilité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c5a-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="48c5a-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="48c5a-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="48c5a-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="48c5a-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="48c5a-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="48c5a-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="48c5a-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="48c5a-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="48c5a-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="48c5a-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

