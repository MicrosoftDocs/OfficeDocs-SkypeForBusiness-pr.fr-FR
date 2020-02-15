---
title: 'Lync Server 2013 : configuration des notifications de type transmission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92ae27b919df6a32f06921df97746680a68b030
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="d2c8a-102">Configuration des notifications de type transmission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2c8a-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c8a-103">_**Dernière modification de la rubrique :** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="d2c8a-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="d2c8a-104">Des notifications push, sous forme de badges, icônes ou alertes, peuvent être envoyées à un appareil mobile même si l’application mobile est inactive.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="d2c8a-105">Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation par messagerie instantanée nouvelle ou manquée, ou un message vocal.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="d2c8a-106">Le service de mobilité Lync Server 2013 envoie les notifications au service de notifications distribuées Lync Server basé sur un nuage, qui envoie ensuite les notifications au service de notifications d’Apple (APNS) Apple (pour un appareil Apple exécutant le client mobile Lync 2010) ou le Microsoft transmission notification service (MPNS) (pour un appareil Windows Phone exécutant Lync 2010 mobile ou le client mobile Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="d2c8a-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2c8a-107">Si vous utilisez Windows Phone avec Lync 2010 mobile ou Lync 2013 mobile client, la notification de transmission est une considération importante.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="d2c8a-108">Si vous utilisez Lync 2010 mobile sur des appareils Apple, la notification de transmission est une considération importante.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="d2c8a-109">Si vous utilisez Lync 2013 mobile sur des appareils Apple, vous n’avez plus besoin d’une notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="d2c8a-110">Vous pouvez configurer votre topologie de sorte qu’elle prenne en charge les notifications push en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="d2c8a-111">Si votre environnement comporte un serveur Edge Lync Server 2010 ou Lync Server 2013, vous devez ajouter un nouveau fournisseur d’hébergement, Microsoft Lync Online, puis configurer la Fédération des fournisseurs d’hébergement entre votre organisation et Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="d2c8a-112">Si votre environnement est doté d’un serveur Edge Office Communications Server 2007 R2, vous devez configurer la Fédération SIP directe avec push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c8a-113">Push.lync.com est un domaine Microsoft Office 365 pour le service de notifications push.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="d2c8a-114">Pour activer les notifications push, vous devez exécuter l’applet de commande **Set-CsPushNotificationConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="d2c8a-115">Par défaut, les notifications push sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="d2c8a-116">Testez la configuration de fédération et les notifications push.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="d2c8a-117">Pour configurer les notifications de type transmission avec Lync Server 2013 ou Lync Server 2010 serveur Edge</span><span class="sxs-lookup"><span data-stu-id="d2c8a-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="d2c8a-118">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du groupe RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d2c8a-119">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d2c8a-120">Ajoutez un fournisseur d’hébergement Lync Server online.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="d2c8a-121">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="d2c8a-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c8a-p104">Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Autrement dit, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-p104">You cannot have more than one federation relationship with a single hosting provider. That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="d2c8a-p105">Configurez la fédération de fournisseurs d’hébergement entre votre organisation et le service de notifications push de Lync Online. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-p105">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online. At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="d2c8a-127">Pour configurer les notifications de type transmission avec le serveur Edge Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d2c8a-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="d2c8a-128">Ouvrez une session sur le serveur Edge en tant que membre du groupe RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d2c8a-129">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Gestion de l’ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="d2c8a-130">Dans l’arborescence de la console, développez **Services et applications**, cliquez avec le bouton droit sur **Microsoft Office Communications Server 2007 R2**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="d2c8a-131">Sous l’onglet **Autoriser**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="d2c8a-132">Dans la boîte de dialogue **Ajouter un partenaire fédéré**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="d2c8a-133">Dans **Nom de domaine du partenaire fédéré**, tapez **push.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="d2c8a-134">Dans **Serveur Edge d’accès du partenaire fédéré**, tapez **sipfed.online.lync.com**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="d2c8a-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="d2c8a-136">Pour activer les notifications push</span><span class="sxs-lookup"><span data-stu-id="d2c8a-136">To enable push notifications</span></span>

1.  <span data-ttu-id="d2c8a-137">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="d2c8a-138">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d2c8a-p106">Activez les notifications push. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-p106">Enable push notifications. At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="d2c8a-p107">Activez la fédération. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-p107">Enable federation. At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="d2c8a-143">Pour tester la fédération et les notifications push</span><span class="sxs-lookup"><span data-stu-id="d2c8a-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="d2c8a-144">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="d2c8a-145">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2c8a-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d2c8a-p108">Testez la configuration de la fédération. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-p108">Test the federation configuration. At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="d2c8a-148">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="d2c8a-p109">Testez les notifications push. Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-p109">Test push notifications. At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="d2c8a-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d2c8a-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2c8a-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2c8a-152">See Also</span></span>


[<span data-ttu-id="d2c8a-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="d2c8a-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="d2c8a-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="d2c8a-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

