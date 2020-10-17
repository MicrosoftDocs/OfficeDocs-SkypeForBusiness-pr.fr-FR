---
title: 'Lync Server 2013 : activation ou désactivation des notifications de type transmission pour les iPhone'
description: 'Lync Server 2013 : activation ou désactivation des notifications de type transmission pour les iPhone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a9c5ec442c3628455797b987d8b2f22677e70e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546500"
---
# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="99dd3-103">Activation ou désactivation des notifications de type transmission pour les iPhone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99dd3-103">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99dd3-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="99dd3-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="99dd3-105">Les notifications de type transmission, sous la forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un iPhone même lorsque l’application mobile est inactive.</span><span class="sxs-lookup"><span data-stu-id="99dd3-105">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="99dd3-106">Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation par messagerie instantanée nouvelle ou manquée, ou un message vocal.</span><span class="sxs-lookup"><span data-stu-id="99dd3-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="99dd3-107">Vous pouvez activer ou désactiver les notifications de type transmission pour iPhone à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="99dd3-107">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="99dd3-108">Pour activer les notifications de type transmission pour iPhone à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="99dd3-108">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="99dd3-109">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="99dd3-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99dd3-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99dd3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99dd3-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99dd3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99dd3-112">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-112">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="99dd3-113">Dans la page **Configuration des notifications par émission** , cliquez sur le site que vous souhaitez modifier, cliquez sur le menu **Edition** , puis sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-113">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="99dd3-114">Cochez la case **Activer les notifications push Apple**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-114">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="99dd3-115">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="99dd3-116">Pour désactiver les notifications de type transmission pour iPhone à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="99dd3-116">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="99dd3-117">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="99dd3-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99dd3-118">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99dd3-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99dd3-119">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99dd3-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99dd3-120">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-120">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="99dd3-121">Dans la page **Configuration des notifications par émission** , cliquez sur le site que vous souhaitez modifier, cliquez sur le menu **Edition** , puis sur Afficher les **Détails**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-121">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="99dd3-122">Décochez la case **Activer les notifications push Apple**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-122">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="99dd3-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="99dd3-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="99dd3-124">Activation ou désactivation des notifications de type transmission vers iPhone à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99dd3-124">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="99dd3-125">Les notifications de type diffuser à Apple iPhone peuvent être activées ou désactivées à l’aide de la cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="99dd3-125">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="99dd3-126">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99dd3-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="99dd3-127">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="99dd3-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="99dd3-128">Pour activer les notifications de type transmission pour iPhone</span><span class="sxs-lookup"><span data-stu-id="99dd3-128">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="99dd3-129">Pour activer les notifications de type transmission pour iPhone, définissez la valeur de la propriété EnableApplePushNotificationService sur true ($True).</span><span class="sxs-lookup"><span data-stu-id="99dd3-129">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="99dd3-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="99dd3-130">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="99dd3-131">Pour désactiver les notifications de type transmission pour iPhone</span><span class="sxs-lookup"><span data-stu-id="99dd3-131">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="99dd3-132">Pour désactiver les notifications de type transmission pour iPhone, définissez la valeur de la propriété EnableApplePushNotificationService sur false ($False).</span><span class="sxs-lookup"><span data-stu-id="99dd3-132">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="99dd3-133">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="99dd3-133">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="99dd3-134">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="99dd3-134">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99dd3-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99dd3-135">See Also</span></span>


[<span data-ttu-id="99dd3-136">Configuration des notifications de type transmission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99dd3-136">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

