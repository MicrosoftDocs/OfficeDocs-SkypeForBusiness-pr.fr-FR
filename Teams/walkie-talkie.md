---
title: Application Talkie-walkie dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Configuration de l’application Talkie-walkie Microsoft Teams du point de vue ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479071"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="a5247-103">Application Talkie-walkie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a5247-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="a5247-104">L’application Talkie-walkie Teams propose des communications PTT (Instant Push-to-Talk) pour votre équipe et est désormais disponible sur Android.</span><span class="sxs-lookup"><span data-stu-id="a5247-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="a5247-105">Le Talkie-walkie permet aux utilisateurs de se connecter à leur équipe en utilisant les mêmes canaux sous-jacents que ceux dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="a5247-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="a5247-106">Seuls les utilisateurs qui se connectent au Talkie-walkie dans un canal deviennent des participants et peuvent communiquer entre eux par push-to-talk, un par un.</span><span class="sxs-lookup"><span data-stu-id="a5247-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="a5247-107">Grâce au Talkie-walkie de Teams, les employés en avant-plan peuvent désormais communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Talkie-walkie fonctionne en tout lieu avec le WiFi ou la connectivité Internet cellulaire.</span><span class="sxs-lookup"><span data-stu-id="a5247-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="a5247-108">Prise en main</span><span class="sxs-lookup"><span data-stu-id="a5247-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="a5247-109">Déploiement de Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="a5247-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="a5247-110">Actuellement, le Talkie-walkie est disponible pour les appareils Android avec Google Mobile Services (GMS) et n’est pas préinstallé.</span><span class="sxs-lookup"><span data-stu-id="a5247-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="a5247-111">Pour activer cette fonctionnalité pour les utilisateurs de votre organisation, vous devez ajouter le Talkie-walkie à la stratégie de configuration d’application qui est affectée aux utilisateurs à partir du Centre [](teams-app-setup-policies.md)   [Teams’administration.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="a5247-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="a5247-112">Une fois activée, le Talkie-walkie sera disponible sur l’application Android dans les 48 heures.</span><span class="sxs-lookup"><span data-stu-id="a5247-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="a5247-113">Ajout d’un Talkie-walkie à votre liste d’applications</span><span class="sxs-lookup"><span data-stu-id="a5247-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="a5247-114">Dans le centre Microsoft Teams d’administration, sous Teams d’installation de l’application, vous devez définir l’accès à l’épinglage utilisateur   >  sur **On.** </span><span class="sxs-lookup"><span data-stu-id="a5247-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="a5247-115">Sous la section Applications épinglées, cliquez **sur +Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="a5247-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Section Applications épinglées et bouton Ajouter des applications à sélectionner.":::

<span data-ttu-id="a5247-117">Dans le **panneau Ajouter des applications épinglées** qui apparaît à droite, utilisez la zone de texte Rechercher pour rechercher talkie-walkie. </span><span class="sxs-lookup"><span data-stu-id="a5247-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="a5247-118">Lorsque vous l’avez comme résultat  de recherche, sélectionnez le bouton Ajouter à droite du nom pour l’ajouter à votre liste.</span><span class="sxs-lookup"><span data-stu-id="a5247-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Affiche la barre latérale Ajouter des applications épinglées avec le walkie entré dans le volet de recherche et l’application Talkie-walkie dans les résultats de recherche, avec le bouton Ajouter à côté.":::

<span data-ttu-id="a5247-120">L’application Talkie-walkie doit maintenant apparaître dans la liste Applications épinglées et peut être utilisé une fois que vous cliquez sur **le bouton** Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a5247-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Affiche la liste des applications épinglées avec l’application Talkie-walkie ajoutée et le bouton Enregistrer sous la liste.":::

### <a name="network-documentation"></a><span data-ttu-id="a5247-122">Documentation réseau</span><span class="sxs-lookup"><span data-stu-id="a5247-122">Network documentation</span></span>

<span data-ttu-id="a5247-123">Le Talkie-walkie Teams nécessite une connectivité Internet. En dessous des conditions réseau, une expérience optimale est requise.</span><span class="sxs-lookup"><span data-stu-id="a5247-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="a5247-124">Mesure</span><span class="sxs-lookup"><span data-stu-id="a5247-124">Metric</span></span> | <span data-ttu-id="a5247-125">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a5247-125">Required</span></span> |
|---|---|
|<span data-ttu-id="a5247-126">Latence (RTT)</span><span class="sxs-lookup"><span data-stu-id="a5247-126">Latency (RTT)</span></span> | <span data-ttu-id="a5247-127">< 300 ms</span><span class="sxs-lookup"><span data-stu-id="a5247-127">< 300ms</span></span> |
|<span data-ttu-id="a5247-128">Jitter</span><span class="sxs-lookup"><span data-stu-id="a5247-128">Jitter</span></span> |<span data-ttu-id="a5247-129">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="a5247-129">< 30ms</span></span> |
|<span data-ttu-id="a5247-130">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="a5247-130">Packet Loss</span></span> |<span data-ttu-id="a5247-131">< 1 %</span><span class="sxs-lookup"><span data-stu-id="a5247-131">< 1%</span></span> |

<span data-ttu-id="a5247-132">Comme indiqué ci-dessus, la qualité des médias en temps réel sur un réseau IP est largement impactée par la qualité de la connectivité du réseau, mais surtout par la quantité de :</span><span class="sxs-lookup"><span data-stu-id="a5247-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="a5247-133">**Latence** - Il s’agit du temps que prend l’accès d’un paquet IP d’un point A à un point B sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a5247-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="a5247-134">Ce retard de propagation sur le réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, ce qui comprend une surcharge des divers routeurs entre les deux.</span><span class="sxs-lookup"><span data-stu-id="a5247-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="a5247-135">La latence se mesure en durée de l’aller-retour (Round-trip Time, RTT).</span><span class="sxs-lookup"><span data-stu-id="a5247-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="a5247-136">**Gigue entre les arrivées** : il s’agit de la variation moyenne de délai entre les paquets successifs.</span><span class="sxs-lookup"><span data-stu-id="a5247-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="a5247-137">**Perte de paquets** - Souvent définie comme le pourcentage de paquets perdus dans une période donnée.</span><span class="sxs-lookup"><span data-stu-id="a5247-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="a5247-138">La perte de paquets affecte directement la qualité audio, de petits paquets individuels perdus, pratiquement sans impact, aux pertes en rafale dos-à-dos à l’origine de coupures audio complètes.</span><span class="sxs-lookup"><span data-stu-id="a5247-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="a5247-139">L’utilisation attendue des données de Talkie-walkie est d’environ 20 Ko lors de l’envoi ou de la réception d’audio.</span><span class="sxs-lookup"><span data-stu-id="a5247-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="a5247-140">Lorsqu’elles sont inactives, l’utilisation attendue des données de Talkie-walkie est en veille.</span><span class="sxs-lookup"><span data-stu-id="a5247-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="a5247-141">Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="a5247-141">Walkie Talkie devices</span></span>

<span data-ttu-id="a5247-142">Les employés en ligne doivent souvent parler et recevoir des appels Walkie Talkie même lorsque leur téléphone est verrouillé.</span><span class="sxs-lookup"><span data-stu-id="a5247-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="a5247-143">Cette expérience est possible via des appareils spécialisés avec un bouton PTT dédié.</span><span class="sxs-lookup"><span data-stu-id="a5247-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="a5247-144">**Casques**</span><span class="sxs-lookup"><span data-stu-id="a5247-144">**Headsets**</span></span>
  - <span data-ttu-id="a5247-145">Casques sans fil</span><span class="sxs-lookup"><span data-stu-id="a5247-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="a5247-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="a5247-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="a5247-147">Casques câblés</span><span class="sxs-lookup"><span data-stu-id="a5247-147">Wired headsets</span></span> 
    - [<span data-ttu-id="a5247-148">Tous les ans!</span><span class="sxs-lookup"><span data-stu-id="a5247-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="a5247-149">**Téléphones accidentés**</span><span class="sxs-lookup"><span data-stu-id="a5247-149">**Rugged phones**</span></span>
  - <span data-ttu-id="a5247-150">Samsung [Galaxy XCover Pro,](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/) [Galaxy XCover 5,](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy) [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="a5247-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="a5247-151">Configuration manuelle : une fois Teams, accédez aux fonctionnalités Paramètres > avancées > XCover/Active.</span><span class="sxs-lookup"><span data-stu-id="a5247-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="a5247-152">Activer « Touche Contrôle XCover avec l’application » et sélectionner « Teams »</span><span class="sxs-lookup"><span data-stu-id="a5247-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="a5247-153">Configuration de la gestion des mdm</span><span class="sxs-lookup"><span data-stu-id="a5247-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="a5247-154">Ces appareils ne sont pas Teams certifiés.</span><span class="sxs-lookup"><span data-stu-id="a5247-154">These devices are not Teams certified.</span></span> <span data-ttu-id="a5247-155">Ils ont été validés pour fonctionner avec Teams Talkie-walkie.</span><span class="sxs-lookup"><span data-stu-id="a5247-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="a5247-156">Conditions de licence requises</span><span class="sxs-lookup"><span data-stu-id="a5247-156">License requirements</span></span>

<span data-ttu-id="a5247-157">L’application Talkie-walkie est incluse dans toutes les licences payantes des Teams dans [Office 365 abonnements.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="a5247-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="a5247-158">Pour plus d’informations sur Teams' accès, consultez comment accéder [à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="a5247-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="a5247-159">Certaines fonctionnalités avancées peuvent nécessiter des licences supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a5247-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="a5247-160">Par exemple, l’intégration avec le Samsung Galaxy XCover Pro nécessite une licence Knox.</span><span class="sxs-lookup"><span data-stu-id="a5247-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="a5247-161">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="a5247-161">Further information</span></span>

- <span data-ttu-id="a5247-162">Les itAdmins peuvent contrôler les personnes qui utilisent talkie-walkie via les stratégies d’application.</span><span class="sxs-lookup"><span data-stu-id="a5247-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="a5247-163">Si votre collègue en première ligne utilise des données mobiles pour communiquer via Teams, talkie-walkie utilisera la même méthode.</span><span class="sxs-lookup"><span data-stu-id="a5247-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="a5247-164">Le Talkie-walkie doit fonctionner bien dans les situations de faible bande passante, ou dans les situations où votre smartphone est connecté et fonctionne.</span><span class="sxs-lookup"><span data-stu-id="a5247-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="a5247-165">Le Talkie-walkie ne fonctionne pas lorsqu’il n’y a aucune connexion.</span><span class="sxs-lookup"><span data-stu-id="a5247-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="a5247-166">Pour plus d’informations sur l’expérience utilisateur final, voir :</span><span class="sxs-lookup"><span data-stu-id="a5247-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="a5247-167">Commencer à travailler avec Teams Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="a5247-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="a5247-168">Communiquer avec votre équipe grâce au Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="a5247-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
