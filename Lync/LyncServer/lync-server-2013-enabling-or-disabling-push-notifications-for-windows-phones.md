---
title: 'Lync Server 2013 : activation ou désactivation des notifications de type transmission pour les téléphones Windows'
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
ms.openlocfilehash: e4bcf8ccda422468416ae4c0b486e2e224b17f9f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515471"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="898ac-102">Activation ou désactivation des notifications de type transmission pour les téléphones Windows dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="898ac-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="898ac-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="898ac-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="898ac-104">Les notifications de type transmission, sous la forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un téléphone Windows même lorsque l’application mobile est inactive.</span><span class="sxs-lookup"><span data-stu-id="898ac-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="898ac-105">Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation par messagerie instantanée nouvelle ou manquée, ou un message vocal.</span><span class="sxs-lookup"><span data-stu-id="898ac-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="898ac-106">Vous pouvez activer ou désactiver les notifications de type transmission pour les appareils Windows Phone à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="898ac-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="898ac-107">Pour activer les notifications de type transmission pour Windows Phone à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="898ac-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="898ac-108">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="898ac-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="898ac-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="898ac-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="898ac-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="898ac-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="898ac-111">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.</span><span class="sxs-lookup"><span data-stu-id="898ac-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="898ac-112">Dans la page **Configuration des notifications par émission** , cliquez sur le site que vous souhaitez modifier, cliquez sur le menu **Edition** , puis sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="898ac-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="898ac-113">Activez la case à cocher **Activer les notifications push Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="898ac-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="898ac-114">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="898ac-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="898ac-115">Pour désactiver les notifications de type transmission pour Windows Phone à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="898ac-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="898ac-116">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="898ac-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="898ac-117">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="898ac-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="898ac-118">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="898ac-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="898ac-119">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.</span><span class="sxs-lookup"><span data-stu-id="898ac-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="898ac-120">Dans la page **Configuration des notifications par émission** , cliquez sur le site que vous souhaitez modifier, cliquez sur le menu **Edition** , puis sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="898ac-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="898ac-121">Désactivez la case à cocher **Activer les notifications push Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="898ac-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="898ac-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="898ac-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="898ac-123">Activation ou désactivation des notifications de type transmission pour Windows Phone à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="898ac-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="898ac-124">Vous pouvez activer ou désactiver les notifications de type transmission pour Windows Phone à l’aide de la cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="898ac-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="898ac-125">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="898ac-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="898ac-126">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="898ac-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="898ac-127">Pour activer les notifications de type transmission pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="898ac-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="898ac-128">Pour activer les notifications de type transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur true ($True).</span><span class="sxs-lookup"><span data-stu-id="898ac-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="898ac-129">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="898ac-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="898ac-130">Pour désactiver les notifications de type transmission pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="898ac-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="898ac-131">Pour désactiver les notifications de type transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur false ($False).</span><span class="sxs-lookup"><span data-stu-id="898ac-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="898ac-132">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="898ac-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="898ac-133">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="898ac-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="898ac-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="898ac-134">See Also</span></span>


[<span data-ttu-id="898ac-135">Configuration des notifications de type transmission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="898ac-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

