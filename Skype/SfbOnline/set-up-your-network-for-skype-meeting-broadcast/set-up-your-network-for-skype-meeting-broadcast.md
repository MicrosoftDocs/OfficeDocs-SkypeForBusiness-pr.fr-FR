---
title: Configurer votre réseau pour la Diffusion de réunion Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106510"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="f9113-103">Configurer votre réseau pour la Diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="f9113-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="f9113-104">Après avoir [activé la diffusion de réunion Skype,](enable-skype-meeting-broadcast.md) vous devez configurer votre réseau.</span><span class="sxs-lookup"><span data-stu-id="f9113-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="f9113-105">Cette étape est prise en compte si vous souhaitez organiser des webinaires ou d’autres diffusions pour des personnes extérieures à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f9113-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9113-106">Skype Entreprise Online prend fin le 31 juillet 2021, date à laquelle l’accès au service prendra fin.</span><span class="sxs-lookup"><span data-stu-id="f9113-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="f9113-107">Nous encourageons les clients à commencer la mise à niveau vers Microsoft Teams, le client principal pour les communications et le travail d’équipe dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9113-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="f9113-108">Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="f9113-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="f9113-109">Pour ignorer cette étape et ajouter une autre entreprise à votre fédération afin de les inviter à des diffusions, suivez les étapes de la procédure Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise [externes.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="f9113-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="f9113-110">Étape 1 : configurer les domaines autorisés</span><span class="sxs-lookup"><span data-stu-id="f9113-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="f9113-111">Pour **configurer** des domaines autorisés, utilisez l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9113-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="f9113-112">**Méthode 1 : utiliser le Centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="f9113-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="f9113-113">Dans le Centre d’administration, dans le panneau de navigation gauche, cliquez sur Les  >  **&amp; modules add-ins**, puis sélectionnez **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="f9113-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="f9113-114">Sur la page **Partage externe** sous **Exceptions** de domaine, sélectionnez Tous les domaines sont **bloqués** sauf, et entrez les domaines suivants, séparés par une virgule (,) :</span><span class="sxs-lookup"><span data-stu-id="f9113-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="f9113-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9113-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="f9113-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9113-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="f9113-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9113-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="f9113-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="f9113-118">resources.lync.com</span></span>

3. <span data-ttu-id="f9113-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f9113-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="f9113-120">**Méthode 2 : utiliser les Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f9113-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="f9113-121">Dans le **menu Démarrer, cliquez** avec le bouton droit sur **Windows PowerShell** puis cliquez sur Exécuter en **tant qu’administrateur.**</span><span class="sxs-lookup"><span data-stu-id="f9113-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="f9113-122">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="f9113-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="f9113-123">Étape 2 : ajouter des domaines, des URL et des adresses IP pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="f9113-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="f9113-124">La deuxième étape du processus de configuration consiste à ajouter les domaines nécessaires, puis à ajouter les adresses IP et LES URL requises pour que la diffusion de réunion Skype fonctionne.</span><span class="sxs-lookup"><span data-stu-id="f9113-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="f9113-125">**Ajoutez les URL de** point de terminaison et les adresses IP Skype Entreprise Online requises en voyant ceux requis [ici.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)</span><span class="sxs-lookup"><span data-stu-id="f9113-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="f9113-126">Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides</span><span class="sxs-lookup"><span data-stu-id="f9113-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="f9113-127">Si vous avez une organisation Skype Entreprise Online et un déploiement local de Lync Server 2010, de Microsoft Lync Server 2013 et de Skype Entreprise Server 2015 et que vos utilisateurs sont à la fois en ligne et sur site, vous devez suivre d’autres étapes de configuration en plus de celle ci-dessus pour permettre à votre organisation sur site de communiquer avec Skype Entreprise Online et autoriser tous vos utilisateurs à participer à une diffusion de réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="f9113-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="f9113-128">Pour consulter les conditions requises, consultez Configurer votre déploiement [local pour la diffusion de réunion Skype.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="f9113-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9113-129">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f9113-129">Related topics</span></span>

[<span data-ttu-id="f9113-130">Activer une diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="f9113-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="f9113-131">URL et plages d’adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="f9113-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="f9113-132">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f9113-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)