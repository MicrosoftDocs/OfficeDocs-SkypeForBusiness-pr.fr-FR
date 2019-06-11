---
title: 'Lync Server 2013 : Configuration des notifications push'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08492aaa6fc8c9fb6569ad6ad642a5cc1157a2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="ffef0-102">Configuration des notifications push dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffef0-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffef0-103">_**Dernière modification de la rubrique:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="ffef0-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="ffef0-104">Les notifications de transmission sous forme de badges, d’icônes ou d’alertes peuvent être envoyées à un appareil mobile même lorsque l’application mobile n’est pas active.</span><span class="sxs-lookup"><span data-stu-id="ffef0-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="ffef0-105">Les notifications de transmission avertissent un utilisateur d’événements tels qu’une invitation à la messagerie instantanée, une invitation à une nouvelle ou une messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="ffef0-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="ffef0-106">Le service de mobilité Lync Server 2013 envoie les notifications au service de notifications de transmission Lync Server via le Cloud, qui envoie ensuite les notifications au service de notifications de transmission d’Apple (APNS) (pour un appareil Apple exécutant le client mobile Lync 2010) ou le Service de notifications d’appel Microsoft (MPNS) (pour un appareil Windows Phone exécutant l’application mobile Lync 2010 ou le client mobile Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="ffef0-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ffef0-107">Si vous utilisez un téléphone Windows Phone avec Lync 2010 mobile ou Lync 2013 mobile, la notification de transmission est une considération importante.</span><span class="sxs-lookup"><span data-stu-id="ffef0-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="ffef0-108">Si vous utilisez Lync 2010 mobile sur des appareils Apple, vous devez tenir compte des notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="ffef0-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="ffef0-109">Si vous utilisez Lync 2013 mobile sur des appareils Apple, vous n’avez plus besoin d’une notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="ffef0-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="ffef0-110">Configurez votre topologie pour prendre en charge les notifications de transmission en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="ffef0-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="ffef0-111">Si votre environnement possède un serveur Edge Lync Server 2010 ou Lync Server 2013, vous devez ajouter un nouveau fournisseur d’hébergement, Microsoft Lync Online, puis configurer la Fédération des fournisseurs d’hébergement entre votre organisation et Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ffef0-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="ffef0-112">Si votre environnement possède un serveur Edge Office Communications Server 2007 R2, vous devez configurer la Fédération SIP directe avec push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ffef0-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffef0-113">Push.lync.com est un domaine Microsoft Office 365 pour le service de notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="ffef0-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="ffef0-114">Pour activer les notifications de transmission, vous devez exécuter l’applet **de cmdlet Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ffef0-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="ffef0-115">Par défaut, les notifications push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="ffef0-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="ffef0-116">Testez la configuration de la Fédération et les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="ffef0-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="ffef0-117">Pour configurer les notifications de transmission avec Lync Server 2013 ou Lync Server 2010 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ffef0-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="ffef0-118">Connectez-vous à un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du groupe RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ffef0-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="ffef0-119">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ffef0-120">Ajoutez un fournisseur d’hébergement Lync Server online.</span><span class="sxs-lookup"><span data-stu-id="ffef0-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="ffef0-121">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ffef0-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="ffef0-122">Exemple :</span><span class="sxs-lookup"><span data-stu-id="ffef0-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffef0-123">Vous ne pouvez pas avoir plusieurs relations de Fédération avec un seul fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="ffef0-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="ffef0-124">Autrement dit, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de Fédération avec sipfed.online.lync.com, n’ajoutez pas d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement n’est pas LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="ffef0-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="ffef0-125">Configurez la Fédération des fournisseurs d’hébergement entre votre organisation et le service de notifications de transmission de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ffef0-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="ffef0-126">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ffef0-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="ffef0-127">Pour configurer les notifications de transmission avec un serveur Edge Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ffef0-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="ffef0-128">Ouvrez une session sur le serveur Edge en tant que membre du groupe RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ffef0-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="ffef0-129">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur gestion de l' **ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="ffef0-130">Dans l’arborescence de la console, développez **services et applications**, cliquez avec le bouton droit sur **Microsoft Office Communications Server 2007 R2**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="ffef0-131">Dans l’onglet **autoriser** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="ffef0-132">Dans la boîte de dialogue **Ajouter un partenaire fédéré** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="ffef0-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="ffef0-133">Dans **nom de domaine du partenaire fédéré**, entrez **push.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="ffef0-134">Dans **serveur Edge d’accès du partenaire fédéré**, entrez **sipfed.online.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="ffef0-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="ffef0-136">Pour activer les notifications de transmission</span><span class="sxs-lookup"><span data-stu-id="ffef0-136">To enable push notifications</span></span>

1.  <span data-ttu-id="ffef0-137">Connectez-vous à un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ffef0-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="ffef0-138">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ffef0-139">Activez les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="ffef0-139">Enable push notifications.</span></span> <span data-ttu-id="ffef0-140">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ffef0-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="ffef0-141">Activez la Fédération.</span><span class="sxs-lookup"><span data-stu-id="ffef0-141">Enable federation.</span></span> <span data-ttu-id="ffef0-142">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ffef0-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="ffef0-143">Pour tester la Fédération et les notifications de transmission</span><span class="sxs-lookup"><span data-stu-id="ffef0-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="ffef0-144">Connectez-vous à un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ffef0-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="ffef0-145">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ffef0-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ffef0-146">Testez la configuration de la Fédération.</span><span class="sxs-lookup"><span data-stu-id="ffef0-146">Test the federation configuration.</span></span> <span data-ttu-id="ffef0-147">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ffef0-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="ffef0-148">Exemple :</span><span class="sxs-lookup"><span data-stu-id="ffef0-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="ffef0-149">Testez les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="ffef0-149">Test push notifications.</span></span> <span data-ttu-id="ffef0-150">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="ffef0-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="ffef0-151">Exemple :</span><span class="sxs-lookup"><span data-stu-id="ffef0-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ffef0-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffef0-152">See Also</span></span>


[<span data-ttu-id="ffef0-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="ffef0-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="ffef0-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="ffef0-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

