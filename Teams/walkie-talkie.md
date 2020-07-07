---
title: Application de discussion de Microsoft teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Découvrez comment configurer l’application de discussion de Microsoft teams à partir d’un point de vue ITAdmin.
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
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043009"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="a3ce5-103">Application de discussion de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a3ce5-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="a3ce5-104">L’application de notification de l’équipe de discussion dans teams fournit une communication instantanée et vocale pour votre équipe et sera bientôt disponible en préversion publique sur Android.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and will soon be available in Public Preview on Android.</span></span> <span data-ttu-id="a3ce5-105">Le Guide d’appel permet aux utilisateurs de communiquer avec leur équipe en utilisant les mêmes canaux sous-jacents dont ils sont membres.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="a3ce5-106">Seuls les utilisateurs qui se connectent à la fonctionnalité de conversation dans un canal deviennent des participants et pourront communiquer entre eux à l’aide de la fonctionnalité de communication d’une personne à la fois.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="a3ce5-107">En équipe, vous pouvez à tout moment communiquer en toute sécurité avec une expérience PTT familière sans avoir besoin de transporter des radios en vrac, et de se familiariser avec la connectivité Internet WiFi ou mobile.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="a3ce5-108">Prise en main</span><span class="sxs-lookup"><span data-stu-id="a3ce5-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="a3ce5-109">Déploiement de l’étape de discussion</span><span class="sxs-lookup"><span data-stu-id="a3ce5-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="a3ce5-110">Dans le cadre de la préversion publique, l’étape de conversation n’est pas préinstallée.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="a3ce5-111">Pour activer cette fonctionnalité pour les utilisateurs de votre organisation, vous devez ajouter le propos de l’outil de [configuration de l’application](teams-app-setup-policies.md)   affecté aux utilisateurs dans le centre d' [administration teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a3ce5-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="a3ce5-112">Dès qu’il est activé, vous pouvez désormais accéder à la discussion sur l’application Android dans les 48 heures.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="a3ce5-113">Ajouter un contact de votre liste d’applications</span><span class="sxs-lookup"><span data-stu-id="a3ce5-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="a3ce5-114">Dans le centre d’administration de Microsoft Teams, sous stratégies de configuration des **applications teams**  >  **Setup policies**, vous devez **On**activer l' **épinglage** pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="a3ce5-115">Dans la section applications épinglées, cliquez sur **+ Ajouter des applications**.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Affiche la section applications épinglées et le bouton Ajouter des applications à sélectionner.":::

<span data-ttu-id="a3ce5-117">Dans le volet **Ajouter des applications épinglées** qui s’affiche à droite, utilisez la zone de **recherche** pour rechercher un contact.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="a3ce5-118">Lorsque vous disposez d’un résultat de recherche, cliquez sur le bouton **Ajouter** à droite du nom pour l’ajouter à votre liste.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Affiche la barre latérale de l’option Ajouter des applications épinglées avec les résultats de la recherche dans le volet de recherche et l’application de présentation de l’aide du bouton Ajouter.":::

<span data-ttu-id="a3ce5-120">L’application de discussion à l’aide de l’application doit maintenant apparaître dans la liste des applications épinglées et être disponible lorsque vous cliquez sur le bouton **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="a3ce5-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Affiche la liste des applications épinglées avec l’application de conversation de discussion ajoutée et le bouton Enregistrer sous la liste.":::

### <a name="network-documentation"></a><span data-ttu-id="a3ce5-122">Documentation du réseau</span><span class="sxs-lookup"><span data-stu-id="a3ce5-122">Network documentation</span></span>

