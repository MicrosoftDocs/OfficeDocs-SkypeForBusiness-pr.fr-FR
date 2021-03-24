---
title: Application Talkie-walkie dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Comment configurer l’application Talkie-walkie dans Microsoft Teams, du point de vue ITAdmin.
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
ms.openlocfilehash: 90d5135196de9ecf62085e88053d80299b6e5a58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097460"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="67cdd-103">Application Talkie-walkie dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67cdd-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="67cdd-104">L’application Talkie-walkie de Teams fournit une communication ptT (Instant Push-to Talk) pour votre équipe et est désormais disponible sur Android.</span><span class="sxs-lookup"><span data-stu-id="67cdd-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="67cdd-105">Le Talkie-walkie permet aux utilisateurs de se connecter à leur équipe en utilisant les mêmes canaux sous-jacents que ceux dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="67cdd-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="67cdd-106">Seuls les utilisateurs qui se connectent au Talkie-walkie dans un canal deviennent des participants et peuvent communiquer entre eux par push-to-talk, un par un.</span><span class="sxs-lookup"><span data-stu-id="67cdd-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="67cdd-107">Grâce au Talkie-walkie dans Teams, les employés en ligne peuvent désormais communiquer en toute sécurité avec une expérience PTT familière sans avoir à transporter des radios volumineuses, et Talkie-walkie fonctionne en tout lieu avec une connexion WiFi ou Internet cellulaire.</span><span class="sxs-lookup"><span data-stu-id="67cdd-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="67cdd-108">Prise en main</span><span class="sxs-lookup"><span data-stu-id="67cdd-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="67cdd-109">Déploiement de Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="67cdd-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="67cdd-110">Actuellement, le Talkie-walkie n’est pas préinstallé.</span><span class="sxs-lookup"><span data-stu-id="67cdd-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="67cdd-111">Pour activer cette fonctionnalité pour les utilisateurs de votre organisation, vous devez ajouter le Talkie-walkie à la stratégie de configuration d’application qui est affectée aux utilisateurs à partir du Centre d’administration [](teams-app-setup-policies.md)   [Teams.](https://admin.teams.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="67cdd-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="67cdd-112">Une fois activée, le Talkie-walkie sera disponible sur l’application Android dans les 48 heures.</span><span class="sxs-lookup"><span data-stu-id="67cdd-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="67cdd-113">Ajout d’un Talkie-walkie à votre liste d’applications</span><span class="sxs-lookup"><span data-stu-id="67cdd-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="67cdd-114">Dans le Centre d’administration Microsoft Teams, sous Stratégies de configuration de l’application **Teams,** vous devez avoir configuré  >  l’épinglage utilisateur sur **On.** </span><span class="sxs-lookup"><span data-stu-id="67cdd-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="67cdd-115">Sous la section Applications épinglées, cliquez **sur +Ajouter des applications.**</span><span class="sxs-lookup"><span data-stu-id="67cdd-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Section Applications épinglées et bouton Ajouter des applications à sélectionner.":::

<span data-ttu-id="67cdd-117">Dans le **panneau Ajouter des applications épinglées** qui apparaît à droite, utilisez la zone de texte Rechercher pour rechercher talkie-walkie. </span><span class="sxs-lookup"><span data-stu-id="67cdd-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="67cdd-118">Lorsque vous l’avez comme résultat  de recherche, sélectionnez le bouton Ajouter à droite du nom pour l’ajouter à votre liste.</span><span class="sxs-lookup"><span data-stu-id="67cdd-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Affiche la barre latérale Ajouter des applications épinglées avec le walkie entré dans le volet de recherche et l’application Talkie-walkie dans les résultats de recherche, avec le bouton Ajouter à côté.":::

<span data-ttu-id="67cdd-120">L’application Talkie-walkie doit maintenant apparaître dans la liste Applications épinglées et peut être utilisé une fois que vous cliquez sur **le bouton** Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="67cdd-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Affiche la liste des applications épinglées avec l’application Talkie-walkie ajoutée et le bouton Enregistrer sous la liste.":::

### <a name="network-documentation"></a><span data-ttu-id="67cdd-122">Documentation réseau</span><span class="sxs-lookup"><span data-stu-id="67cdd-122">Network documentation</span></span>

<span data-ttu-id="67cdd-123">Le Talkie-walkie dans Teams requiert une connectivité Internet. En dessous des conditions réseau, une expérience optimale est requise.</span><span class="sxs-lookup"><span data-stu-id="67cdd-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="67cdd-124">Mesure</span><span class="sxs-lookup"><span data-stu-id="67cdd-124">Metric</span></span> | <span data-ttu-id="67cdd-125">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="67cdd-125">Required</span></span> |
|---|---|
|<span data-ttu-id="67cdd-126">Latence (RTT)</span><span class="sxs-lookup"><span data-stu-id="67cdd-126">Latency (RTT)</span></span> | <span data-ttu-id="67cdd-127">< 300 ms</span><span class="sxs-lookup"><span data-stu-id="67cdd-127">< 300ms</span></span> |
|<span data-ttu-id="67cdd-128">Jitter</span><span class="sxs-lookup"><span data-stu-id="67cdd-128">Jitter</span></span> |<span data-ttu-id="67cdd-129">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="67cdd-129">< 30ms</span></span> |
|<span data-ttu-id="67cdd-130">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="67cdd-130">Packet Loss</span></span> |<span data-ttu-id="67cdd-131">< 1 %</span><span class="sxs-lookup"><span data-stu-id="67cdd-131">< 1%</span></span> |

<span data-ttu-id="67cdd-132">Comme indiqué ci-dessus, la qualité des médias en temps réel sur un réseau IP est largement impactée par la qualité de la connectivité du réseau, mais surtout par la quantité de :</span><span class="sxs-lookup"><span data-stu-id="67cdd-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="67cdd-133">**Latence** - Il s’agit du temps que prend l’accès d’un paquet IP d’un point A à un point B sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="67cdd-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="67cdd-134">Ce retard de propagation sur le réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, ce qui comprend une surcharge des divers routeurs entre les deux.</span><span class="sxs-lookup"><span data-stu-id="67cdd-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="67cdd-135">La latence se mesure en durée de l’aller-retour (Round-trip Time, RTT).</span><span class="sxs-lookup"><span data-stu-id="67cdd-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="67cdd-136">**Perte de paquets** - Souvent définie comme le pourcentage de paquets perdus dans une période donnée.</span><span class="sxs-lookup"><span data-stu-id="67cdd-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="67cdd-137">La perte de paquets affecte directement la qualité audio, de petits paquets individuels perdus, pratiquement sans impact, aux pertes en rafale dos-à-dos à l’origine de coupures audio complètes.</span><span class="sxs-lookup"><span data-stu-id="67cdd-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="67cdd-138">**Gigue** - Il s’agit de la variation moyenne de délai entre les paquets successifs.</span><span class="sxs-lookup"><span data-stu-id="67cdd-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="67cdd-139">L’utilisation attendue des données de Talkie-walkie est d’environ 20 Kbits/s lors de l’envoi ou de la réception de fichiers audio.</span><span class="sxs-lookup"><span data-stu-id="67cdd-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="67cdd-140">Lorsqu’elles sont inactives, l’utilisation attendue des données de Talkie-walkie est en veille.</span><span class="sxs-lookup"><span data-stu-id="67cdd-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="67cdd-141">Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="67cdd-141">Walkie Talkie devices</span></span>

<span data-ttu-id="67cdd-142">Les employés en ligne doivent souvent parler et recevoir des appels Walkie Talkie même lorsque leur téléphone est verrouillé.</span><span class="sxs-lookup"><span data-stu-id="67cdd-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="67cdd-143">Cette expérience est possible via des appareils spécialisés avec un bouton PTT dédié.</span><span class="sxs-lookup"><span data-stu-id="67cdd-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="67cdd-144">Casques</span><span class="sxs-lookup"><span data-stu-id="67cdd-144">Headsets</span></span>
  - <span data-ttu-id="67cdd-145">Casques câblés[(Syzyn)](https://www.kleinelectronics.com/poc-accessories/mtwt/)</span><span class="sxs-lookup"><span data-stu-id="67cdd-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="67cdd-146">Casques sans fil[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)</span><span class="sxs-lookup"><span data-stu-id="67cdd-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="67cdd-147">Téléphones accidentés</span><span class="sxs-lookup"><span data-stu-id="67cdd-147">Rugged phones</span></span>
  - <span data-ttu-id="67cdd-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="67cdd-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="67cdd-149">[Plus d’informations.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)</span><span class="sxs-lookup"><span data-stu-id="67cdd-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="67cdd-150">[Guide de configuration.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)</span><span class="sxs-lookup"><span data-stu-id="67cdd-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="67cdd-151">Ces appareils ne sont pas certifiés Teams.</span><span class="sxs-lookup"><span data-stu-id="67cdd-151">These devices are not Teams certified.</span></span> <span data-ttu-id="67cdd-152">Ils ont été validés pour fonctionner avec Le Walkie Talkie de Teams.</span><span class="sxs-lookup"><span data-stu-id="67cdd-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="67cdd-153">Conditions de licence requises</span><span class="sxs-lookup"><span data-stu-id="67cdd-153">License requirements</span></span>

<span data-ttu-id="67cdd-154">L’application Talkie-walkie est incluse dans toutes les licences payantes de Teams dans [les abonnements Office 365.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="67cdd-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="67cdd-155">Pour plus d’informations sur l’obtention de Teams, consultez comment accéder [à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="67cdd-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="67cdd-156">Certaines fonctionnalités avancées peuvent nécessiter des licences supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="67cdd-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="67cdd-157">Par exemple, l’intégration avec samsung Galaxy XCover Pro nécessite une licence Knox.</span><span class="sxs-lookup"><span data-stu-id="67cdd-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="67cdd-158">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="67cdd-158">Further information</span></span>

- <span data-ttu-id="67cdd-159">Les itAdmins peuvent contrôler les personnes qui utilisent talkie-walkie via les stratégies d’application.</span><span class="sxs-lookup"><span data-stu-id="67cdd-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="67cdd-160">Si votre collègue en ligne utilise des données mobiles pour communiquer via Teams, le Talkie-walkie utilisera la même méthode.</span><span class="sxs-lookup"><span data-stu-id="67cdd-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="67cdd-161">Le Talkie-walkie doit fonctionner bien dans les situations de faible bande passante, ou dans les situations où votre smartphone est connecté et fonctionne.</span><span class="sxs-lookup"><span data-stu-id="67cdd-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="67cdd-162">Le Talkie-walkie ne fonctionne pas lorsqu’il n’y a aucune connexion.</span><span class="sxs-lookup"><span data-stu-id="67cdd-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="67cdd-163">Pour plus d’informations sur l’expérience utilisateur final, voir :</span><span class="sxs-lookup"><span data-stu-id="67cdd-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="67cdd-164">Démarrer le Talkie-walkie de Teams</span><span class="sxs-lookup"><span data-stu-id="67cdd-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="67cdd-165">Communiquer avec votre équipe grâce au Talkie-walkie</span><span class="sxs-lookup"><span data-stu-id="67cdd-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)