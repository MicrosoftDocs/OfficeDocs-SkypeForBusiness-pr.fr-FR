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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: b29ec51ddcb672f6727f7bc43958872962245ebb
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788974"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="7a8dc-103">Configurer votre réseau pour la Diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="7a8dc-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="7a8dc-104">Après avoir [Activer la diffusion de réunion Skype](enable-skype-meeting-broadcast.md) de diffusion de réunion Skype, vous devez configurer votre réseau.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="7a8dc-105">Effectuez cette étape si vous souhaitez bloquer les conférences Web et autres diffusions pour les personnes à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="7a8dc-106">Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="7a8dc-107">Pour ignorer cette étape et l’ajouter à la place une autre entreprise de votre fédération afin que vous pouvez les inviter à diffusions, suivez les étapes de [Autoriser les utilisateurs à contacts Skype externe pour les utilisateurs professionnels](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="7a8dc-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="7a8dc-108">Étape 1 : Configurer des domaines autorisés</span><span class="sxs-lookup"><span data-stu-id="7a8dc-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="7a8dc-109">Utilisez l' **une** des méthodes suivantes pour configurer des domaines autorisés :</span><span class="sxs-lookup"><span data-stu-id="7a8dc-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="7a8dc-110">**Méthode 1 : Utiliser le centre d’administration Office 365**</span><span class="sxs-lookup"><span data-stu-id="7a8dc-110">**Method 1: Use the Office 365 admin center**</span></span>

1. <span data-ttu-id="7a8dc-111">Accédez au **Centre d’administration Office 365** et puis, dans la navigation de gauche, cliquez sur **paramètres** > **Services &amp; compléments**, puis choisissez **Skype pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="7a8dc-112">Dans la page **partage externe** sous **exceptions du domaine**, sélectionnez **tous les domaines bloqués à l’exception**, puis entrez les domaines suivants, séparés par une virgule (,) :</span><span class="sxs-lookup"><span data-stu-id="7a8dc-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="7a8dc-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="7a8dc-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="7a8dc-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="7a8dc-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="7a8dc-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="7a8dc-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="7a8dc-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="7a8dc-116">resources.lync.com</span></span>

3. <span data-ttu-id="7a8dc-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="7a8dc-118">**Méthode 2 : Utiliser Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7a8dc-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="7a8dc-119">Dans le **Menu Démarrer**, avec le bouton droit de **Windows PowerShell** , cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="7a8dc-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="7a8dc-121">Étape 2 : Ajout de diffusion réunion Skype, les URL et les domaines IP adresses</span><span class="sxs-lookup"><span data-stu-id="7a8dc-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="7a8dc-122">La deuxième étape du processus d’installation est vous permet d’ajouter des domaines qui sont nécessaires, puis ajoutez des adresses IP et les URL qui sont requis pour la diffusion de réunion Skype travailler.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="7a8dc-123">**Ajouter le Skype requis pour les URL de point de terminaison Business en ligne et les adresses IP en consultant la rubrique celles qui sont requises** [ici](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="7a8dc-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="7a8dc-124">Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides</span><span class="sxs-lookup"><span data-stu-id="7a8dc-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="7a8dc-125">Si vous avez un Skype pour l’organisation d’entreprise en ligne et d’un déploiement local de Lync Server 2010, Microsoft Lync Server 2013 et Skype pour Business Server 2015 et avez des utilisateurs à la fois en ligne et sur site, il existe des autres étapes de configuration que vous devrez faire dans Outre celles ci-dessus pour permettre à votre organisation locale communiquer avec Skype pour Business Online et permettre à tous vos utilisateurs à participer à une réunion Skype de diffusion.</span><span class="sxs-lookup"><span data-stu-id="7a8dc-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="7a8dc-126">Pour voir quelles sont les conditions requises, voir [configuration de votre déploiement sur site de diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="7a8dc-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a8dc-127">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="7a8dc-127">Related topics</span></span>

[<span data-ttu-id="7a8dc-128">Autoriser la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="7a8dc-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="7a8dc-129">URL et plages d'adresses IP Office 365</span><span class="sxs-lookup"><span data-stu-id="7a8dc-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="7a8dc-130">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7a8dc-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



