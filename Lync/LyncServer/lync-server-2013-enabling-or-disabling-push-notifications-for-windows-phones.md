---
title: 'Lync Server 2013 : activation ou désactivation des notifications de transmission pour les téléphones Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="4b775-102">Activation ou désactivation des notifications de transmission pour les téléphones Windows dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b775-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b775-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4b775-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4b775-104">Les notifications de transmission sous forme de badges, d’icônes ou d’alertes peuvent être envoyées à un Windows Phone même lorsque l’application mobile n’est pas active.</span><span class="sxs-lookup"><span data-stu-id="4b775-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="4b775-105">Les notifications de transmission avertissent un utilisateur d’événements tels qu’une invitation à la messagerie instantanée, une invitation à une nouvelle ou une messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4b775-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="4b775-106">Vous pouvez activer ou désactiver les notifications de transmission pour les appareils Windows Phone à l’aide de Lync Server 2013 Control Panel ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4b775-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="4b775-107">Pour activer les notifications de transmission pour Windows Phone à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="4b775-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4b775-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4b775-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b775-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b775-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b775-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4b775-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b775-111">Dans la barre de navigation gauche, cliquez sur **clients**, puis sur le bouton de navigation **configuration de notifications de transmission** .</span><span class="sxs-lookup"><span data-stu-id="4b775-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4b775-112">Dans la page **configuration de notifications de transmission** , cliquez sur le site que vous voulez modifier, cliquez sur le menu **modifier** , puis cliquez sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="4b775-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4b775-113">Activez la case à cocher **activer les notifications de transmission Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="4b775-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="4b775-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4b775-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="4b775-115">Pour désactiver les notifications de transmission pour Windows Phone à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="4b775-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4b775-116">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4b775-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b775-117">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b775-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b775-118">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4b775-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b775-119">Dans la barre de navigation gauche, cliquez sur **clients**, puis sur le bouton de navigation **configuration de notifications de transmission** .</span><span class="sxs-lookup"><span data-stu-id="4b775-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4b775-120">Dans la page **configuration de notifications de transmission** , cliquez sur le site que vous voulez modifier, cliquez sur le menu **modifier** , puis cliquez sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="4b775-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4b775-121">Décochez la case **activer les notifications de transmission de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="4b775-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="4b775-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4b775-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4b775-123">Activation ou désactivation des notifications de transmission pour Windows Phone à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b775-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4b775-124">Vous pouvez activer ou désactiver les notifications de transmission pour Windows Phone à l’aide de la cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4b775-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="4b775-125">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b775-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4b775-126">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="4b775-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="4b775-127">Pour activer les notifications de transmission pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="4b775-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="4b775-128">Pour activer les notifications de transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur true ($True).</span><span class="sxs-lookup"><span data-stu-id="4b775-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="4b775-129">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4b775-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="4b775-130">Pour désactiver les notifications de transmission pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="4b775-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="4b775-131">Pour désactiver les notifications de transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur false ($False).</span><span class="sxs-lookup"><span data-stu-id="4b775-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="4b775-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4b775-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="4b775-133">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4b775-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b775-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b775-134">See Also</span></span>


[<span data-ttu-id="4b775-135">Configuration des notifications push dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b775-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

