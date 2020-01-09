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
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 95ad00be416a53e6e861ce4e9f235bded8e8075a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990979"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="faf60-103">Configurer votre réseau pour la Diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="faf60-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="faf60-104">Après l' [activation](enable-skype-meeting-broadcast.md) de la diffusion de réunion Skype, vous devez configurer votre réseau.</span><span class="sxs-lookup"><span data-stu-id="faf60-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="faf60-105">Cette étape permet de mettre en avant des webinaires et d’autres émissions pour des personnes extérieures à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="faf60-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="faf60-106">Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="faf60-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="faf60-107">Pour ignorer cette étape et ajouter une autre entreprise à votre Fédération pour pouvoir inviter celles-ci à être diffusées, suivez les étapes de la rubrique [autoriser les utilisateurs à contacter des utilisateurs Skype entreprise externes](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="faf60-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="faf60-108">Étape 1 : configurer les domaines autorisés</span><span class="sxs-lookup"><span data-stu-id="faf60-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="faf60-109">Pour configurer des domaines autorisés, utilisez l' **une** des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="faf60-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="faf60-110">**Méthode 1 : utiliser le centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="faf60-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="faf60-111">Accédez au centre d’administration, puis dans le volet de navigation de gauche, cliquez sur **paramètres** > des**compléments &amp; services**, puis sélectionnez **Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="faf60-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="faf60-112">Dans la page **partage externe** , sous **exceptions de domaine**, sélectionnez **tous les domaines sont bloqués à l’exception**de, puis entrez les domaines suivants, en les séparant par une virgule (,) :</span><span class="sxs-lookup"><span data-stu-id="faf60-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="faf60-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="faf60-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="faf60-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="faf60-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="faf60-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="faf60-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="faf60-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="faf60-116">resources.lync.com</span></span>

3. <span data-ttu-id="faf60-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="faf60-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="faf60-118">**Méthode 2 : utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="faf60-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="faf60-119">Dans le **menu Démarrer**, cliquez avec le bouton droit sur **Windows PowerShell** , puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="faf60-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="faf60-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="faf60-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="faf60-121">Étape 2 : ajouter des domaines, des URL et des adresses IP pour la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="faf60-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="faf60-122">La deuxième étape du processus de configuration consiste à ajouter d’abord les domaines nécessaires, puis à ajouter des adresses IP et des URL requises pour le bon fonctionnement de la diffusion de réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="faf60-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="faf60-123">**Ajoutez les URL et adresses IP de points de terminaison Skype entreprise Online requises en consultant les éléments requis** [ici](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="faf60-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="faf60-124">Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides</span><span class="sxs-lookup"><span data-stu-id="faf60-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="faf60-125">Si vous disposez d’une organisation Skype entreprise Online et d’un déploiement local de Lync Server 2010, Microsoft Lync Server 2013 et de Skype entreprise Server 2015 et que les utilisateurs sont connectés et en local, vous devez effectuer les opérations suivantes. vous pouvez également accéder à ces éléments pour permettre à votre organisation locale de communiquer avec Skype entreprise Online et de permettre aux utilisateurs de participer à une diffusion de réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="faf60-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="faf60-126">Pour connaître la configuration requise, reportez-vous à [la section configurer votre déploiement local pour la diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="faf60-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="faf60-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="faf60-127">Related topics</span></span>

[<span data-ttu-id="faf60-128">Activer une diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="faf60-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="faf60-129">URL et plages d’adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="faf60-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="faf60-130">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="faf60-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



