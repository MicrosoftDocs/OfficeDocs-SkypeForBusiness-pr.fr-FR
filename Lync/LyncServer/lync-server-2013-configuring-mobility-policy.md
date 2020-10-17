---
title: 'Lync Server 2013 : configuration de la stratégie de mobilité'
description: 'Lync Server 2013 : configuration de la stratégie de mobilité.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbbf7f9db54c8436f2db24d593dbd7a1372d5e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570000"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="f562b-103">Configuration de la stratégie de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f562b-103">Configuring mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f562b-104">_**Dernière modification de la rubrique :** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="f562b-104">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="f562b-105">Lync Server 2013 fournit des stratégies de mobilité qui déterminent qui peut utiliser les fonctionnalités de mobilité, l’appel via le bureau, la voix sur IP (VoIP) ou la vidéo, et si WiFi est requis pour la voix ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="f562b-105">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="f562b-106">La fonctionnalité appeler via le bureau permet à un utilisateur mobile de passer et de recevoir des appels sur un téléphone mobile en utilisant un numéro de téléphone professionnel au lieu du numéro de téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="f562b-106">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="f562b-107">Cette fonctionnalité empêche la partie appelée de voir le numéro de téléphone mobile de l’appelant et permet à un utilisateur d’éviter les frais d’appels sortants.</span><span class="sxs-lookup"><span data-stu-id="f562b-107">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="f562b-108">La configuration de la VoIP et de la vidéo permet aux utilisateurs de recevoir et de passer des appels VoIP et de vidéo.</span><span class="sxs-lookup"><span data-stu-id="f562b-108">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="f562b-109">Paramètres d’utilisation de WiFi définissez si l’appareil d’un utilisateur doit utiliser un réseau WiFi sur un réseau de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="f562b-109">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="f562b-110">Par défaut, la mobilité, l’appel via le bureau et les fonctionnalités VoIP et vidéo sont activées.</span><span class="sxs-lookup"><span data-stu-id="f562b-110">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="f562b-111">Les paramètres permettant d’exiger WiFi pour VoIp et vidéo sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="f562b-111">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="f562b-112">Les administrateurs peuvent déterminer qui a accès à ces fonctionnalités en exécutant une applet de commande.</span><span class="sxs-lookup"><span data-stu-id="f562b-112">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="f562b-113">Il est possible de désactiver les options globalement, par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f562b-113">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="f562b-114">Pour pouvoir utiliser les fonctionnalités de mobilité et d’Appel via le bureau, les utilisateurs doivent remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="f562b-114">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="f562b-115">Les utilisateurs doivent être activés pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f562b-115">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="f562b-116">les utilisateurs doivent être activés pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f562b-116">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="f562b-117">une stratégie de mobilité dont l’option **EnableMobility** a la valeur True doit être assignée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f562b-117">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="f562b-118">Pour pouvoir utiliser la fonctionnalité d’Appel via le bureau, les utilisateurs doivent remplir les deux conditions supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="f562b-118">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="f562b-119">une stratégie de voix ayant l’option **Activer la sonnerie simultanée de téléphones** activée doit être assignée aux utilisateurs ;</span><span class="sxs-lookup"><span data-stu-id="f562b-119">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="f562b-120">une stratégie de mobilité dont l’option **EnableOutsideVoice** a la valeur True doit être assignée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f562b-120">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f562b-121">Les utilisateurs qui ne sont pas activés pour voix entreprise peuvent utiliser leurs appareils mobiles pour passer des appels Lync à Lync VoIP (voix sur IP) ou participer à des conférences en utilisant le lien Cliquer pour rejoindre les appareils mobiles, si vous leur attribuez les options appropriées pour la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="f562b-121">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="f562b-122">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-defining-your-mobility-requirements.md">la rubrique définition de vos besoins de mobilité pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f562b-122">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f562b-123">Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, reportez-vous à la rubrique désactiver ou réactiver [le compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="f562b-123">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="f562b-124">Pour plus d’informations sur l’activation des utilisateurs pour voix entreprise, consultez la rubrique [activation des utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="f562b-124">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="f562b-125">Pour plus d’informations sur la configuration des options de stratégie de voix, voir [modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="f562b-125">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="f562b-126">Pour modifier la stratégie de mobilité globale</span><span class="sxs-lookup"><span data-stu-id="f562b-126">To modify global mobility policy</span></span>

1.  <span data-ttu-id="f562b-127">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f562b-127">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f562b-128">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f562b-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f562b-p105">Désactivez globalement l’accès à la mobilité et l’Appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="f562b-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f562b-p106">Vous pouvez désactiver l’Appel via le bureau sans désactiver l’accès à la mobilité. En revanche, il est impossible de désactiver la mobilité sans également désactiver l’Appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="f562b-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="f562b-133">Pour modifier la stratégie de mobilité par site</span><span class="sxs-lookup"><span data-stu-id="f562b-133">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="f562b-134">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f562b-134">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f562b-135">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f562b-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f562b-136">Créez une stratégie au niveau du site, puis désactivez VoIP et la vidéo, et activez l’entrée « WiFi » pour l’audio IP et la vidéo IP par site.</span><span class="sxs-lookup"><span data-stu-id="f562b-136">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="f562b-137">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f562b-137">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="f562b-138">Pour modifier la stratégie de mobilité par utilisateur</span><span class="sxs-lookup"><span data-stu-id="f562b-138">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="f562b-139">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f562b-139">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="f562b-140">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f562b-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f562b-p108">Créez des stratégies de mobilité au niveau de l’utilisateur et désactivez la mobilité et l’Appel via le bureau par utilisateur. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="f562b-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="f562b-p109">Vous pouvez désactiver l’Appel via le bureau sans désactiver l’accès à la mobilité. En revanche, il est impossible de désactiver la mobilité sans également désactiver l’Appel via le bureau.</span><span class="sxs-lookup"><span data-stu-id="f562b-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="f562b-145">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f562b-145">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f562b-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f562b-146">See Also</span></span>


[<span data-ttu-id="f562b-147">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f562b-147">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="f562b-148">Activer les utilisateurs pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f562b-148">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="f562b-149">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f562b-149">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="f562b-150">Définition de la configuration requise pour la mobilité pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f562b-150">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="f562b-151">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f562b-151">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="f562b-152">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f562b-152">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="f562b-153">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f562b-153">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="f562b-154">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f562b-154">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="f562b-155">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f562b-155">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