<span data-ttu-id="a3ce5-123">Dans Microsoft Teams, il est nécessaire de disposer d’une connectivité Internet et au-dessous des conditions de réseau pour une expérience optimale.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="a3ce5-124">Latence (RTT) < 300. Scintillement < 30ms | Perte de paquets < 1%</span><span class="sxs-lookup"><span data-stu-id="a3ce5-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="a3ce5-125">Comme indiqué plus haut, la qualité du contenu multimédia en temps réel sur un réseau IP est fortement affectée par la qualité de la connectivité du réseau, mais surtout par la quantité de :</span><span class="sxs-lookup"><span data-stu-id="a3ce5-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="a3ce5-126">**Latence** -il s’agit du temps nécessaire à l’obtention d’un paquet IP du point A au point B sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="a3ce5-127">Ce délai de propagation du réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, y compris la surcharge supplémentaire prélevée par les différents routeurs entre eux.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="a3ce5-128">La latence est mesurée en temps réel de boucle.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="a3ce5-129">**Perte de paquets** : il s’agit généralement du pourcentage de paquets perdus dans une période donnée.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="a3ce5-130">La perte de paquets affecte directement la qualité audio (par rapport aux petits paquets perdus individuels qui n’ont presque aucun impact, en raison d’une perte de Burst en retour en continu qui engendre une coupure audio complète).</span><span class="sxs-lookup"><span data-stu-id="a3ce5-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="a3ce5-131">**Scintillement** -il s’agit du changement moyen de délai entre les paquets successifs.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="a3ce5-132">L’utilisation de données attendue à partir de Walk parle est entourée de 20KB/s lors de l’envoi ou de la réception d’audio.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="a3ce5-133">En cas d’inactivité, la durée de l’utilisation des données de Walkship parle est négligeable.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="a3ce5-134">Appareils de discussion</span><span class="sxs-lookup"><span data-stu-id="a3ce5-134">Walkie Talkie devices</span></span>

<span data-ttu-id="a3ce5-135">Les travailleurs terrain doivent souvent parler et recevoir des appels à propos de l’appel, même si leur téléphone est verrouillé.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="a3ce5-136">Cette expérimentation est possible via des appareils spécialisés avec un bouton PTT dédié.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="a3ce5-137">Téléphones existants</span><span class="sxs-lookup"><span data-stu-id="a3ce5-137">Existing phones</span></span>
  - <span data-ttu-id="a3ce5-138">Casques câblés ([électronique Klein](https://www.kleinelectronics.com/))</span><span class="sxs-lookup"><span data-stu-id="a3ce5-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/))</span></span>
  - <span data-ttu-id="a3ce5-139">Casques sans fil ([Jabra BlueParrott](https://www.blueparrott.com/))</span><span class="sxs-lookup"><span data-stu-id="a3ce5-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/))</span></span>
- <span data-ttu-id="a3ce5-140">Des téléphones plus robustes</span><span class="sxs-lookup"><span data-stu-id="a3ce5-140">Rugged phones</span></span>
  - <span data-ttu-id="a3ce5-141">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="a3ce5-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="a3ce5-142">[Plus d’informations](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="a3ce5-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="a3ce5-143">[Guide de configuration](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)</span><span class="sxs-lookup"><span data-stu-id="a3ce5-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="a3ce5-144">Ces appareils ne sont pas des équipes certifiées.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-144">These devices are not Teams certified.</span></span> <span data-ttu-id="a3ce5-145">Elles ont été validées pour fonctionner avec le Guide de conversation de teams.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="a3ce5-146">Conditions de licence</span><span class="sxs-lookup"><span data-stu-id="a3ce5-146">License requirements</span></span>

<span data-ttu-id="a3ce5-147">L’application de discussion à propos de Microsoft est incluse dans toutes les licences payantes d’équipes dans les [abonnements Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span><span class="sxs-lookup"><span data-stu-id="a3ce5-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="a3ce5-148">Pour plus d’informations sur l’obtention d’équipes, voir [Comment obtenir l’accès à Microsoft teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="a3ce5-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="a3ce5-149">Certaines fonctionnalités avancées pourront nécessiter des licences supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="a3ce5-150">Par exemple, l’intégration de Samsung Galaxy XCover Pro nécessite une licence Knox.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="a3ce5-151">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="a3ce5-151">Further information</span></span>

- <span data-ttu-id="a3ce5-152">ITAdmins peut conserver le contrôle de qui utilise des stratégies de l’application.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="a3ce5-153">Si votre travailleur terrain utilise des données mobiles pour communiquer par le biais d’équipes, vous pouvez utiliser la même méthode.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="a3ce5-154">L’utilisation de la gestion des problèmes de bande passante devrait fonctionner correctement dans les situations de faible bande passante, ou dans les cas où votre smartphone est connecté et fonctionne.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="a3ce5-155">La discussion ne fonctionnera pas tant qu’il n’y a aucune connexion.</span><span class="sxs-lookup"><span data-stu-id="a3ce5-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="a3ce5-156">Pour en savoir plus sur l’utilisation des utilisateurs finaux, voir :</span><span class="sxs-lookup"><span data-stu-id="a3ce5-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="a3ce5-157">Commencer à utiliser teams</span><span class="sxs-lookup"><span data-stu-id="a3ce5-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="a3ce5-158">Communiquer avec votre équipe grâce au Guide de conversation</span><span class="sxs-lookup"><span data-stu-id="a3ce5-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
